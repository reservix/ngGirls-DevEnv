# Vagrant for ngGirls Virtualbox Image
This Project is for bootstrapping the ngGirls Development Environment.
It creates a VirtualBox Image via vagrant and provisions all required software into the VM via ansible.

## Requirements
* Vagrant
* ansible >= 2.4
* VirtualBox

### Installation
On Debian/Ubuntu you may just run the following commands:

```sh
apt install vagrant virtualbox
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
You may want to use the ansible playbook itself:
Please have a look at http://docs.ansible.com/ansible/latest/become.html for available become methods.

```sh
ansible-playbook -i inventory playbook.yml -e "ansible_ssh_host=192.168.33.25 ansible_ssh_user=ngGirl" --skip-tags vbox
```
