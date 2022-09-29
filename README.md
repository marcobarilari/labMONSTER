# labMONSTER

This repo is about script and resources to maintain the room-D324 computer called **'the MONSTER'**

This machine runs UBUNTU (swithced from centOS on the 19th september 2022)

Every user has their own user and has root priviledge

It has two main Volumes:

- ssd for daily use (1 TB + 1 TB) **for the moment, please do not use `DATA_SSD`**

- hd for storage (6TB + 2 TB RAID xxx)

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


### Install manually

- chrome - TO CHECK if available for all users
- dropbox - TO CHECK if available for all users
- conda via miniconda - each user has to install it indipendently (see here [miniconda installer](https://docs.conda.io/en/latest/miniconda.html))
- FSL - TO CHECK if available for all users
- fsleyes via conda - each user has to install it indipendently
- matlab 2017a - TO CHECK if available for all users
- rstudio - TO CHECK if available for all users
- afni - each user has to install it indipendently (most of missing libraries should be installed for everyone so now should be easier)

[ TIPS :bulb: ]

1. add this in in `~/.baschrc` to help FSL being more reachable

```bash
#FSL
FSLDIR=/usr/local/fsl
. ${FSLDIR}/etc/fslconf/fsl.sh
PATH=${FSLDIR}/bin:${PATH}
export FSLDIR PATH
```

2. open FSL gui using `fsl` in the terminal


3. open fsleyes gui using `fsleyes` in the terminal, if installed via conda you need to activate it first via `conda activate`

4. open matlab gui using `/usr/local/MATLAB/R2017a/bin/matlab` in the terminal, to be faster add an aliasia in the `~/.bashrc` file

```bash
alias matlab=/usr/local/MATLAB/R2017a/bin/matlab
```

5. afni setup is not 100% done since we are missing some libraries as `libGLw.so.1` and `libgsl.so.19`

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



### to do
* freesurfer - available for all users at `/usr/local/freesurfer/7.2.0-1`
* datalad
* ITK snap