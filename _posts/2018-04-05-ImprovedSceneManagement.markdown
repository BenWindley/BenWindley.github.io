---
layout: post
title: "Improved Scene Management"
date: 2018-04-05
author: Ben Windley
categories:
- Blog
- Low-Level Programming
img: FrameworkLayout.jpg
thumb: c_thumb.jpg
---

## Previous Model

The functionality of the previous scene manager consisted of a switch statement that directed the game to update the current scene. The current scene was stored in a polymorphic scene class, the polymorphic traits were update, init, and render, all of which form the foundations of the scene manager.

To change the scene the update function returned an enum to signify which scene to change to.

Inside the header:
```C++
BaseScene* current_scene = nullptr;
```
Inside the Init function:
```C++
current_scene = new FirstScene;
current_scene->init();
```
Inside the update function:
```C++
switch (current_scene->update((float) ms.delta_time.count(), renderer.get()))
{
	case SceneEnum::GAME:
	{
		delete current_scene;
		current_scene = new SecondScene;
		current_scene->init();
		break;
	}
}
```
Inside the render function:
```C++
current_scene->update(renderer.get());
```
The problems I discovered using this system was the limit to flexibility of the scenes, as each time a scene were to be changed the scene would have to be deleted.

## New Model

The new scene manager I wanted to create should have the following traits:
- Multiple scenes stored in a vector
- Different scene change types, to replace, add or remove scenes.

Therefore a simple method to pass multiple things back to the scene manager is a struct containing multiple enums for change type, next scene (and for the future - scene transition type).
```C++
enum ChangeType
{
	REPLACE,
	REPLACE_ALL,
	REMOVE,
	ADD,
	EXIT,
	NONE
};

enum TransitionType
{
	QUICK_CHANGE
};

enum SceneEnum
{
	MENU,
	GAME,
	NONE
};

struct SceneChange
{
	ChangeType change_type = ChangeType::NONE;
	TransitionType transition = TransitionType::QUICK_CHANGE;
	SceneEnum scene = SceneEnum::NONE;
};
```
This allows for an easy but elegant solution to create a scene manager akin to cocos however a more elegant solution to adding more scenes to the scene manager would improve the model greatly.