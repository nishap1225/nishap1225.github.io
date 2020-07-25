---
layout: post
title: Centralized Node Attribute Database for High Performance Computing
tags: [Project]
color: rgb(104, 183, 227)
author: nishap1225
excerpt_separator: <!--more-->
---
### Python | mySQL | Bash | Linux
***Organization***: Lawrence Livermore National Laboratory

<!--more-->
### Background
In LLNL high performance computing systems, the [*genders tool*](https://github.com/chaos/genders) stores information about node configurations and is used for cluster configuration management. Each cluster has a *genders* file stored on the local storage system. However, there is no way to access this information without manually entering a node. Furthermore, there is no way to ask queries that concern all the nodes of the system. So, we created a centralized database which stores all of the node attribute information for all of the clusters.

### Process
First, we adjusted the installation files to build [libgenders](https://github.com/chaos/genders/tree/master/src/libgenders) (the python extension for the genders tool) on python3 instead of python2.  
Next, we designed and created the structure of the database using mySQL.
We then wrote scripts to comb through the genders files and populate the database. We adapted the script to comb through the directories of a [cfengine](https://cfengine.com/) repository.   
Finally, we adapted *nodeattr*, the built-in genders query tool, to instead send queries to the database.
