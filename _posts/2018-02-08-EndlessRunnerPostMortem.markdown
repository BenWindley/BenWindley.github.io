---
layout: post
title: Endless Runner Post-Mortem
date: 2018-02-08
author: Ben Windley
categories:
  - Blog
  - Low-Level Programming
img: Endless Runner.PNG
thumb: Endless Runner(2).PNG
---

#### What went well?
- Due to the hindsight into ASGE's workings it was far easier to create a framework.
- The scene manager that I created early on, with the focus of scalability, set the modular foundations for the Game, Menu and Name Input Scenes.
 
#### What went wrong?
- Due to the reinstantiations of obstacles clashing with the render system (which could've been easily avoided with an obstacle pool) this meant the obstacles had to come in waves instead of a steady stream of obstacles that was intended.
- The input handler was less elegant since it was handled outside the scene classes.

#### What I learned
- I learned that the input handler callbacks can be added to classes.
- That a good scene manager allows for far easier coding.
- Modularising certain aspects of the project is useful for future projects.