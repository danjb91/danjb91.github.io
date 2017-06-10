---
layout: post
title: Final Year Project - Music Visualisation Demo
excerpt: "Using an OpenCL powered particle system to simulate hundreds of thousands of particles!"
categories: blog
tags: [University, Final Year Project, C++, GPU Particles, OpenCL]
comments: false
share: false
author: dan_bradshaw
---

# Coming up with the idea

I had a number of ideas I wanted to work on for my final year project, but over my second year I had a growing interest of using the GPU to offload computation from the CPU.

Now that I'm in my final year at University, I have to select which a final year project to work on. Over the summer I had a number of ideas for this, but I've finally narrowed this down to working with GPU compute.

Since the beginning of second year I had a great interest in using the GPU to offload computation from the CPU. This has many uses, but I decided to focus on particle simulation. The huge parallel processing power of GPUs is perfectly suited to running particle simulations, and allows for a huge increase in the number of particles we can simulate at once.

By creating an API to easily offload this particle simulation for users, I hope to make integrating GPU based particle simulation into games and other applications easier and much more flexible.

# Selecting the graphics API to use

One of the most important parts to get right for this project is selecting which API to use when interfacing with the GPU. There's a number of options available as listed below:

#### Compute Shaders

The newest versions of DirectX and OpenGL provide the user with the use of compute shaders. These more general purpose shaders allow the programmer to define more complex tasks to run on arbitrary data, rather than the traditional and rather limited vertex/geometry/pixel shader variants.

Since this system will be targeting as many platforms as possible, OpenGL is the main option here as it supports all major platforms such as Windows, Mac and Linux.

#### CUDA

nVidia provides an amazing GPU compute platform called CUDA. The platform provides a great set of APIs and makes it very easy to get set up and running code on a GPU. Unfortunately, this is only available on nVidia GPUs at the moment, which rules out all users using AMD hardware.

#### OpenCL

OpenCL is an opensource cross plaform alternative to CUDA.


<iframe src="https://www.youtube.com/embed/oXoq9hyEH8U?ecver=2" width="640" height="360" frameborder="0" style="position:absolute;width:100%;height:100%;left:0" allowfullscreen></iframe>
