# New Starter Software

## Operating Systems: Linux/Ubuntu
For code development it is much easier to work in a Linux environment so most of us in the group dual boot windows/Ubuntu. I tend to avoid using windows if possible because the stock UKAEA windows build is very slow - I only use it if I absolutely have to use microsoft office. Otherwise I try to use web apps for everything else like outlook, teams etc. The big advantage of Ubuntu is that you can install whatever you like without needing to log a ticket with the IT department. Make sure the version of Ubuntu you install is the previous LTS (long term support) version as this will be most stable.

If you have a low spec refurbished laptop I would recommend completely removing windows and just running Ubuntu as it uses much less resources and the laptop will run much faster.

### The terminal
Doing things on Ubuntu is different to windows/macos. At least half the time you will be using a terminal (also called a command prompt) to enter commands to install or run software. The software training listed below is a good resource for getting familiar with the terminal. To open a terminal in Ubuntu you can use the shortcut key combination `ctrl+alt+t`. Any of the commands listed below for installation will need to be entered into the terminal.

Another key thing about the terminal is that you can create you own shortcut commands by editing the `.bashrc` file in your home directory. Note that the '.' indicates this is a hidden file so you will have to turn on hidden file visibility to see and edit it or use the command `ls -a` in the terminal. An example of one I use is to access the VPN using the alias `workvpn` by adding the following at the bottom of my `.bashrc`:

```bash
alias workvpn="sudo openfortivpn vpn.ukaea.uk:943 --username=wx5768"
```

## Git Training
UKAEA has some excellent resources for getting you up to speed with using git to version control code:

https://software-training.gitpages.ccfe.ac.uk/version-control-with-git/

Go through this in detail because you will be using git a lot!

## General High-Performance Computing Training
The following DIRAC course on high performance computing fundamentals is an excellent introduction to super computing systems and the key skills you will need such as SSH, using the terminal, version control with git etc. The course is free and you can sign up here:

https://dirac.ac.uk/courses/hpc-skills-training/

I would recommend you complete this course before getting into the weeds of developing your own software. If you have done the git training above the git section should be easy.

To teach myself about the terminal, git, ssh and other software principles I started a git repository specifically for writing notes and commands I needed to remember in markdown format. By writing your own reference guides like this you will have your own cheat sheet when you forget things like me!

## Software to Install
### VSCode
This is a great universal and easy to use code editor. It has extensions for syntax highlighting for every tool we use. I would install the following extensions:
- python extension
- pylint extension
- moose extension
- gmsh extension

### Python: Miniforge / Mamba
Ubuntu comes with a pre-canned version of python the problem is that this tied to the operating system so you don't want to touch it in case you break your OS. The best way to deal with this is to create virtual environments that have their own isolated version of python. I do this using miniforge/mamba. You can find the install instructions for these here:

- https://mamba.readthedocs.io/en/latest/installation/mamba-installation.html

- https://github.com/conda-forge/miniforge

Grab the shell install script from the miniforge github and run it to install mamba. Once you have installed mamba you can use it to create a virtual environment called 'dev-env' with the following commands in the terminal:

```shell
mamba create -c conda-forge -n dev-env numpy scipy pandas matplotlib sympy cython pytest
```

This creates a virtual environment with various useful packages (numpy etc). Note that it is good practice to leave the 'base' environment alone with your mamba install. Having the 'base' environment auto activate when you open a terminal can mess up installation of other software so I set it to not activate using the following command:

```bash
mamba config --set auto_activate_base false
```

### MOOSE: Multi-physics object oriented simulation environment
This is an open-source finite element based simulation toolbox. I use moose apps which are built by our advanced computing team - the main one being
`proteus` which you can find here:

https://github.com/aurora-multiphysics/proteus

Once you have that installed there is some moose training material here:

https://ukaeauk-my.sharepoint.com/:f:/g/personal/lloyd_fletcher_ukaea_uk/Et98xVoomL1FsUExHFcA-nMBVBmGXJq5Lb0M8MsrXEINfQ?e=lif32K

Then I would go through the tutorials on the moose website here:

https://mooseframework.inl.gov/modules/heat_transfer/tutorials/introduction/index.html
https://mooseframework.inl.gov/modules/solid_mechanics/tutorials/introduction/index.html


### Gmsh and Paraview
In addition to moose you will need something to help you build more complex meshes (`gmsh`) and something to let you look at the results (`paraview`). You can download these from here:

- Gmsh: https://gmsh.info/#Download
- Paraview: https://www.paraview.org/download/

I recommend you create a `.bahsrc` alias to run them from terminal if needed, something like this but make sure to change the path to match where you put it on your system:

