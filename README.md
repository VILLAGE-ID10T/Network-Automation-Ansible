# Network Automation - Ansible


**Downloads**

[ansible.cfg](https://github.com/jodyjhoughton/Network-Automation/blob/master/ansible.cfg) 

`https://github.com/jodyjhoughton/Network-Automation/blob/master/ansible.cfg` 

[hosts](https://github.com/jodyjhoughton/Network-Automation/blob/master/hosts)

`https://github.com/jodyjhoughton/Network-Automation/blob/master/hosts`

[group_vars](https://github.com/jodyjhoughton/Network-Automation/tree/master/group_vars)

`https://github.com/jodyjhoughton/Network-Automation/tree/master/group_vars`

**Update Hosts**

`apt -y update && apt -y upgrade`

**Cleanup Python**

> consoldate python to latest

`Update-alternatives --config python`

> check version

python --version

**Check installed versions**

`which python && ls -la /etc/python`

**Check install paths and Change or add aliases for new version**

`/etc/python*`

```shell
echo <<EOF> $HOME/.bashrc
alias py=python3.6
alias python=python3.6
alias pip=pip3
<EOF>
```

>validate, both should should show current versions

`
which py
which pip
`

**upgrade pip**

`pip install --upgrade pip`

**Install Python Virtualenv & Python Virtualenv Wrapper**

`pip install virtualenv && pip install virtualenvwrapper`

Validate
`which virtualenv`

**Add Virtualenv Wrapper Variables to .bashrc**

```shell
cd ~
set .bashrc variables
echo <<EOF> .bash_profile
Press shift+I to add the next two lines to your .bash_profile
export WORKON_HOME=~/.virtualenvs
source /usr/local/bin/virtualenvwrapper.sh
load virtualenvwrapper for python (after custom PATHs)
venvwrap="virtualenvwrapper.sh"
/usr/bin/which -s $venvwrap
if [ $? -eq 0 ]; then
venvwrap=`/usr/bin/which $venvwrap`
source $venvwrap
fi
<EOF>
```

**Choose your .bashrc file as 'source'**

`source .bashrc`

**Create virtualenv directory, and cd to it**
> This will be where all the virtualenv's live
`cd .virtualenvs`

**Create the virtualenv you want to start working in**
**once this is created.  Use 'deactivate' to exit and 'workon' to activate**

```shell
mkvirtualenv labv2
deactivate labv2
workon labv2
```

**validate path**

`pwd && ls -la`

**validate pip**

(labv2) root@ansible2020:/ which pip && which python && which ansible
> /root/.virtualenvs/labv2/bin/pip

> /root/.virtualenvs/labv2/bin/python

> /root/.virtualenvs/labv2/bin/ansible


**validate python**
(labv2) root@ansible2020:/pip --version && python --version && ansible --version


```python
pip 20.2.2 from /root/.virtualenvs/labv2/lib/python3.6/site-packages/pip (python 3.6)
Python 3.6.9
ansible 2.9.12
  config file = /root/.virtualenvs/labv2/ansible.cfg
  configured module search path = ['/root/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /root/.virtualenvs/labv2/lib/python3.6/site-packages/ansible
  executable location = /root/.virtualenvs/labv2/bin/ansible
  python version = 3.6.9 (default, Jul 17 2020, 12:50:27) [GCC 8.4.0]
```

**Install ansible**

```shell
apt -y update
apt -y install software-properties-common
apt-add-repository ppa:ansible/ansible
apt -y update
apt -y install ansible
sudo apt install build-essential libssl-dev libffi-dev python-dev
git clone https://github.com/ansible/ansible.git
```
