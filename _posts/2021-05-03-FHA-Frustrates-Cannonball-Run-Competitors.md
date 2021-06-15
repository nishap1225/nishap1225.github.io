---
layout: post
title: FHA Frustrates Cannonball Run Challengers!
tags: [CS 170, Project]
color: rgb(30, 168, 72)
author: nishap1225
excerpt_separator: <!--more-->
---
### Python | Algorithmic Optimization | Randomized Algorithms | Heuristic Algorithms | Simulated Annealing 
<!--more-->

[***Specification***](https://cs170.org/assets/pdf/project_spec.pdf)

**The Problem**: Given a wheighted, undirected, graph, a source and destination vertex, and two integer budgets, maximize the distance between the source and destination by removing edges and vertices as the budget allows. 

In order to solve this problem (without any parallelization/machine optimization), we tried a variety of algorithm optimizations. 

What was most successful was the heuristic methods. By creating a "score" for each vertex/edge, or removing vertices/edges in a somewhat advantageous order, we were able to increase the distance between the source and destination significantly. 

We also attempted randomization and simulated annealing, but these approaches were less successful because we weren't able to fine tune them to work effectively. 

