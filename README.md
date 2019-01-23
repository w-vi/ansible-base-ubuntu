# Ansible basic VM setup Ubuntu

This repository contains a playbook for provisioning a base ubuntu machine.

## Features

* User setup
* SSH hardening (no password login, no root login)
* Firewall setup (HTTP/S and SSH allowed)
* Fail2Ban
* Unattened-upgrades
* Mailutils

### Unattened-upgrades

- update not only security patches but general updates
- remove unused automatically installed kernel-related packages
- automatic removal of new unused dependencies after the upgrade
- perodical update every day
- email every time not only on error


## Usage

Configure your [hosts file](https://github.com/w-vi/ansible-base-ubuntu/blob/master/hosts).

```
[production]
192.168.1.1 # example.com
```

and edit [provision.yml](https://github.com/w-vi/ansible-base-ubuntu/blob/master/provision.yml)
to configure the non root user. This will create a new user on the
provisioned server that can be used later.


Execute:

```
$ ansible-playbook provision.yml
```

If the initial root user needs password:

```
$ ansible-playbook provision.yml --ask-pass
```
