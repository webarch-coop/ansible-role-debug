# Debug Ansible variables

[![pipeline status](https://git.coop/webarch/debug/badges/master/pipeline.svg)](https://git.coop/webarch/debug/-/commits/master)

Generate a file per host with as many Ansible variables as possible, this role will, by [default](defaults/main.yml), write variables to a `/root/servername.example.org.yml` file on the server.

| Variable name         | Default value                                      | Comment                                                                 |
|-----------------------|----------------------------------------------------|-------------------------------------------------------------------------|
| `debug_dir`           | `/root`                                            | The directory to write the variable file into                           |
| `debug_file`          | `"{{ inventory_hostname }}.yml"`                   | The file to write the variables into                                    |
| `debug_mode`          | `0640`                                             | The mode of the variable file                                           |
| `debug_owner`         | `root`                                             | The owner of the variable file                                          |
| `debug_group`         | `root`                                             | The group of the variable file                                          |
| `debug_fetch`         | `false`                                            | Set this variable to True to download the results to `debug_local_dir`  |
| `debug_email`         | `false`                                            | Set this variable to True to email the results to `debug_email_address` |
| `debug_email_address` | `root@localhost`                                   | Set this variable to the email address to send results to               |
| `debug_email_subject` | `"Ansible variables for {{ inventory_hostname }}"` | Subject line for the email with the results                             |
| `debug_local_dir`     | `/tmp`                                             | Local directory to downbload the results to                             |

This role requires a recent version of the [community.mysql collection](https://docs.ansible.com/ansible/latest/collections/community/mysql/), in order to generate MariaDB variables, this can be installed into `~/.ansible/collections/ansible_collections` like this:

```bash
ansible-galaxy collection install community.mysql
```

The primary URL of this repo is [`https://git.coop/webarch/debug`](https://git.coop/webarch/debug) and this is where the [release notes](https://git.coop/webarch/debug/-/releases) are, it is also [mirrored to GitHub](https://github.com/webarch-coop/ansible-role-debug) and [available via Ansible Galaxy](https://galaxy.ansible.com/chriscroome/debug).

The [localhost](https://git.coop/webarch/localhost) repo can be used to run this role on the `localhost`.

This role was inspired by [this role](https://github.com/f500/ansible-dumpall).
