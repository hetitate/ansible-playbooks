# Docker and Docker Compose on CentOS 8

This playbook will install Docker and Docker Compose on CentOS 8 machine.
A number of containers will be created with the options specified in the `vars/default.yml` variable file.

## Settings

- `user`: Specify which user add to the 'docker' group.


## Running this Playbook

Quick Steps:

### 1. Obtain the playbook
```shell
git clone https://github.com/hetitate/ansible-playbooks.git
cd ansible-playbooks/docker_centos8
```

### 2. Customize Options

```shell
nano vars/default.yml
```

```yml
#vars/default.yml
---
user: centos
```

### 3. Run the Playbook

```command
ansible-playbook -l [target] -i [inventory file] -u [remote user] playbook.yml
```

### 4. Example

```command
ansible-playbook -l server1 -i hosts -u centos docker_centos8/playbook.yml
```