HA K3S
=========

Install HA K3S cluster with embeded Etcd 

Requirements
------------

* At least 3 and odd number of master nodes
* 1 or more worker nodes
* Nodes need to have memory cgroup enabled. If nodes are Raspberry Pi, the role will do that for you
* A fixed registration address that loadbalances to master nodes, more detail at https://docs.k3s.io/datastore/ha#3-configure-the-fixed-registration-address

Role Variables
--------------

Following variables must be passed to the role for the fixed registration address and its dns name:
* ```k3s_master_lb_ip_address```
* ```k3s_master_lb_dns_name``` 


Example Playbook
----------------

    - hosts: servers
      roles:
         - role: krittin.ha-k3s
           var:
             k3s_master_lb_ip_address: lb.my-k3s-master
             k3s_master_lb_dns_name: 10.10.1.1
