# ngGirls Development Environment
This Project is for bootstrapping the [ngGirls](http://ng-girls.org/) Development Environment.
It creates a VirtualBox Image via vagrant and provisions all required software into the VM via ansible.

## Requirements
* Vagrant
* ansible >= 2.4
* VirtualBox

### Installation
On Debian/Ubuntu you may just run the following commands:

```sh
apt install vagrant virtualbox pip
pip install ansible
```

### Preparation

```sh
git clone https://github.com/Reservix/ngGirls-DevEnv.git
git submodule update --init --recursive
```

### Usage
#### VirtualBox

```sh
vagrant up
```

#### Ansible
You may want to use the ansible playbook itself to deploy to localhost:

```sh
ansible-playbook -i inventory.yml playbook.yml -l localhost --skip-tags vbox --ask-become-pass
```

Per default sudo is used for privilege escalation.

Please have a look at http://docs.ansible.com/ansible/latest/become.html for available become methods.
