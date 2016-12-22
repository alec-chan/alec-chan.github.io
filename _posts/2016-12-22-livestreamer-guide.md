---
layout: post
title:  A guide to using Livestreamer and Crunchyroll
category: misc
description: How I Learned to Stop Using Flashplayer and Love MPV
---

Crunchyroll is a pretty good resource for streaming anime, and considering their recent [partnership](http://www.crunchyroll.com/anime-news/2016/09/08/crunchyroll-and-funimation-partner-to-expand-access-to-anime) with Funimation, it just keeps getting better.  

Despite all that's good about Crunchyroll, as a streaming service, it's held back by its outdated flash based player that is forced upon us for DRM reasons.

That's where Livestreamer comes in.  Livestreamer is able to extract the video stream from a Crunchyroll URL and pipe it into a video player of your choice.  No more flash player!

Here's how to set that up:

1. Install Livestreamer
 - Use your distro's package manager, in my case it's `sudo apt-get install livestreamer`, for macOS `easy_install -U livestreamer`, or if you're on Windows, download the [installer](http://docs.livestreamer.io/install.html#installer) from their site and run that.
2. Write the config file
 - For Unix-likes create the file ~/.livestreamerrc
 - For Windows create the file %APPDATA%\livestreamer\livestreamerrc
 - These are the options I use for my config, feel free to use whatever suits your needs:
 <script src="https://gist.github.com/alec-chan/66b4bfc3b27672b31a82846d80f13384.js"></script>
3. Stream your show
 - Open a command line and execute `livestreamer http://www.crunchyroll.com/gintama/episode-67-for-the-wind-is-the-life-510196` replacing with the url for the episode you're watching.

 Complete documentation for Livestreamer can be found [here](http://docs.livestreamer.io/)


![image]({{ site.url }}/assets/img/livestreamer.png)