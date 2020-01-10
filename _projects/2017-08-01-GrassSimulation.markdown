---
layout: project
title:  "Grass Simulation"
date:   2017-08-01
author: Ben Windley
categories:
- Project
thumb: Grass Simulation.png
img: Grass Simulation.png
carousel:
- Grass Simulation (1).PNG
- Grass Simulation (2).PNG
- Grass Simulation (3).PNG
- Grass Simulation (4).PNG
- Grass Simulation (5).PNG
- Grass Simulation (6).PNG
tagged: Unity, Shaders, C#
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

### Footage

<p style="text-align: center">
<img src="https://i.gyazo.com/c2b7c3de21cc17ec9d6676ab4560948c.gif" width="500" height="400" />
</p>