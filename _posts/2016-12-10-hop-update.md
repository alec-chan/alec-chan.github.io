---
layout: post
title:  Hop Changelog 2016-12-10
tags: hop-dev 
description: 2D characters in the 3D world
---

After ripping out all the bloated net code from Hop and basically completely restarting the project, things run a lot smoother.  

The animation control code, camera flow, character physics and a lot of other things need to be fixed up... in general, it's really glitchy right now, but it was surprisingly easy to get my 2D character controller to interact properly with the 3D environment.

Here's a short video of a 2D Ricky navigating in the 3D world.

{% include videoplayer.html url="3drickytest.webm" type="video/webm" %}
