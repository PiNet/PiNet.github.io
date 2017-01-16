---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---

# Getting started with PiNet

![](/assets/images/raspi-login.jpeg)

## What is PiNet?
PiNet is a free and open source project for helping schools set up and manage a Raspberry Pi classroom.   
It has been developed alongside teachers with feedback from over 15 countries across the world.   
Its key features include   
- Network based user accounts - Any student can sit down at any Raspberry Pi and log in.   
- Network based operating system - All Raspberry Pis boot a single master Raspbian operating system.   
- Shared folders - Easy to use shared folder system for teachers and students.    
- Work collection system - Simple work collection/submittion system to allow students to hand in work.   
- Automated backups - Automatically backup all students work to an external drive periodically.   
- Many more small features like batch user import, classroom management software integration etc.     

The server software is installed on a computer running Ubuntu Linux 14.04 (legacy) or 16.04 (recommended). Ubuntu is completely free. You must then connect the server and Raspberry Pis together by using a [wired network](hardware.html).   
**Note Wifi is not supported** - More information on WiFi [here](../faq.html).   
   
## Ok, I am interested... How do I get started?
First you need to grab the required equipment. Full details of this can be found on the [hardware page](hardware.html).      
- An old desktop/laptop computer for the server with a gigabit ethernet port.   
- A network switch (requires at least a single gigabit or 1000/100/10mbit port for the server).   
- A router (for a standalone network) or connection to your schools network.   
- Some Ethernet cables.    
- A Raspberry Pi and SD card with a size of at least 128mb (so yes, 2gb, 4gb, 8gb etc cards will also work).   

### I dont have a spare old desktop/laptop computer sitting around currently..    
**It is not recommended to use this method in a production environment and it is not officially supported.**   
You can also install a virtual copy of Ubuntu onto another computer to try it out first. This comes with the advantage it is all self contained. If you don't like PiNet, you can just delete the entire
virtual machine (is contained in a single file).    
Although there are a number of pieces of software for virtualization (and if you have your own you prefer to use, please use it), a few examples include Hyper-V, VMWare, Parallels.    
I will be using Virtualbox, a free cross-platform virtualization platform.   
For more info on Virtualbox setup with PiNet, check the [Virtualbox install guide](virtualbox.html)

Installing
-----------

Once you have the needed equipment, you will need to install Ubuntu 16.04 onto your server computer and then install PiNet.
Overall this takes roughly 2-3 hours. Of that 2-3 hours, you are required at the computer for 20-30 minutes.   
Finally when the installation is complete you must copy the generated SD card boot files to a blank SD card.   
If your school or organisation uses any form of web filtering or a proxy to access the internet, make sure to first read the [web filtering information page](../advanced/web-filtering.html).   

1. [Installing Ubuntu server](installing-ubuntu.html)
1. [Installing PiNet](installing-PiNet.html)
1. [Copying files to SD card](sd-card-copy.html)

Once completed, you may want to play with some of the other options in PiNet, the full documentation list can be found back on the [guides page](../guides.html).   
**If you were previously running a Raspi-LTSP server and wish to migrate to a new PiNet server, check out the [user migration guide](../manage-users/migration.html)**.   
