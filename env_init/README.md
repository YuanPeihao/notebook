# DevEnvSetup
I just cannot help myself to record my mem here 

# Create Dev Dir and Setup GIT

```
root@vnfm-dev:/home/sqa/pyuan# mkdir dev
root@vnfm-dev:/home/sqa/pyuan# cd dev
root@vnfm-dev:/home/sqa/pyuan/dev# ls
root@vnfm-dev:/home/sqa/pyuan/dev# git init
Initialized empty Git repository in /home/sqa/pyuan/dev/.git/
root@vnfm-dev:/home/sqa/pyuan/dev# git config --local user.name "username"
root@vnfm-dev:/home/sqa/pyuan/dev# git config --local user.email "email"
root@vnfm-dev:/home/sqa/pyuan/dev# ssh-keygen -t rsa -C email
root@vnfm-dev:/home/sqa/pyuan/dev# vim ~/.ssh/
authorized_keys  id_rsa           id_rsa.pub
root@vnfm-dev:/home/sqa/pyuan/dev# vim ~/.ssh/id_rsa.pub
```

# Clone remote master

```
root@vnfm-dev:/home/sqa/pyuan/dev# git clone SSHURL
root@vnfm-dev:/home/sqa/pyuan/dev# ls
femtocoreMOP
root@vnfm-dev:/home/sqa/pyuan/dev# cd femtocoreMOP/
```

# Setup virtualvenv

```
root@vnfm-dev:/home/sqa/pyuan/dev/femtocoreMOP# virtualenv --version
15.0.1
root@vnfm-dev:/home/sqa/pyuan/dev/femtocoreMOP# virtualenv --python=/usr/bin/python3 venv
Already using interpreter /usr/bin/python3
Using base prefix '/usr'
New python executable in /home/sqa/pyuan/dev/femtocoreMOP/venv/bin/python3
Also creating executable in /home/sqa/pyuan/dev/femtocoreMOP/venv/bin/python
Installing setuptools < 51.3, pkg_resources, pip < 21, wheel...done.
root@vnfm-dev:/home/sqa/pyuan/dev/femtocoreMOP# python --version
Python 2.7.12
root@vnfm-dev:/home/sqa/pyuan/dev/femtocoreMOP# source venv/bin/activate
(venv) root@vnfm-dev:/home/sqa/pyuan/dev/femtocoreMOP# python --version
Python 3.5.2
```

# Setup venv (supported by Python 3.3+)

```
root@Simulator118:/home/pyuan/femtocoreMOP# python3 -m venv ./venv
root@Simulator118:/home/pyuan/femtocoreMOP# source venv/bin/activate
(venv) root@Simulator118:/home/pyuan/femtocoreMOP# python --version                
Python 3.8.6 
```

# Install dependencies in pre-downloaded wheels package

```
(venv) root@Simulator118:/home/pyuan/femtocoreMOP/python_module_packages# pip install --no-index --find-links=./ -r requirements.txt  --ignore-installed
```

# Install dependencies online 

```
(venv) root@vnfm-dev:/home/sqa/pyuan/dev/femtocoreMOP# pip --version
pip 20.3.4 from /home/sqa/pyuan/dev/femtocoreMOP/venv/lib/python3.5/site-packages/pip (python 3.5)
(venv) root@vnfm-dev:/home/sqa/pyuan/dev/femtocoreMOP# pip install -r requirements.txt
```

# Customize VIM

```
(venv) root@Simulator118:/home/pyuan# vim .vimrc # create new vim config file
(venv) root@Simulator118:/home/pyuan# vim fis_sample.yaml # open the file to edit
:source /home/pyuan/.vimrc # apply the new config  
```
