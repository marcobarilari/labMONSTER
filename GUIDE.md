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
# make sure you have `virtualenv` installed
virtualenv datalad
 source datalad/bin/activate
conda install -c conda-forge datalad
```
git config --global --add user.name "marcobarilari"
git config --global --add user.email "marcobarilr@gmail.com"
ssh-keygen -t rsa -b 4096 -C "marcobarilr@gmail.com"
cd ~/.ssh/
ls
cat ~/.ssh/id_rsa.pub
