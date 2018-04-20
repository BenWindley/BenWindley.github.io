---
layout: post
title: "Checking Isometric Point Collision"
date: 2018-04-15
author: Ben Windley
categories:
- Blog
- Low-Level Programming
img: Isometric.PNG
thumb: c_thumb.jpg
---

### Theory

In mathematics, to check if a point is within the constraints of any area, you can check the lines that create the collider and check if the point is above the top colliders, and below the bottom colliders. 

#### Method

This series of checks allows for a cheap and efficient way to check if you click on an isometric tile, the only pre-requisite is knowledge of how to make the collision area by calculating the lines using two co-ordinates on the line.

#### Psuedocode

```C++
if(point.x * line_gradient + line_constant < point.y)
{
    point is above line
}
```
By doing multiple of these checks and returning false if it is outside any of constraints.