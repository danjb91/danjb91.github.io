---
layout: post
title: Direct 3D - Soft Shadows
excerpt: "Dynamic soft shadows in DirectX 9"
categories: blog
tags: [University, Second Year Projects, DirectX 9, C++]
comments: false
share: false
author: dan_bradshaw
---

<iframe src="https://www.youtube.com/embed/HlVocgF9OM0?ecver=2" width="640" height="360" frameborder="0" style="position:absolute;width:100%;height:100%;left:0" allowfullscreen></iframe>

This is the most recent version of the spotlights system I've created in my second year. It has support for any number of lights (within reason! :D) and supports different projected textures for each light.

It makes use of comparison filters to make PCF shadow filtering faster and create smoother, better looking shadows.

<iframe src="https://www.youtube.com/embed/5ShIiPgCtjM?ecver=2" width="640" height="360" frameborder="0" style="position:absolute;width:100%;height:100%;left:0" allowfullscreen></iframe>

The video above demos an earlier version which only supported one light.
