# **Work In Progress readme to update on the state of the art of the machine**

This readme has the purpose to share at which stage is a specific action (e.g., software installation, maintenance, etc.).

Since we are facing several problems in setting up **the Monster**, it might be good to save _'check points'_ of each specific process going on in several days ~~aka trial and error~~.

## * EasyBuild installation 

### 10-05-2019, Marco

Following this [demo video](https://easybuild.readthedocs.io/en/latest/demos/bootstrapping.html#demo-bootstrapping):

1. installed *pip install* ([from here](https://pip.pypa.io/en/stable/installing/))

2. *step 1* installs by default `setuptools` then upgraded manually to the latest version via `sudo pip install setuptools --upgrade`

3. installed recuired Python packaged (see [here](https://easybuild.readthedocs.io/en/latest/Installation.html#required-python-packages))
* `vsc-base` via `sudo pip install vsc-base`
* `vsc-install` via `sudo pip install vsc-install`

