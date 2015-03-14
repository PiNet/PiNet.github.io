---
title: "PiNet, a system for setting up and managing a classroom set of Raspberry Pis."
layout: article
---

#Getting started with PiNet

![](/assets/images/raspi-login.jpeg)


##Ok, I am interested... How do I get started?
First you need to grab the required equipment.   
- An old desktop/laptop computer for the server (preferably made within the last 6 years).   
- A network switch (requires at least a single gigabit or 1000/100/10mbit port for the server).   
- A router (for a standalone network) or connection to your schools network.   
- Some Ethernet cables.    
- A Raspberry Pi and SD card with a size of at least 128mb (so yes, 2gb, 4gb, 8gb etc cards will also work).   

###I dont have a spare old desktop/laptop computer sitting around currently..    
**It is not recommended to use this method in a production environment and it is not officially supported.**   
You can also install a virtual copy of Ubuntu onto another computer to try it out first. This comes with the advantage it is all self contained. If you don't like PiNet, you can just delete the entire
virtual machine (is contained in a single file).    
Although there are a number of piece of software for virtualisation (and if you have your own you prefer to use, please use it), a few examples include Hyper-V, VMWare, Parallels.    
I will be using Virtualbox, a free cross-platform virtualisation platform.   
For more info on Virtualbox setup with PiNet, check the [Virtualbox install guide](virtualbox.html)

Installing
-----------

Once you have the needed equipment, you will need to install Ubuntu 14.04 onto your server computer and then install PiNet.
Overall this takes roughly 2 hours. Of that 2 hours, you are required at the computer for 20-30 minutes maximum.
Finally when the installation is complete you must copy the generated SD card boot files to a blank SD card.

1. [Installing Ubuntu server](installing-ubuntu.html)
1. [Installing PiNet](installing-PiNet.html)
1. [Copying files to SD card](sd-card-copy.html)

Once completed, you may want to change some of the other options in PiNet, the full documentation list can be found back on the [guides page](../guides.html).
