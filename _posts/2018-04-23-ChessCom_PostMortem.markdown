---
layout: post
title: "Simple Animations to Add Magic"
date: 2018-04-15
author: Ben Windley
categories:
- Blog
- Low-Level Programming
- Chess-Com
img: Isometric.PNG
thumb: ChessCom_Thumb.png
---
<!--more-->

### Simple Lerp (Linear Interpolation) Animation

<p style="text-align: center"> ![Alt Text](https://gyazo.com/e6adca221b97758cfb50328c11be53eb.gif)</p>

When adding animations to things in code, a lerp animation is the easiest of them all, by taking two points and calculating the average point of the two you can easily add a little magic to your game. All you need to remember is that this needs to be isolated to game-side mechanics otherwise you can expect <b>undefined behaviour.</b>

#### Psuedocode
``` C++
z_position = 0.9f * z_position + 0.1f * z_target;
```

### Simple Move-Towards Animation

<p style="text-align: center"> ![](https://gyazo.com/36491785d46c1560e7dc0b72c8c83cc4.gif)</p>

Although the smooth end on the Lerp is pretty satisfying, a constant speed can also be desired as it allows for movement that can be predicted. 

#### Psuedocode
``` C++
if (magnitude <= max_movement)
{
    z_position = z_target;
}
else
{
	z_position += sign(z_target - z_position) * move_speed;
}
```

### Combination of both

<p style="text-align: center"> ![Alt Text](https://gyazo.com/8d0d4794f555be530c8c4eaadf027435.gif)</p>

To give weight to the pieces - a slow rise and a fast fall makes the piece feel heavier.