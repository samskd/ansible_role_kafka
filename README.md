kafka
=========
This is the kafka role for ansible.

Dependencies
------------
- java
- zookeeper

Usage
-----

```
#requirements.yml
---
- src: git+ssh://git@github.com:samskd/ansible_role_kafka.git
  name: kafka

#/bin/bash
> ansible-galaxy install -r requirements.yml

#playbook.yml
---
- hosts: all
  become: true
  become_method: sudo
  roles:
    - kafka

#/bin/bash
> ansible-playbook -i inventory playbook.yml --tags "deploy,restart"

Available tags:
deploy - Install and configures kafka server
restart - Restarts kafka server
configure - Configures kafka server
stop - Stops kafka server
```
