---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---

Remote Applications   
=====   

**The section below uses an experimental feature of [LTSP (Linux Terminal Server Project)](http://www.ltsp.org/) which PiNet is based off. As such, expect possible issues/bugs**    

PiNet by default includes support for the [ltsp-remoteapps](http://manpages.ubuntu.com/manpages/trusty/man1/ltsp-remoteapps.1.html) tool.    
This tool allows you to run an application from your server computer, on the server then forward the window to the Raspberry Pi. It then behaves as a native application on the Raspberry Pi.    
It is already used in PiNet by the change password utility and to allow you to open the PiNet control panel from a Raspberry Pi.      
   
## Why is this important?   
Lets say you have an application that only runs on an x86 processor (the Raspberry Pi uses an ARM processor), you would be able to access that application on the Raspberry Pi as long as the application ran on your server and was installed.       
Or, perhaps there is an application that doesn't run well on the Raspberry Pi (too slow etc), you can use ltsp-remoteapps to launch it from the Raspberry Pi and all the processing will be done by the server.     

## Warnings    
1. ltsp-remoteapps requires a powerful server machine, as it is running additional applications, especially if using with a full classroom of students. It very much depends on which application though is being run through it.    
2. **ltsp-remoteapps is buggy!** It can have issues with some applications and for applications involving a high frame-rate (games or videos for example), it may not work well.    
3. You must have a fast network to use ltsp-remoteapps given additional network traffic required. A full gigabit (10/100/1000mbit/s) network is **highly** recommended.    
    
## Using remoteapps    
Using the ltsp-remoteapps tool is actually very simple. All you need is to know the application name.   
1. Open a terminal on the Raspberry Pi started up with PiNet.   
2. Enter ```ltsp-remoteapps application_name```.    
3. In the above step, make sure you replace application_name with the actual name of the application you want to launch. For example ```ltsp-remoteapps firefox``` will launch Mozilla Firefox on the server and forward it to your Raspberry Pi.    
4. If you get no data returned on the terminal and the connection doesn't start, there may be an issue with the application you are trying to load (most common you are using the wrong name for it). Don't forget, not all applications work with ltsp-remoteapps.    