```bash
alias pview='~/paraview/bin/paraview'
alias gmsh='~/gmsh/bin/gmsh'
```

### VPN on Linux
The following terminal command will install the vpn client:
```shell
sudo apt install openfortivpn
```

You can then run the vpn using the following command:
```bash
sudo openfortivpn vpn.ukaea.uk:943 --username=UKAEA_USERNAME
```

Make sure you replace the `UKAEA_USERNAME` with your UKAEA username which will be alpha numeric, for example mine is wx5768. You will then need to leave the terminal window open with the VPN running. You can close the VPN using the `ctrl+c` in the terminal window to stop the process. As mentioned above you can add the following to your `.bashrc` file to create an alias to access this quickly from terminal.

## Digital Image Correlation Software: MatchID
https://www.matchid.eu/Portal/login.php
- Username: AEA_YS
- Password: MatchID

You can also access the MatchID wiki with tutorials from here. Note that MatchID only runs on windows machines and you will need a USB license dongle to use the software on your computer. We have two on site at FTF Yorkshire. One is permanently in the shared workstation L2919 which you can access remotely using the instructions above.

## 3D Printing and CAD
The general workflow for 3D printing is:

1. Create a 3D model using CAD software – FreeCAD
2. Create an external mesh of the 3D model and export as a *.stl – also can be done in FreeCAD
3. Import the *.stl into Prusa Slicer, set the printing options and slice the model. Export a *.gcode file which can be copied to the printers SD card
4. Print the model

All these steps are described in more detail in this design for 3D printing guide I put together:
https://ukaeauk-my.sharepoint.com/:p:/g/personal/lloyd_fletcher_ukaea_uk/EVXZxXxyv9hDif6wCm79FEYBk63KO6_vsiImORvxXrGHdg?e=bckUQJ

You will probably want to go through some FreeCAD tutorials to get used to it because it is a bit clunky (like all CAD programs are). Once you are used to it is quite powerful. A good series of youtube tutorials can be found here:
https://www.youtube.com/playlist?list=PLP1rv37BojTd5NY3E_aqOWUe0uA8J-J1T


## Accessing high specification workstations
There are two workstations at FTF Yorkshire for FE modelling and DIC data processing. These are 32 core AMD systems with 256GB RAM and a mid level Nvidia GPU currently dual booting windows/ubuntu. The UKAEA asset numbers are listed below along with the IP addresses to use ssh to access ubuntu. You will need these numbers to log in to the computers remotely:

- L2918, IP: 10.208.194.51
- L2919, IP: 10.208.192.67

**NOTE: To access any UKAEA computer remotely you will need to be on the vpn.**

These computers have two fast SSDs on the smaller 1TB are the operating systems (windows/ubuntu). There is also a 2TB SSD that can be used for fast data processing or running programs that need fast io. On the 2TB SSD create a folder with your name to store your files. Make sure to move things onto the slower normal hard disks when you are done as the fast SSDs are only meant for live processing.

If you need ssh access to these please contact a sudo user

### GUI Windows Remote Access
These are the remote connection instructions from a windows machine to the workstations:

• First make sure you are connected to the VPN using Forticlient or connected to the UKAEA network through a cable/docking station.
• Click the windows symbol and type ‘Remote Desktop Connection’ – click and open the windows remote desktop app
• In the computer box type the name of the PC follow by: .ccfepc.ccfe.ac.uk
    ◦ EXAMPLE: L2919.ccfepc.ccfe.ac.uk
• You will then be prompted for a username and password. If you are connected to the UKAEA network with a cable you need to input your alphanumeric username (e.g. wx5768). If you are offsite and connected through the VPN then you use you UKAEA email as the username (e.g. lloyd.fletcher@ukaea.uk). The password will be your normal UKAEA password regardless of the username.
• This should log you into the computer and you should be able to use it normally – beware if another user is logged into the machine then a warning dialogue will appear. If you continue to log in then the other user will be kicked off and they will loose any simulation data that is currently running. If this happens please contact the other user to make sure you are not accidentally stopping their simulation or data processing.

Note that the windows remote desktop clent can output a *.rdp file which can be used in Ubuntu to remotely access the computer by desktop - however, I recommend you use ssh where possible to get used to it as supercomputers don't have a gui options.

## GUI Remote Access for Ubuntu
For Ubuntu you can use the in-built remmina application to connect using *.rdp files for the configuration here:
https://ukaeauk-my.sharepoint.com/:f:/g/personal/lloyd_fletcher_ukaea_uk/EnKKDbem75RIle7TCduPMCEB2ajRw16ICo1BPTLn3wAGnA?e=fenbcB