---
layout: post
title:  "Perlin Noise Generator"
date:   2021-10-01 00:00:00
categories: Personal-Project JavaFX
---

As a personal project to build upon my JavaFX knowledge, I decided to create a 2D terrain generator that could be used to make procedurally generated terrain for a indie game. I started off with just a perlin noise function that I equalized the values between 0 and 1, assigned it a color, and then applied that color to groups of pixels. This however was quite slow and was only the first iteration with none of the functionality I wanted. Thus, I began to incorporate changing the settings like the octaves, persistance, scale, etc. and applying it to each pixel with the map function instead of looping over each pixel group. I took it further and incorporated zooming and panning functionality so the user can look through the generated terrain.

<h4>  Edit Generation Settings and Auto-Gen </h4>
<img src="{{'/assets/images/TerrainGenVid1.gif' | relative_url}}" />

<h4> Zoom and Pan Function </h4>
<img src="{{'/assets/images/TerrainGenVid2.gif' | relative_url}}" />
