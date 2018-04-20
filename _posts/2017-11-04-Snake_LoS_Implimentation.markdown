---
layout: post
title: Line of Sight Implimentation
date: 2017-11-04
author: Ben Windley
categories:
  - Blog
  - Low-Level Programming
img: Caves-of-Qud-Mobile.jpg
thumb: Snake_Thumb.png
---
<!--more-->
#### Planning
My initial thought was to draw a line between each grid space and the head position of the snake, therefore <b>Bresenham's algorithm</b> of the generation of pixel-based lines helped this.

#### Bresenham's Algorithm
```C++
void plotLine(int x0, int y0, int x1, int y1)
{
   int dx =  abs(x1-x0), sx = x0<x1 ? 1 : -1;
   int dy = -abs(y1-y0), sy = y0<y1 ? 1 : -1; 
   int err = dx+dy, e2; 
 
   for(;;){  /* loop */
      setPixel(x0,y0);
      if (x0==x1 && y0==y1) break;
      e2 = 2*err;
      if (e2 >= dy) { err += dy; x0 += sx; }
      if (e2 <= dx) { err += dx; y0 += sy; }
   }
}
```
Modifying the algorithm allows the ability to check <b>point by point</b> if a grid space is occupied.

#### Process
By starting with the default of all spaces not being visible you can draw lines from the snake to check if any opaque materials are in the way, as each point is checked, each can be marked as visible. Since a visible tile will definitely be visible by the snake those don't need to be checked twice.
