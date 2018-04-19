---
layout: post
title: Endless Runner Polymorphic Scene Manager
date: 2018-02-01
author: Ben Windley
categories:
  - Blog
  - Low-Level Programming
img: Endless Runner(2).PNG
thumb: Endless Runner(2).PNG
---

### Desired Usage
- Ability to have one active scene and interchange it with different scene classes.
- Make code cleaner and isolate code that doesn't require dependancy on each other.
- Make use of polymorphism and pointers.

#### Polymorphism
```C++
Scene* current_scene = nullptr;

current_scene = new MenuScene();

if (!current_scene->init(renderer.get()))
{
    return false;
}
```
As long as the functions called from current_scene are the inherited functions of Scene, MenuScene can override the functions as it wishes.
