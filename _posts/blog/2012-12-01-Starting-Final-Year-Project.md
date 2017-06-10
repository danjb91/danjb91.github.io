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

<iframe src="https://www.youtube.com/embed/oXoq9hyEH8U?ecver=2" width="640" height="360" frameborder="0" style="position:absolute;width:100%;height:100%;left:0" allowfullscreen></iframe>

I had a number of ideas I wanted to work on for my final year project, but over my second year I had a growing interest of using the GPU to offload computation from the CPU.

Now that I'm in my final year at University, I have to select which a final year project to work on. Over the summer I had a number of ideas for this, but I've finally narrowed this down to working with GPU compute.

Since the beginning of second year I had a great interest in using the GPU to offload computation from the CPU. This has many uses, but I decided to focus on particle simulation. The huge parallel processing power of GPUs is perfectly suited to running particle simulations, and allows for a huge increase in the number of particles we can simulate at once.
