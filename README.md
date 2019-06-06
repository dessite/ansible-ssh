# ansible-ssh
Simple script that allows you to quickly SSH into one of your hosts defined in Ansible Inventory file. Usefull fof quick debugging of hosts, witout the need to remember their IP's or credentials.

# Prerequisites
Script assumes that you have `yq` (https://github.com/mikefarah/yq) installed in your path.

# Installation

Clone this repo or [Download latest release](https://github.com/dessite/ansible-ssh/releases/latest) and put the `ansible-ssh` binary into your `$PATH`

# Usage
Script assumes that your Ansible inventory file follows the following structure:

inventory.yml
```
---

  all:
    hosts:
      host1:
        ansible_host: some.ip.addr.ess
        ansible_user: username
        ansible_ssh_private_key_file: "path/to/ssh/key"
      host2:
        ansible_host: some.ip.addr.ess
        ansible_user: username
```

If there is no SSH key configured, it will assume a password will be prompted.

To use:
```
ansible-ssh inventory.yml host1
```
Will use configured SSH key

```
ansible-ssh inventory.yml host2
```
Will prompt for password if host allows

# Author
Bartłomiej Kałuża
