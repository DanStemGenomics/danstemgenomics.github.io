## How to use Computerome

### Wiki
In this document, we only give you some of the basics to get started. For more details, go over the [Computerome Wiki](https://www.computerome.dk/display/C2W/Computerome+2.0) histed by DTU.

### KU-IT support
You can find some information in the [KU guide](https://kunet.ku.dk/work-areas/research/Research%20Infrastructure/research-it/computerome-2.0/Pages/default.aspx) inside the [Research IT and infrastructure](https://kunet.ku.dk/work-areas/research/Research%20Infrastructure/Pages/default.aspx) section of the research portal. If you have a problem and want to requet new features, please make a request in the [sd system](http://sd.ku.dk/).

### Cost
When requesting a new group in the [sd system](http://sd.ku.dk/), an alias is required, that will be charged. There are 2 main costs on C2: storage and compute. Those prices are given in the price section of the [KU guide](https://kunet.ku.dk/work-areas/research/Research%20Infrastructure/research-it/computerome-2.0/Pages/default.aspx) and group owners can have access to a Tableau interface with the details of the usage for all users using this group.
- Storage: cost is based on the maximum size of the data stored in the group during a given month. So if you have at some point in the month about 1 Tb stored in your group, you will be charged about 100 DKK for that month.
- Compute: more difficult to assess. The price is about 4 DKK per node, per hour. Typically, we compute on a single node (with many cores). So if you run computations for 10h, you should be charged arround 40 DKK. As an example, processing several runs on the platforms (= not so heavy computations, mapping, etc.), we have between 500 and 1500 DKK in computing per month. If you start doing computations that run for weeks (e.g. deep learning), you can get much more.

### Login
1. Open a terminal
2. Login with ssh: `ssh username@ssh.computerome.dk`
3. Enter your password
4. Enter the PASSCODE you receive on your phone
 
More on [the wiki](https://www.computerome.dk/display/C2W/SSH+login+to+Computerome+2.0)

### Project, directory and file structure

Predefined data structure:
- /home/people/yourlogin => this is your private space. Only for configuration files. Limited to 10Gb. DO NOT STORE DATA THERE. Typically, you don’t need to use it.
- /home/projects/yourproject => this is the shared space for your group/project. This is where you store data, results, etc.
- /home/databases/ => this is a shared resource so that we don’t have to all download the same databases, e.g. genomes.

Inside each project, the following structure is defined. `/home/projects/<project>` includes:
- ./apps
- ./apps/modulefiles
- ./backup
- ./data => typically here you have the group data (e.g. the processed genomics files)
- ./people/<user> => here you have your folder where you can do your things. Typically, I recommend creating a folder with the date each time you do something (e.g. 2020-08-27_my-first-test)
- ./scratch

To see what project(s) you have access to, you can type `id` to know.


Go back to the [Genomics Platform home](https://danstemgenomics.github.io)
