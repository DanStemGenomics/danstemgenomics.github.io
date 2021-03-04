## How to use Computerome

### Wiki
In this document, we only give you some of the basics to get started. For more details, go over the [Computerome Wiki](https://www.computerome.dk/display/C2W/Computerome+2.0).

### KU-IT support
You can find some information in the [KU guide](https://kunet.ku.dk/employee-guide/Pages/IT/Computerome-2.0.aspx ) and make some requests in the [sd system](http://sd.ku.dk/).

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
