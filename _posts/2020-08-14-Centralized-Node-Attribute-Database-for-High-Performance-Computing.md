---
layout: post
title: Centralized Node Attribute Database for High Performance Computing
tags: [LLNL, Project]
color: rgb(104, 183, 227)
author: nishap1225
excerpt_separator: <!--more-->
---
### Python | mySQL | Bash | Linux
<!--more-->

***Organization***: Lawrence Livermore National Laboratories

#### [Github](https://github.com/LLNL/HPCCEA/tree/master/2020/Genders) | [Presentation](https://drive.google.com/file/d/1wSphZDyJK3cgB54JE0zQWa2RnX2kQsXn/view?usp=sharing)

### Background
The [*genders tool*](https://github.com/chaos/genders) is an open source LLNL tool that stores information about node configurations and is used for cluster configuration management. On each cluster, there exists a file which contains configuration information about a node. The genders file is replicated on each node of the cluster. The genders file can be queried with the command line `nodeattr` tool.

### Motivation
However, there is no way to remotely query the genders file of a node; you have to log into the node and use `nodattr`. So, in order to solve this problem, we created a centralized database which stores all the genders of all the clusters which can be accessed anywhere in the system.

#### Process
- We installed `libgenders`, the python library which functions similarly to `nodeattr`. We changed the configuration to build on python3 instead of python2.
- We then created the structure of the database. We
decided to use mySQL versus a non-relational database like
mongoDB the genders structure was easily visualized as a relational schema. 
{% include aligner.html images="pexels/gender_schema.png" column=3 %}  
- Next, we used the python module to query the local genders file 
and feed it into the database. This was then adapted to be able
to comb through multiple directories.
- Lastly, we created python methods for users to query from the database through the command line. This mimics `nodeattr` except the information is read from the database.
- After the code was complete, we compiled the code into a python package

#### What's Next?
- Ideally, we would want to automatically run the script that updates the database, so that when somebody updates one of the genders files, the database changes as well.

**LLNL-WEB-813516**  
*This work was performed under the auspices of the U.S. Department  of Energy by Lawrence Livermore National Laboratory under Contract  DE-AC52-07NA27344. Lawrence Livermore National Security, LLC*
