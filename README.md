# Ansible Role : Galera Cluster

Ansible Role for Jakarta Project's Cluster DB.
This role is meant to deploy its content on every DB VM.

Requirements
------------

- Debian 9 with minimal install
- SSH installed and sshd.service enabled
- **sudo** package installed
- One bridged interface using the **.20.16-18/26 IP**
- DNS set to 192.168.4.2 in */etc/resolv.conf*
- [User 'Ansible' already configured](https://github.com/nickjj/ansible-user)

**Note** : A template Debian 9 VM **with all requirements satisfied** is available [here](https://192.168.4.16/Equipe_1_Jakarta/debian9-template).

Example Playbook
----------------

```
- name: Deploy galera cluster
  hosts: "{{hosts}}"
  remote_user: ansible
  tasks:
  - import_role:
      name: galera_cluster
      tasks_from: install
```

Author Information
------------------

* **Toréa TESSIER** - <torea.tessier@reseau.eseo.fr> - [Jakarta Project](https://192.168.4.16/Equipe_1_Jakarta/)