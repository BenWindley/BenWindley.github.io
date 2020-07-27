---
layout: project
title:  "Marching Cubes"
date:   2020-01-01
author: Ben Windley
categories:
- Project
thumb: Marching Cubes.png
img: Marching Cubes.png
carousel:
- Marching Cubes (1).png
- Marching Cubes (2).png
- Marching Cubes (3).png
- Marching Cubes (4).png
- Marching Cubes (5).png
tagged: Unity, Shaders
published: true
---

### Concept
This was a fun side-project to explore the creation of meshes using the marching cubes algorithm in a compute shader, I originally made it to run on the CPU and then ported it to the GPU to compare the results (with generation being far faster as expected). 

I then created a 3D noise generator alongside a ramp pass to create the mountainous formations, with a few different options to dictate the appearance of the map.

I also added a LOD feature to the generation to allow for the meshes to be rendered at different detail levels the further the camera moved from the map tile segments.

I think that matching cubes could be interesting to implement in a game in the future, for instance a game like Astroneer takes advantage of the wacky generation and tile destructionvof matching cubes in an interesting way.

### Features

- Optimised weighted marching cubes algorithm
- GPU compute shaders
- Terrain generation
- Chunk based tiles
- LOD tiles
- Terrain deformation tools

### Footage

<p style="text-align: center">
<iframe width="560" height="315" src="https://www.youtube.com/embed/an-aR7jjFuI?rel=0&amp;showinfo=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
</p>
