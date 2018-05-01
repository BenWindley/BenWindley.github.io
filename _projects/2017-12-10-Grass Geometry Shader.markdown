---
layout: project
title:  "Grass Geometry Shader"
date:   2017-12-10
author: Ben Windley
categories:
- Project
thumb: Grass_Thumb.png
img: Grass_Thumb.png
carousel:
- Grass.png
- Grass_1.png
- Grass_2.png
- Grass_3.png
- Grass_4.png
tagged: Unity, ShaderLab, OpenGL
published: true
---

### Initial Concept

The task was to create grass in any game engine, I chose unity for it's low level support of geometry shaders. The features that I added to it were:
- Wind animation.
- Spawning via vertex.
- 3D (in a pyramid shape)
- LOD in distance to player, lowering the thickness of the grass in an exponential decay.
- Customisable colour of the grass.
- Noise generated through texture.
- Customisable Length, Width, and Length Randomness.
- Grass interaction with objects.

### Skills used

The required skills to create the shader were:

- Familiarity with ShaderLab and supported OpenGL functions.
- Knowledge of Geometry shaders.
- Knowledge of Fragment shaders.
- Familiarity with script and material interaction.
- Ability to read textures in shaders.
- Knowledge of seeded instancing for each individual vertex.

<p style="text-align: center">
<img src="https://i.gyazo.com/c2b7c3de21cc17ec9d6676ab4560948c.gif" width="500" height="400" />
</p>

#### Links
[Smoother Animation](https://i.gyazo.com/c2b7c3de21cc17ec9d6676ab4560948c)