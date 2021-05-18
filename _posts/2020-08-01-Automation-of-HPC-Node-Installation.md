---
layout: post
title: Automation of HPC Node Installation
tags: [LLNL, Project]
color: rgb(35, 80, 148)
author: nishap1225
excerpt_separator: <!--more-->
---
### Ansible | Bash | Linux
<!--more-->

***Organization***: Lawrence Livermore National Laboratories

#### [Github](https://github.com/LLNL/HPCCEA/tree/master/2020/ClusterBuild)

In our first few weeks of the internship, we installed the management and compute nodes of a cluster entirely manually. After that laborious process, we decided we needed to create a faster way of doing this - automating the process.

#### Scripts I Worked On
- Creating Users
    - [Creating users on the management node](https://github.com/LLNL/HPCCEA/blob/master/2020/ClusterBuild/user_setup_mgmt.yml)
    - [Creating users on the localhost](https://github.com/LLNL/HPCCEA/blob/master/2020/ClusterBuild/user_setup_host.yml)
    - [Combining the two](https://github.com/LLNL/HPCCEA/blob/master/2020/ClusterBuild/create-users.sh)
- [Rebooting the node after installation](https://github.com/LLNL/HPCCEA/blob/master/2020/ClusterBuild/reboot.yml)

### Creating Users
The first task I took care of was creating a user account on all of the compute nodes, as well as on the management node. I used ansible to create a user (with a passed in username) with a password (which is passed in as well). Next, I set up sudo access for the account by editing the */etc/sudoers* file. This was replicated on all of the compute nodes, as well as the management node.  

The final task was to setup the password-less ssh capabilities between the nodes. I created the ./ssh directory if it wasn't already set up. Then, I created a RSA key-pair for the account and copied it into the *./ssh/authorized_keys* file of each node.

Finally, we created a bash script that took arguments and called the appropriate ansible playbooks.

### Rebooting the Node
After a node is completely installed and configured, it's important to reboot the node locally to be make sure the configuration changes are correct. I did this with an ansible playbook by calling on the *reboot* module. Once the computer had rebooted, I wrote a simple test to check if the node had rebooted successfully.

**LLNL-WEB-813517**   
*This work was performed under the auspices of the U.S. Department  of Energy by Lawrence Livermore National Laboratory under Contract  DE-AC52-07NA27344. Lawrence Livermore National Security, LLC*
