# labMONSTER

This repo is about script and resources to maintain the room-D324 computer called **'the MONSTER'**

This machine runs UBUNTU (swithced from centOS on the 19th september 2022)

Every user has their own user and has root priviledge

It has two main Volumes:

- ssd for daily use (1 TB + 1 TB) 
  
  :warning: **for the moment, please do not use `DATA_SSD`**

- hd for storage (6TB + 2 TB (should be) RAID 5)

## Table of content

- [labMONSTER](#labmonster)
  - [Table of content](#table-of-content)
  - [Best practices](#best-practices)
  - [New user](#new-user)
  - [FAQ](#faq)
    - [How can I connect remotely?](#how-can-i-connect-remotely)
    - [I can't connect remotely](#i-cant-connect-remotely)
    - [How do I know if there is HD space on the computer?](#how-do-i-know-if-there-is-hd-space-on-the-computer)
    - [How do I know if someone else is using part or all the cpus/RAM?](#how-do-i-know-if-someone-else-is-using-part-or-all-the-cpusram)
    - [I run a command in remote and closed the connection and it seems that the command was quit](#i-run-a-command-in-remote-and-closed-the-connection-and-it-seems-that-the-command-was-quit)
    - [How do I exchange files from somewhere to the MONSTER and back (especially if working remotely)?](#how-do-i-exchange-files-from-somewhere-to-the-monster-and-back-especially-if-working-remotely)
    - [Machine is stuck when switching user with blinking cursor](#machine-is-stuck-when-switching-user-with-blinking-cursor)
  - [Specs](#specs)
  - [List installed software](#list-installed-software)
    - [Installed with `sudo snap install ***`](#installed-with-sudo-snap-install-)
    - [Installed with `sudo apt-get ***`](#installed-with-sudo-apt-get-)
    - [Installed manually](#installed-manually)
      - [FSL](#fsl)
      - [MATLAB 2017a](#matlab-2017a)
      - [MATLAB 2018a](#matlab-2018a)
      - [AFNI](#afni)
      - [freesurfer](#freesurfer)
      - [itksanp](#itksanp)
    - [to do](#to-do)

## Best practices

- Free up space asap
- Can you run the analyses you intend to perform on the UCLouvain cluster (e.g. fmriPrep, mriqc, anything that can be run on Octave)? If yes, then try to move it there.
- Delete your user when you know you will not use the monster anymore
- Book screen and/or cpu time on the calendar `cpp : monster`
- The monster is a common space so contribute to make it better by sharing issues/solution via this documentation
- If you are running massive computation speak with other user
- For your cyber sicurety, better not leaving logged sensitive websites eg emails, google/safari (all your passwords are saved there!!!) etc.
- Consider to share your user password with someone else in the lab so easier to deal woth your use if you are not aroudn a and you forgot to back up or delete your user
- After a year of unused user, it will be deleted automatically
- If you have problems, you need to install softwares or anything else you are not sure about, open an issue [here](https://github.com/cpp-lln-lab/labMONSTER/issues/new/choose) or ask the current monster maintaner (at the moment is @marcobarilari)
  
## New user 

1. Read these docs and ask question/open issue if something is not clear
2. Ask a sudo user to create your user
3. Enjoy and improve others experience by imporoving this documentation with your experience

## FAQ 

### How can I connect remotely?

Ask Marco

### I can't connect remotely

Are you in the UCLouvain network or using a VPN to connect as-if you are within the UCLouvain network? Check [how to use UCLouvain VPN here](https://intranet.uclouvain.be/fr/myucl/services-informatiques/vpn.html) 

### How do I know if there is HD space on the computer?

run `df -h` on a terminal, volumes of interests are:

- `tmpfs`: HDD for archive usage
- `/dev/nvme0n1p2`: SSD on which the OS is istalled and operting for day by day use.
- `/dev/nvme1n1p1`: avoid using this one, it will become a back-up fo `/dev/nvme1n1p2` (RAID1)

```bash
Filesystem      Size  Used Avail Use% Mounted on
tmpfs           6,3G  4,3M  6,3G   1% /run
/dev/nvme0n1p2  938G  230G  661G  26% /
tmpfs            32G  150M   32G   1% /dev/shm
tmpfs           5,0M  4,0K  5,0M   1% /run/lock
/dev/nvme1n1p1  938G   28K  891G   1% /mnt/91061732-7f0e-4c15-9251-185421ec948a
/dev/nvme0n1p1  511M   31M  481M   6% /boot/efi
tmpfs           6,3G  164K  6,3G   1% /run/user/1000
tmpfs           6,3G  2,5M  6,3G   1% /run/user/1003
tmpfs           6,3G  4,7M  6,3G   1% /run/user/1001
tmpfs           6,3G  120K  6,3G   1% /run/user/1004
tmpfs           6,3G  2,5M  6,3G   1% /run/user/1005
tmpfs           6,3G   88K  6,3G   1% /run/user/127
```

### How do I know if someone else is using part or all the cpus/RAM?

run `htop` on the terminal, it is a "graphic" interface displaying live command running and by who, each cpu usage, and RAM usage.

### I run a command in remote and closed the connection and it seems that the command was quit

Did you use `screen`? Check the guide [SSH-tips](SSH-tips.md)

### How do I exchange files from somewhere to the MONSTER and back (especially if working remotely)?

Please use Datalad and GIN. _Why?_ Because it is easy for you to drop files and free up space since this machine is a crunch machine and not a data archive machine. BUT... If you are in a rush, check [SSH-tips](SSH-tips.md) on how to use `scp` command.

### Machine is stuck when switching user with blinking cursor

use `Ctrl` + `Alt` + `F2`

## Specs

**ADD SPECS**

## List installed software

### Installed with `sudo snap install ***`

to update all the software use `sudo snap refresh`

- gitkraken - available for all users
- vscode - available for all users
- octave (7.1.9) - available for all users
- docker (20.10.14) - available for all users, docker images are shared across users

[ TIPS :bulb: ]

If ayou are a new user and don't want to use 'sudo' everytime you call a `docker` command , use the first time `sudo usermod -aG docker $USER` (log out and in again :/)

### Installed with `sudo apt-get ***`

- git - available for all users
- git-annex - available for all users
- openssh-server (to acces remotly) [installation guide](https://linuxize.com/post/how-to-enable-ssh-on-ubuntu-18-04/)  and [user guide](`SSH-access.md`)- TO CHECK if available for all users
- screen (to open terminal sessions while accessing remotley) [installation guide](https://linuxize.com/post/how-to-use-linux-screen/) and [user guide](`SSH-access.md`)- TO CHECK if available for all users
- r - TO CHECK if available for all users
  
[ TIPS :bulb: ]

1. to update the list of available softwre online `sudo apt-get update`
2. to upgrade the list of software installed via `apt` use `sudo apt-get upgrade`


### Installed manually

- chrome - TO CHECK if available for all users
- dropbox - TO CHECK if available for all users
- conda via miniconda - each user has to install it indipendently (see here [miniconda installer](https://docs.conda.io/en/latest/miniconda.html))
- rstudio - TO CHECK if available for all users
- datalad - each user has to install it indipendently via `pip install`

#### FSL

fsleyes via conda - each user has to install it indipendently

TO CHECK if available for all users

[ TIPS :bulb: ]

- add this in in `~/.baschrc` to help FSL being more reachable

```bash
#FSL
FSLDIR=/usr/local/fsl
. ${FSLDIR}/etc/fslconf/fsl.sh
PATH=${FSLDIR}/bin:${PATH}
export FSLDIR PATH
```

- open FSL gui using `fsl` in the terminal

- open fsleyes gui using `fsleyes` in the terminal, if installed via conda you need to activate it first via `conda activate`

#### MATLAB 2017a

TO CHECK if available for all users (tools eg spm12 should be installed by each user)

[ TIPS :bulb: ]

- open matlab gui using `/usr/local/MATLAB/R2017a/bin/matlab` in the terminal, to be faster add an aliasia in the `~/.bashrc` file

```bash
alias matlab2017=/usr/local/MATLAB/R2017a/bin/matlab
```

#### MATLAB 2018a

TO CHECK if available for all users (tools eg spm12 should be installed by each user)

[ TIPS :bulb: ]

- open matlab gui using `/usr/local/MATLAB/R2018a/bin/matlab` in the terminal, to be faster add an aliasia in the `~/.bashrc` file

```bash
alias matlab2018=/usr/local/MATLAB/R2018a/bin/matlab
```

- how to run matlab script the lazy way:

1. Write down a bash function in eg `~/.my-func` named `matlabrun.sh`

```bash

#!/bin/bash

#matlabrun function 

matlabrun () {

    script_path=$1

    matlab -nodisplay -nosplash -nodesktop -r "run('"${script_path}"');"

}

```

where `matlab` here is an alias for `/usr/local/MATLAB/R2018a/bin/matlab`

2. Run or add `source ~/.my-func/matlabrun.sh` to either `~/.bashrc` `~/.bash_profile` or `~/.zrsrc` depending on your set up environment

3. Usage in a terminal:

```bash
matlab path/to/script.m
```

#### AFNI

each user has to install it indipendently (most of missing libraries should be installed for everyone so now should be easier)

[ TIPS :bulb: ]

- afni setup is not 100% done since we are missing some libraries as `libGLw.so.1` and `libgsl.so.19`

from running 'afni_system_check.py -check_all':

```bash
testing ability to start various programs...
    afni                 : success
    suma                 : FAILURE
        suma: error while loading shared libraries: libGLw.so.1: cannot open shared object file: No such file or directory
    3dSkullStrip         : FAILURE
        3dSkullStrip: error while loading shared libraries: libGLw.so.1: cannot open shared object file: No such file or directory
    uber_subject.py      : success
    3dAllineate          : success
    3dRSFC               : FAILURE
        3dRSFC: error while loading shared libraries: libgsl.so.19: cannot open shared object file: No such file or directory
    SurfMesh             : FAILURE
        SurfMesh: error while loading shared libraries: libGLw.so.1: cannot open shared object file: No such file or directory
    3dClustSim           : success
    3dMVM                : success
```

#### freesurfer

available for all users

[ TIPS :bulb: ]

- set up freesurfer by adding this in `~/.bashrc` and then take care to have license somewhere

```bash
export FREESURFER_HOME=/usr/local/freesurfer/7.3.2
source $FREESURFER_HOME/SetUpFreeSurfer.sh
```
#### itksanp

available for all users

- run this in the terminal to call the app via terminal with `itksnap`

```bash
export PATH=$PATH:/usr/local/itksnap-3.8.0-20190612-Linux-gcc64/bin
```

### to do
