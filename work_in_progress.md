# **Readme file to update on the workin in progress state of the art of the machine**

This readme has the purpose to share at which stage is a specific action (e.g., software installation, maintenance, etc.).

Since we are facing several problems in setting up **the MONSTER**, it might be good to save _'check points'_ of each specific process going on in several days ~~aka trial and error~~.

## EasyBuild installation 

### 10-05-2019, Marco

Following this [vide demo](https://easybuild.readthedocs.io/en/latest/demos/bootstrapping.html#demo-bootstrapping):

1. installed *pip install* from ([here](https://pip.pypa.io/en/stable/installing/))

2. *step 1* installs by default `setuptools` then upgraded manually to the latest version via `sudo pip install setuptools --upgrade`

3. installed recuired Python packaged (see [here](https://easybuild.readthedocs.io/en/latest/Installation.html#required-python-packages))
* `vsc-base` via `sudo pip install vsc-base`
* `vsc-install` via `sudo pip install vsc-install`

4. trying to install `Lmod` as nodule tools, see [here - github repo](https://github.com/TACC/Lmod ) and [here - dev site?](https://www.tacc.utexas.edu/research-development/tacc-projects/lmod)                               

## Computer frozen & graphic problem 

### 09-05-2019, Remi & Marco

1. NVIDIA graphic card driver installation following this [blog post](https://www.cyberciti.biz/faq/how-to-install-nvidia-driver-on-centos-7-linux/)

2. Cross your fingers and hope the issue is solved
