## How to use DanGPU

### What is DanGPU
DanGPU is a server bought by DanStem and administered by KU-IT for computational experts needing to connect large datasets stored on KU-IT storage to compute (including GPU). It is primarily based at image data analysis.

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

### Resource management with Slurm

Resources are managed via Slurm. Please do not do any computing outside slurm.
If you are not familiar with Slurm, please learn online with this [quick start](https://slurm.schedmd.com/quickstart.html) or something else.

There are some modules installed, which you can see via `module avail`.

Go back to the [Genomics Platform home](https://danstemgenomics.github.io)
