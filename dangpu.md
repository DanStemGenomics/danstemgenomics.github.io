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
If you are not familiar with Slurm, please learn online with this [quick start](https://slurm.schedmd.com/quickstart.html) or something else.

There are some modules installed, which you can see via `module avail`.

Go back to the [Genomics Platform home](https://danstemgenomics.github.io)
