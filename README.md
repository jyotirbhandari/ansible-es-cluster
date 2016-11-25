# Ansible-ES-Cluster : Elasticsearch Cluster version 2.3.4

An Ansible Role that installs Cluster of Elasticsearch version 2.3.4 on RHEL/CentOS 7.x
In this playbook, I have used CentOS 7.x vagrant box minimal image and then modified ethernet to bridge mode for a LAN environment.  

# Requirements :

Three minimal instances of RHEL/CentOS 7.x with ssh and internet access.

# Nodes :

Defining all the three nodes in the host file.

```
[nodes]
192.168.100.21
192.168.100.22
192.168.100.23
```
