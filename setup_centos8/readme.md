# Initial Server Setup on CentOS 8

This playbook will execute a initial server setup for CentOS 8 systems.
A number of containers will be created with the options specified in the `vars/default.yml` variable file.

## Settings

- `create_user`: the name of the remote sudo user to create.
- `copy_local_key`: path to a local SSH public key that will be copied as authorized key for the new user. By default, it copies the key from the current system user running Ansible.
- `sys_packages`: array with list of packages that should be installed.


## Running this Playbook

Quick Steps:

### 1. Obtain the playbook
```shell
git clone https://github.com/hetitate/ansible-playbooks.git
cd ansible-playbooks/setup_centos8
```

### 2. Customize Options

```shell
nano vars/default.yml
```

```yml
#vars/default.yml
---
create_user: centos
copy_local_key: "{{ lookup('file', lookup('env','HOME') + '/.ssh/id_ed25519.pub') }}"
sys_packages: [ 'curl', 'vim', 'git', 'epel-release', 'openvpn', 'nano', 'traceroute', 'htop', 'rsync' ]
```

### 3. Run the Playbook

```command
ansible-playbook -l [target] -i [inventory file] -u [remote user] playbook.yml
```

### 4. Example

```command
ansible-playbook -l server1 -i hosts -u root setup_centos8/playbook.yml
```
