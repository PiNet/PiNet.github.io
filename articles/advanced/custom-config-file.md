---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---

Custom config.txt files
======   

<iframe width="1280" height="720" src="https://www.youtube-nocookie.com/embed/0TlAwf5cHUk" frameborder="0" allowfullscreen></iframe>   

Like normal Raspberry Pis running Raspbian. The config.txt file is the first thing the Raspberry Pi checks when it loads up off a PiNet based SD card.   
The config.txt file can contain some key configuration/setup variables which can be used to set stuff like monitor resolution, overclocking etc.   
A full list of the config.txt supported values can be found [here](https://www.raspberrypi.org/documentation/configuration/config-txt.md).   

## Setting up in PiNet
Although a complex job to do in the background, PiNet allows for custom config.txt parameters to be appended to the default config.txt file then pushed out to all the Raspberry Pis.   

1. Select the "Other" submenu from the PiNet main menu.   
2. Select "Custom-config".   
3. The custom config file can now be edited. Make sure to add your custom parameters below the dotted line.   
4. Once finished editing, hit ctrl+x, followed by y, then enter to save the file.   
5. Finally, run Update-SD to push out the newly created config.txt file. The next time the Raspberry Pis reboot, they will update their config.txt file.   
