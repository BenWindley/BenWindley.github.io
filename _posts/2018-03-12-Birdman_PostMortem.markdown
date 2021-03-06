---
layout: post
title: Birdman Post-Mortem
date: 2018-03-12
author: Ben Windley
categories:
  - Blog
  - Low-Level Programming
  - Birdman
img: birdman.png
thumb: Birdman_Thumb.png
---
<!--more-->
#### What went well?
- The art and music gave a polished feel to the game.
- File reading allowed for easy interaction and easy changes without hard-coding.
- The concept was fun and many playtesters enjoys replaying to try to get a perfect ending, which many achieved after a few tries.
- Having the input handler inside the scene classes allowed for a neat system.
 
#### What went wrong?
- The scene manager wasn't stored in it's own class, which made transitions ridgid.
- Functions and variables didn't follow const-correctness.
- The game scene didn't give enough feedback to the player when choosing options.

#### What I learned
- More advanced file reading.
- How to initialise input handlers inside seperate classes.
- Audio is an important tool for feedback to the player.
- Playtesting is important for creating a player-friendly experience.
