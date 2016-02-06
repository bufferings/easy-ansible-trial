# try-ansible

Vagrant script to try Ansible.

This script uses Vagrant with Ansible Local Provisioner.

So you don't need to install Ansible to your Vagrant host:)

## Preparation

Please install Virtual Box and Vagrant.

### Virtual Box

https://www.virtualbox.org/wiki/Downloads

I used Virtual Box 5.0.14

### Vagrant

https://www.vagrantup.com/downloads.html

Vagrant version should be > 1.8.1, because this script use "Ansible Local Provisioner" which is introduced from 1.8

## Hello Ansible!

```
vagrant up
```

It takes long time for the first time to download Box and create VM.
Then you will see following error message.

```
default: Installing Ansible...
The Ansible software could not be found! Please verify
that Ansible is correctly installed on your guest system.

If you haven't installed Ansible yet, please install Ansible
on your Vagrant basebox, or enable the automated setup with the
`install` option of this provisioner. Please check
https://docs.vagrantup.com/v2/provisioning/ansible_local.html
for more information.
```

This is because of the issue ( https://github.com/mitchellh/vagrant/issues/6793 )
which is caused by Vagrant 1.8.1 & Ansible 2.0. I'm looking forward to 1.8.2 release.

There's a workaround introduced in the issue discussion.
And this repository's Vagrantfile includes it.

So please provision again.

```
vagrant provision
```

Then you will see Ansible working!

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

Now ready for trying Ansible. Let's enjoy!
