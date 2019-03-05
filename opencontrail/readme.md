# Introduction:

This playbook is used to install the opencontrail+devstack in the remote machine(preferably ubunutu 16.04 - no other linux flavors supported)

This playbook is supported contrail 4.1 and above versions only. also strictly the openstack versions above ocata.

There is strict version compatibility between contrail and openstack, as below

Contrail R4.1
Contrail R5.0


The default openstack version is stable/queens

This playbook builds the devstack in the tmux session of the remote machine. Once it started build the stack the playbook ends. roughly 15-30 mins will take to complete the installation.

User can ssh to the vm, and "tmux attach" to see the build process as a "stack" user.


# How to run:

1. Change the hosts file with the remote machine details.

- remote machine IP (ansible_host=84.39.42.152), 
- username (ansible_user=cloud), 
- password(ansible_ssh_pass=mypassword) if required,  
- ssh key (ssh_private_key_file=/home/suresh/mykey.private) if required.

2. Run the playbook


```
	ansible-playbook -i hosts deploy_contraildevstack.yml -e "branch=stable/queens hostip=10.0.1.4" -vv
```

The default values are ,

branch  is stable/queens,

you can change as below,

 	branch=stable/queens 

 	branch=stable/rocky

	branch=stable/pike

	branch=stable/ocata


hostip is 10.0.1.4

hostip must be changed with the correct private IP of the remote machine.

