---
layout: post
title: "Low-Level Particle System Colour Lerp"
date: 2018-04-27
author: Ben Windley
categories:
- Blog
- Low-Level Programming
img: ParticleEffects_Test3.PNG
thumb: ChessCom_Thumb.png
---
<!--more-->

### Additions

In this update I added support for multiple colours, where it lerps through them in a way similar to how unity makes blend trees. Currently they cannot have different points where it changes, however I might add that in the future. 
I also added particle pooling to increase optimisation, this might cause some issues in the future, however, with how I handle the pools of particles. 

#### How it works

Since this is the smartest thing about the particle system (so far) I won't post it in it's entirity, but the general process is:

```C++
int index = life_percentage_rounded_down * colour_size;
float progress_in_index = life_percentage * colour_size - index;

sprite->setColours(colours.at(index) * (1 - progress_in_index) + colourse.at(index + 1) * progress_in_index);
```