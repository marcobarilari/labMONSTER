# labMONSTER

This repo is about script and resources to maintain the room-D324 computer called **'the MONSTER'**

This machine runs UBUNTU (swithced from centOS on the 19th september 2022)

Every user has their own user and has root priviledge

It has two main Volumes:

- ssd for daily use (1 TB + 1 TB) **for the moment, please do not use `DATA_SSD`**

- hd for storage (6TB + 2 TB RAID xxx)

## Specs

**ADD SPECS**

## Installed software

### with `sudo snap install ***`:

to update all the software use `sudo snap refresh` 

* gitkraken - available for all users

* vscode - available for all users

* octave (7.1.9) - available for all users

* docker (20.10.14) - available for all users as well as docker images

if ayou are a new user and don't want to use 'sudo' everytime, use the first time `sudo usermod -aG docker $USER` (log out and in again :/)

### with `sudo apt-get ***`

to update the list of available softwre online `sudo apt-get update`

to upgrade the list of software insstall via `apt` use `sudo apt-get upgrade`

* git

* git-annex

* openssh-server (to acces remotly) [installation guide](https://linuxize.com/post/how-to-enable-ssh-on-ubuntu-18-04/), TO CHECK if available for all users

* screen (to open terminal sessions while accessing remotley) [installation guide](https://linuxize.com/post/how-to-use-linux-screen/), TO CHECK if available for all users

### manually

* chrome - TO CHECK if available for all users

* dropbox - TO CHECK if available for all users

* conda via miniconda BUT each user has to install indipendently (see here [miniconda installer](https://docs.conda.io/en/latest/miniconda.html))

* FSL

in `.baschrc`
```bash
#FSL
FSLDIR=/usr/local/fsl
. ${FSLDIR}/etc/fslconf/fsl.sh
PATH=${FSLDIR}/bin:${PATH}
export FSLDIR PATH
```
open gui with `fsl` in the terminal

* fsleyes via conda

open gui with `fsleyes` in the terminal, if installed via conda you need to activate it first

* matlab, open the GUI with `/usr/local/MATLAB/R2017a/bin/matlab` - TO CHECK if available for all users

### to do
* freesurfer - available for all users at `/usr/local/freesurfer/7.2.0-1`
* datalad
* ITK snap