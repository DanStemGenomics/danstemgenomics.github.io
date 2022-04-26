## How to use DanGPU

### What is DanGPU
DanGPU is a server bought by DanStem and administered by KU-IT for computational experts needing to connect large datasets stored on KU-IT storage to compute (DL580, 120 CPU cores, 4 GPUs RTX8000, RedHat). It is primarily based at image data analysis.

### KU-IT support
For support, please create a ticket in the [sd system](http://sd.ku.dk/).

### Getting access
Please email Magali Michaut.

### Login
Login is done via the KU credentials (the 6 characters id and associated password).
1. Connect to CISCO VPN
2. Open a terminal
3. Login with ssh: `ssh KUid@dangpu01fl.unicph.domain`
4. Enter your KU password

### Folder structure
Here are a few locations to know about:
1. /home/\<ku-id\> This is your home. Only you have access. The foder has a quota of 10 Gb. In general, you don't put anything there (maybe a few config files), but rather use the project folder(s) to put your experiments (even if you are the only one working on this project at this time).
2. /home/\<ku-id\>/ucph/groupdir/ This is where the unicph network drives you have access to are mounted.
3. /home/\<ku-id\>/ucph/securedir This is where the S-drive (for secured data) are mounted.
4. /project/dan1 This is the (for now only) project that we are all in. We can define more projects later on if we need to split access. It is recommended that you put your files into /project/dan1/people/\<ku-id\>

### Resource management with Slurm

Resources are managed via Slurm. Please do not do any computing outside slurm.
Before running anything on the server, check the status following the steps described in the slides here: /Volumes/SUN-DAN-server/SHARED/2022-03-15_dangpu-meeting-server-basics.pdf
If you are not familiar with Slurm, you can find some basic info in the slides and learn online with this [quick start](https://slurm.schedmd.com/quickstart.html) or something else.

### Rstudio

You can access Rstudio here: [http://dangpu01fl:8787/](http://dangpu01fl:8787/).

### Software

There are some modules installed, which you can see via `module avail`.

Here some software you might miss:
* cutadapt: module load miniconda/4.10.4 ; conda activate cutadaptenv
* refgenie: module load miniconda/4.10.4 refgenie/0.12.1 (might need to define the REFGENIE variable)
* TEtranscripts: module load anaconda3/2021.11 tetranscripts/2.2.1


Go back to the [Genomics Platform home](https://danstemgenomics.github.io)
