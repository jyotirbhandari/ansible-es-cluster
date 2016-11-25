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

# Global Variable :

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

