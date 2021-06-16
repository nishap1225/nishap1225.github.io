---
layout: post
title: 9 Men's Morris Optimization
tags: [GamesCrafters, Project]
color: rgb(99, 191, 33)
author: nishap1225
excerpt_separator: <!--more-->
---
### C | Combinatorial Game Theory  
<!--more-->

#### [GamesCrafters Website](http://gamescrafters.berkeley.edu/) | [Github](https://github.com/GamesCrafters/GamesmanClassic/blob/369MMSp2021/src/m369mm.c) | [Writeup](https://docs.google.com/document/d/19buRo8mXmqn_wscRFo-euUD8Gh32t7Xi9Y_ViSdK4wQ/edit?usp=sharing) | [Presentation](https://youtu.be/V1nkqx3hsK4)

Gamescrafters is a research group at UC Berkeley headed by [Professor Garcia](https://www2.eecs.berkeley.edu/Faculty/Homepages/garcia.html) which explores combinatorial game theory. 

[9 Men's Morris](https://en.wikipedia.org/wiki/Nine_men%27s_morris) is an ancient game that was (partially) implemented by GamesCrafters in previous semesters. However, it was unable to be solved fully because it consumed too much time and memory. 

We worked to increase the efficiency of the [retrograde solver](https://github.com/GamesCrafters/GamesmanClassic/blob/369MMSp2021/src/core/solveretrograde.c).  

In order to decrease the time complexity, we implemented symmetries (symmetrcal game positions that are collapsed into a single position). This cut the time to solve by a factor of 16. 

We also implemented the functions `GenerateUndoMoves` and `UndoMove`, which takes a position and generates the possible preceding positions. The standard retrograde solver stores a stack of every move taken; by implementing this method, we can cut down the storage space and compute the backwards stack when it's needed. 