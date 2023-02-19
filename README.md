# ansible

Kick-start a new environment setup.

## Backup or Restore Proxmox VM

### Create a VM backup

`101` - is the VM ID.

```sh
cd /var/lib/vz/dump
vzdump 101
```

### Restore a VM backup

`102` - is the new VM ID.

```sh
cd /var/lib/vz/dump 
qmrestore vzdump-qemu-101-YYYY_MM_DD_HH_MM_SS.vma 102
```

## Kick-start a base setup

### Install ansible

```sh
sudo apt-add-repository -y ppa:ansible/ansible
sudo apt-get update -y
sudo apt-get install -y curl git software-properties-common ansible
```

### Pull ansible playbook and execute on a local host

```sh
ansible-pull -U https://github.com/ppetroskevicius/ansible.git --ask-become-pass --ask-vault-pass
```

or

```sh
ansible-playbook -t dotfiles local.yml --ask-become-pass --ask-vault-pass
```
