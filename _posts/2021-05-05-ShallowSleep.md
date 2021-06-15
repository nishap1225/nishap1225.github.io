---
layout: post
title: ShallowSleep
tags: [Launchpad, Project]
color: rgb(62, 240, 151)
author: nishap1225
excerpt_separator: <!--more-->
---
### PyTorch | Keras | CNNs | LSTMs | React | Javascript
<!--more-->

#### [Github](https://github.com/maxemerling/ShallowSleep) | [Website](https://shallow-sleep.web.app/dashboard/) | [Presentation](https://www.youtube.com/watch?v=LZnCByZwqOw&list=PL0breT9kiPgs3xiXwfHeILRuEj5RqL7y-&index=2&t=12s) 

Current methods to track sleep are either 1) sleep labs or 2) wearable technology. Sleep labs are accurate, but they are also expensive and uncomfortable. Wearable technology is inexpensive, but is inaccurate. 

[This paper](http://sleep.csail.mit.edu/files/rfsleep-paper.pdf) released a few years ago from MIT proposed an alternative solution: determining sleep stages with a ML model using radio signals. Our project was to implement this model, and see what level of accuracy we could achieve.  

We used a three part model: an encoder, label predictor, and source discriminator to construct an adversarial structure.   

Personally, I experimented with implementing a ResNet model to be our encoder. 

I also helped create [the website linked above](https://shallow-sleep.web.app/dashboard/) using React.  

