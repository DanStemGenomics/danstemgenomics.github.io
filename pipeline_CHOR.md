## CHOR-seq pipeline

### Setting-up
We define here a few variables. You can use them as real variables in a script (called with the dollar sign `$VARIABLE`), or you can just see those names as some placeholder that you replace with your values every time it appears.

First we need to know where the reads are. If you have single-read data, each sample will have a single fastq file:

`SAMPLE=my.sample.fastq.gz`

If the file is not in the current working directory, you need to add the path as well:

`SAMPLE=/path/to/my/data/my.sample.fastq.gz`

And `NAME` is the name of your sample, without the .fastq.gz.

Now, if you are working with paired-end data, each sample will have 2 fastq files:

`R1=my.sample.R1.fastq.gz` 

`R2=my.sample.R2.fastq.gz`  

You also define here where all the files will be created. Let's call it the output directory. It's best practice to create all the files in a separate folder so that if something does not work as you expect, it's easy to delete (or rename) the output directory and start again from scratch.  
`OUTDIR=CHOR-OUTPUT`

If you (really) want to generate the files in your current directory, just define `OUTDIR=.` or ignore/delete every time `$OUTDIR` appears.

### Step 1: Trimming reads

For single-read, you can use trim_galore this way:

`trim_galore $SAMPLE -o $OUTDIR --fastqc`

Trim_galore is only a wrapper method that uses cutadapt inside. It will create a file 

`R1trim=$OUTDIR/${NAME}_trimmed.fq.gz`

For paired-end, for some reason (that I don't really remember), I use cutadap directly like that:

`cutadapt -a CTGTCTCTTATA -A CTGTCTCTTATA -q 20 -m 5 -o $R1trim -p $R2trim $R1 $R2`

 ### Step 2: Mapping to the reference genome
 
 Let's consider that our reference genome is mouse (mm10). We're going to map the reads with Bowtie2.
 
 First, we need to create our Bowtie index. Let's assume for now that you have your index here:
 
 `BOWTIEIDX=your/path/Mouse/mm10/Bowtie2Index/genome`
 
 Note that `genome` here is the prefix of all you index files in this folder.
 
 You will map with Bowtie2, then create the BAM file and then sort the BAM file.
 
 We can compress all those steps like that:
 
 `bowtie2 -x $BOWTIEIDX -U $R1 | samtools view -Sb -F 4 - | samtools sort - -o $BAM`
 
 And if you have access to several cores, you can use the option with the number of threads to go faster (e.g. on Computerome 2 you can get up to 40 - if you have requested the resources):
 
 `bowtie2 -p $NCORES -x $BOWTIEIDX -U $R1 | samtools view -@ $NCORES -Sb -F 4 - | samtools sort -@ $NCORES - -o $BAM`
 
 
 Go back to the [Genomics Platform home](https://danstemgenomics.github.io)
 
