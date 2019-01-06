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
5. PiNet will then auto run Update-SD and recompress the operating system. Once this is complete, simply reboot all the Raspberry Pis and they will pull in the new config.txt file, then reboot to apply it.

## Example - Enabling the OpenGL driver
1. Select the "Other" submenu from the PiNet main menu.   
2. Select "Custom-config".
3. Add the following lines into the file   
  ```
  dtoverlay=vc4-kms-v3d   
  gpu_mem=128
  ```
  ![Custom config file screenshot](/assets/images/custom-config1.png)
4. Once finished editing, hit ctrl+x, followed by y, then enter to save the file.
5. PiNet will then auto run Update-SD and recompress the operating system. Once this is complete, simply reboot all the Raspberry Pis and they will pull in the new config.txt file, then reboot to apply it.
6. Note as well, to make sure the required Raspbian pages are installed to go alongside the driver, put the following packages into Install-Program ```xcompmgr libgl1-mesa-dri mesa-utils```.   
