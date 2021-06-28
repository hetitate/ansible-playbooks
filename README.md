# Ansible Playbooks

A collection of minimalist Ansible playbooks for automating server setups.

- [Initial Server Setup for CentOS 8](https://github.com/hetitate/ansible-playbooks/tree/master/setup_centos8) *
- [Docker and Docker Compose on CentOS 8](https://github.com/hetitate/ansible-playbooks/tree/master/docker_centos8)

_\*the Initial Server Setup should be your starting point for fresh servers._

## Playbook Structure

The playbooks contained in this repository were created for educational purposes, and should serve as a base for you to create your own playbooks and roles.

For instance, this is how the `setup_centos8` playbook is structured:

```
setup_centos8
├── vars
│   └── default.yml
├── playbook.yml
└── readme.md
```


- `vars/`: directory to save variable files. A `default.yml` var file is included by default.
- `playbook.yml`: the playbook file.
- `readme.md`: instructions related to this playbook.

### Connection Test

From your local machine or Ansible control node, run:

```command
ansible all -m ping -u remote_user
```

If you're able to get a "pong" reply back from your node(s), your setup works as expected and you'll be able to run both ad-hoc commands and playbooks on your nodes, using Ansible.

