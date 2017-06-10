---
layout: post
title: Games Engine Construction - Final Game Demo
excerpt: "Creating a game engine in C++"
categories: blog
tags: [University, Second Year Projects, Custom Engine, FMOD, C++]
comments: false
share: false
author: dan_bradshaw
---

<iframe src="https://www.youtube.com/embed/VGZ3I_Ky8Ew?ecver=2" width="480" height="360" frameborder="0" style="position:absolute;width:100%;height:100%;left:0" allowfullscreen></iframe>

For my main project this year, I was tasked with creating a 2D engine from scratch. The final product is shown in the video above.

Our lecturer provided an API called HAPI, which exposed a pointer to a frame buffer and an interface to mouse and keyboard input. It also provided a simple audio implementation, which I replace with code for FMOD I created in first year for my last big project. This provided a lot more flexibility and a much larger feature set to work with.

HAPI didn't provide and systems for drawing sprites, and only exposed a way to load images from files. Taking this image data, I created an instanced sprite rendering system to quickly blit the sprites to the screen buffer, including transparent blending and background scrolling.

Taking inspiration from other engines, I implemented a simple component system to build entities from. This was driven by a entity manager which handled the creation and assembly of entities when requested by the gameplay code. It also handled memory allocation and pooling of entities.

The entity manager was also tasked with updating the entities and components attached to those entities, automatically drawing or updating entities as needed.

When working on the audio for this project, I had a lot more time to get stuck into FMOD and make use of all the awesome features it provides. I used dynamic music that progressed as the player progressed through the level, and event systems and RTPC systems.

Overall I thoroughly enjoyed working on this project, and I think that shows in the video!
