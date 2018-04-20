---
layout: post
title: Snake Post Mortem
date: 2017-11-16
author: Ben Windley
categories:
  - Blog
  - Low-Level Programming
img: snake-1200x627.png
thumb: Snake_Thumb.png
---

#### What went well?
- Line of sight worked well with snake, exemplifying the sense of claustrophobia.
- The changing snake corner sprites added a nice feel of fluidity.
- My scene management was easily expandable however having each scene in seperate classes would've made it much cleaner.
- My menu scene was nicely organised.

#### What went wrong?
- A lot of the snake/body interaction could have been handled far better if there were a dedicated snake class that interacted with the head and body
- The corners were heavily unoptimised by changing sprite texture each update, a better method could've been having different sprites that are rendered depending on situation.
- Line of sight was jarring at times, although this is expected.

#### What I learned
- Class inheritance provides a nice default class system.
- Vectors are useful for adjustable arrays of instantiated body parts
- Having more classes dedicated as managers can be useful as an expandable, modular structure.
