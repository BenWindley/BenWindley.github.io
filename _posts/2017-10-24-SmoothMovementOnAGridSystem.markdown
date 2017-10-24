---
layout: post
title:  "Smooth Movement on a Grid System"
date:   2017-10-24
author: Ben Windley
categories: 
- Blog
-Low Level Programming
---

<b>Smooth Movement on a Grid System</b>  <!--more-->

>Smooth Movement on a Grid System
>By checking for intent to change direction each update the class can store the next planned move for the snake. So by updating each tick for movement by a few pixels each time (divisible by the tile size) the snake can check for a change in direction when the next tile is lined up.
>Problems in this system relies on the inconsistencies of update and tick, by spamming input it is possible to change direction multiple times before the next tick is called. To solve this it's as simple as either moving the snake in the direction after it has changed, or having a bool to only take one change of direction per tile.
