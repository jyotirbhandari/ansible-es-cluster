# Ansible-ES-Cluster : Elasticsearch Cluster version 2.3.4

An Ansible Role that installs Cluster of Elasticsearch version 2.3.4 on RHEL/CentOS 7.x
In this playbook, I have used CentOS 7.x vagrant box minimal image and then modified ethernet to bridge mode for a LAN environment.  

# Requirements :

Three minimal instances of RHEL/CentOS 7.x with ssh and internet access.

# Nodes :

Defining all the three nodes ip adddress in the host file.

```
[nodes]
x.x.x.x
y.y.y.y
z.z.z.z
```

# Global Variables :

Defining directories and server host name in group_vars

```
---
server1: server1
server2: server2
server3: server3

masterdir: local
datadir0: data00
datadir1: data01
datadir2: data02
```

# Installation Role Variables :

Defining installation role variable in defaults/main.yml

```
---
es_version: 2.3.4
es_dependencies:
  - java
  - https://download.elastic.co/elasticsearch/release/org/elasticsearch/distribution/rpm/elasticsearch/{{ es_version }}/elasticsearch-{{ es_version }}.rpm
```

# Cluster playbook trigger :

Trigger playbook in all the three servers and get ready to start services.

```
--- 

- hosts: nodes
  remote_user: vagrant
  become: yes
  roles:
    - installation
    - configuration
```

# Start service playbook trigger :

Starting the services in all the three server simulataneously.

```
--- 

- hosts: nodes
  remote_user: vagrant
  become: yes
  roles:
    - service_start
```

# Start service playbook trigger :

Stopping the services in all the three server simulataneously.

```
--- 

- hosts: nodes
  remote_user: vagrant
  become: yes
  roles:
    - service_stop
```
