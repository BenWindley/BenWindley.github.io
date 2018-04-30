---
layout: post
title: "Low-Level Particle System Colour Over Time"
date: 2018-04-26
author: Ben Windley
categories:
- Blog
- Low-Level Programming
img: ParticleEffects_Test2.PNG
thumb: ChessCom_Thumb.png
---
<!--more-->

### Additions

I added an ASGE::Colour constructor overload to accept three variables instead of a float array [3], this allows for easier creation of colours without the need to change any existing code that relies on constructing colours through arrays. 

I added colour over time as this is a useful feature in unity, however I would like to add multiple colour changes using vectors to make the flame look more believable, as many flames go from orange, to red, to dark-grey.

For debugging purposes I added a particle counter to see the effects of the particle count on FPS.

#### Colour Change

The code is a simple lerp as always however it is applied to multiple variables. 

```C++
void ColourOverTime::update(float delta_time)
{
	lifetime -= delta_time;
	sprite->colour({ end_colour.r * (max_lifetime - lifetime) + start_colour.r * lifetime,
					 end_colour.g * (max_lifetime - lifetime) + start_colour.g * lifetime,
					 end_colour.b * (max_lifetime - lifetime) + start_colour.b * lifetime, });
}
```

<p style="text-align: center">
<img src="https://gyazo.com/a72b271a26490fa3ba84c846189fb758.gif" width="400" height="400" />
</p>