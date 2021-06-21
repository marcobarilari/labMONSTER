## Install and set up Datalad

1. Install python 3

cd /opt
sudo wget https://www.python.org/ftp/python/3.8.7/Python-3.8.7.tgz

sudo tar xzf Python-3.8.7.tgz
cd Python-3.8.7
sudo ./configure --enable-optimizations
sudo make altinstall
python3.8 -V
 cd /opt
sudo rm -f Python-3.8.7.tgz


cd ~

wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
sh Miniconda3-latest-Linux-x86_64.sh
conda -V
conda actiavate

virtualenv datalad
 source datalad/bin/activate
conda install -c conda-forge datalad

git config --global --add user.name "marcobarilari"
git config --global --add user.email "marcobarilr@gmail.com"
ssh-keygen -t rsa -b 4096 -C "marcobarilr@gmail.com"
cd ~/.ssh/
ls
cat ~/.ssh/id_rsa.pub
