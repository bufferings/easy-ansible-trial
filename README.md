# get-started-with-ansible

Getting started with Ansible.

This script uses Vagrant + Ansible Local Provisioner.

So you don't need to install Ansible to your Vagrant host:)

## Preparation

Please install Virtual Box and Vagrant.

### Virtual Box

https://www.virtualbox.org/wiki/Downloads

I used Virtual Box 5.0.14 .

### Vagrant

https://www.vagrantup.com/downloads.html

Vagrant version should be > 1.8.1, because this script use "Ansible Local Provisioner"

## Hello Ansible!

```
# It takes long time for the first time to download Box image.
vagrant up

# This is needed for the issue ( https://github.com/mitchellh/vagrant/issues/6793 )
# I'm waiting for Vagrant 1.8.2 release.
vagrant provision
```

Then you will see
```
PLAY ***************************************************************************

TASK [setup] *******************************************************************
ok: [default]

TASK [debug] *******************************************************************
ok: [default] => {
    "msg": "Hello world!"
}

PLAY RECAP *********************************************************************
default                    : ok=2    changed=0    unreachable=0    failed=0
```

```


