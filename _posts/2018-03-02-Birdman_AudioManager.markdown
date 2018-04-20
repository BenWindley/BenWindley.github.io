---
layout: post
title: Birdman Audio Manager
date: 2018-03-02
author: Ben Windley
categories:
  - Blog
  - Low-Level Programming
img: birdman.png
thumb: Birdman_Thumb.png
---
## Audio Manager

### Introduction to irrKlang
irrKlang is an audio library for c++ that could be tagged onto ASGE to provide audio.

### Desired Utility
My desired functionality for the audio manager was to provide audio feedback to the player and to relax them with music while they played, therefore I made a class that could be passed as an instance to each scene via shared_ptr (to prevent audio from being cut off on scene change). Therefore I implimented the following:
- Start Background Music
- Stop Background Music
- Play Sound Effect

### Making things easier
Since long strings aren't very elegant when writing code, I kept all audio files in one folder to keep a consistent file path, and then I made the function:
```C++
void AudioManager::setupBackgroundMusic(std::string background_name, bool should_loop)
{
	std::string file = ".\\Resources\\Audio\\" + background_name;
	audio_engine->play2D(file.c_str(), should_loop);
}
```
This is a method to make setting up background music a lot more readable and accessable by others. 