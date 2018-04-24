---
layout: post
title: "Chess-Com PostMortem"
date: 2018-04-23
author: Ben Windley
categories:
- Blog
- Low-Level Programming
- Chess-Com
img: Isometric.PNG
thumb: ChessCom_Thumb.png
---
<!--more-->

#### What went well?
- Line of sight was functional and well implimented, it was optimised to only update on certain events such as piece movement and spawning which allowed the maps to be as large as 20x20.
- The isometric grid functioned well and added an intersting style as opposed to the standard grid.
- The particle system helped make the combat more interesting and I'll make sure to add particle systems in all my upcoming games.
- The improved scene manager allowed for more intricate scene manipulation.
- The sprites were easy to draw but had a professional feel to them.

#### What went wrong?
- I feel that the map could have had less piece movement logic.
- I would have liked to have implimented an event system and some logic (such as a move towards function) earlier into the project.

#### What I learned
- Team-based activities are really fun with same-skilled teammates!
- A good concept is one that can be improved easily, but is already fun.
- When working in a team, solid framework makes their job easier far more than it makes your own.