---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---

Overclocking issues
======

PiNet by default overclocks your Raspberry Pis to "Turbo" mode.   
This provides a boost to performance with little if any tradeoff.   
This is supported by the Raspberry Pi foundation and for most users is not an issue.   
   
Some users though have reported issues with this with older Raspberry Pis (or dodgy power supplies). These issues usually manifest themselves in power hungry applications (especially Minecraft Pi edition) crashing or black-screening.

###Disabling overclocking
   
You can easily disable overclocking by modifying the Piboot folder and copying it over to the SD card.    
In the folder is a file called config_standard.txt and also a file called config.txt. Delete config.txt file and copy and rename the config_standard.txt file to config.txt. This file is exactly the same as the initial config.txt file except it does not have any overclocking settings so the Raspberry Pi will default to no overclocking.   
   
**Remember you will need to copy this folder again to every Raspberry Pi SD card and will need to make this change again if the SD card files are ever updated!**   
A more permenent fix is coming for this.   
