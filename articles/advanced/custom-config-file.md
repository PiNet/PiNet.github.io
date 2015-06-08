---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---

Custom config.txt files
======
Like normal Raspberry Pis running Raspbian. The config.txt file is the first thing the Raspberry Pi checks when it loads up off a PiNet based SD card.   
The config.txt file can contain some key configuration/setup variables which can be used to set stuff like monitor resolution, overclocking etc.   
A full list of the config.txt supported values can be found [here](https://www.raspberrypi.org/documentation/configuration/config-txt.md).   

##What you need to know
Right now PiNet does not fully support custom config.txt parameters.   
They can be manually added to each config.txt on each SD card, but they will be overwritten when the system does an automated kernel update (every 3-6 months).    
   
There is though a fix coming. The plan is to have the ability to push out a custom config.txt to **all** PiNet SD cards.  
Unfortunately, this will not help when you require multiple different config.txt files for different monitors etc.   
Right now I don't see an easy way to solve that issue, but if you have any ideas, [drop me an email or open a github issue](../support.html).
