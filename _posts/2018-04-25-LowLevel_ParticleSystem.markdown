---
layout: post
title: "Low-Level Particle System"
date: 2018-04-25
author: Ben Windley
categories:
- Blog
- Low-Level Programming
img: ParticleEffects_Test1.PNG
thumb: ChessCom_Thumb.png
---
<!--more-->

### Planned Model
As always, the best way to create a system is to plan out the desired uses of said system. Firstly I must disclaim that the model I based it after is Unity's particle system. However, the implimentation was desired to cover the following: 
- Little interaction between scene and system.
- Scalable with the increasing number of particle types.
- Each particle is to update and render in identical ways, with specifics such as Opacity over time, Size over time, and Colour over time only included as components that serve small purpose in how the sprite is manipulated.
- Each particle should have it's own position, velocity, and accelaration.
- Each particle has a shared pointer to world offset, which allows the particles to inhabit a world-space without being constantly updated.
- Sprite Animation through multiple methods such as sprite cycling and sprite progression over lieftime

#### Over Time
The defininig parts of a particle are it's components, and having multiple components that can be attached to a particle allows for interesting manipulation. The primary method I used to have a value move towards another over lifetime was through a lerp.
``` C++
void OpacityOverTime::update(float delta_time)
{
	lifetime -= delta_time;
	sprite->opacity(end_opacity * (max_lifetime - lifetime) + 
                    start_opacity * lifetime);
}
```
This way opacity will move towards end_opacity over the sprite's lifetime! However this is very limited in how it models change over time. In the future I might make a model for exponential decay, however for now I want to focus on adding more components.

<p style="text-align: center">
<img src="https://gyazo.com/78fb8db784bb95f96d4c88d4354ed4da.gif" width="400" height="400" />
</p>