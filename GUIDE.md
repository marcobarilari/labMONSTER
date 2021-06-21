## Install and set up Datalad

>DISCLAIMER: if some steps are not working, try to close and open the terminal again

0. (if necessary) Install Miniconda, this should take care of installing pythin as well

see here [Install Miniconda on CentOS 7 / RedHat 7](https://deeplearning.lipingyang.org/2018/12/24/install-miniconda-on-centos-7-redhat-7/)

nb:

```bash
# snippet code to de/activate the conda environment
conda actiavate
conda deactivate
```

1. create a virtual environment with `virtualenv` to use datalad (highly suggested for each software running under python)

```bash
# make sure you have `virtualenv` installed, if not install it via pip
virtualenv --version

# make sure you are in ~ and create the virtual environment folder
cd ~
virtualenv datalad

# and activate it
source datalad/bin/activate

# you should see something like this in your terminal
# (datalad) (base) [marcobar@0013 ~]$
```

2. Datalad installation and configuration (from the [datalad handbook](https://handbook.datalad.org/en/latest/intro/installation.html)) + [GIN](https://gin.g-node.org/) configuration

```bash
# install datalad
conda install -c conda-forge datalad

# configure your git account
git config --global --add user.name "your-username"
git config --global --add user.email "your-email@example.com"

# generate the ssh key to interact with gin
ssh-keygen -t rsa -b 4096 -C "your-email@example.com"
# retrieve the ssh key to be set on the gin website preferences
# copy the output and add it to the keys in gin (gin.g-node.org>your settings>SSH Keys>add key>etc.)
cat ~/.ssh/id_rsa.pub

# if the last command does not work, navigate to the folder and look hoe the *.pub file has been called
cd ~/.ssh/
ls
# etc.
