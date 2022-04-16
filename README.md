# Debug Ansible variables

Generate a file per host with as many Ansible variables as possible, this role will, by [default](defaults/main), write variables to a `/root/servername.example.org.yml` file on the server.

This role requires a recent version of the [community.mysql collection](https://docs.ansible.com/ansible/latest/collections/community/mysql/), in order to generate MariaDB variables, this can be installed into `~/.ansible/collections/ansible_collections` like this:

```bash
ansible-galaxy collection install community.mysql
```


Inspired by [this role](https://github.com/f500/ansible-dumpall).
