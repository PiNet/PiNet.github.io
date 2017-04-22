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
- Work collection system - Simple work collection/submission system to allow students to hand in work.   
- Automated backups - Automatically backup all students work to an external drive periodically.   
- Many more small features like batch user import, classroom management software integration etc.     

The server software is installed on a computer running [Ubuntu Linux 16.04](https://www.ubuntu.com/desktop) (recommended). Ubuntu is completely free. You must then connect the server and Raspberry Pis together by using a [wired network](hardware.html).   
{% include warning.html title="Note Wifi is not supported" message="More information on WiFi <a href='../faq.html'>here</a>"%}   
   
   
## I am interested, what do I need to get started?
First you need to grab the required equipment. Full details of this can be found on the [hardware page](hardware.html).  
- A network switch (with at least a [single gigabit or 10/100/1000mbit port](https://youtu.be/Wyy8wb2D_y4?t=79) for the server).  
- A router (only if building a standalone network).   
- Some ethernet cables to link it all up together.   
- A [supported Raspberry Pi](http://pinet.org.uk/articles/key-info.html) with an SD card (or micro SD card) of at least 128MB in size.   
- A computer to use for the PiNet server. For this, you have 2 options...   

#### Dedicated computer for the PiNet server   
PiNet can run on an old desktop/laptop you may have sitting around. Just make sure it adheres to the [minimum specs required for PiNet](hardware.html).

#### Virtual machine running on another Windows/Mac/Linux computer for the PiNet server   
Not got an old machine you can dedicate to PiNet? No problem, PiNet can run in an isolated virtual machine on another computer running Windows, Mac OS or Linux. This method comes with a number of advantages including  
- It is easy to delete or start again as PiNet/Ubuntu are stored in a single file on the computer.   
- Given the PiNet/Ubuntu server is a single file, it can be easily moved to a different computer later down the line.   
- Allows for virtual machine snapshots to be used, allowing the server to be easily reverted to an older saved copy.   

There are some disadvantages though   
- A computer with decent performance is required (see [hardware page](hardware.html) for minimum/recommended hardware required).  
- When running the PiNet server, other software running on the computer may feel slower as it is running 2 complete operating systems.   
- Additional hard disk space is required (recommended 40GB for PiNet) as the computer holds a full copy of Windows/Mac OS/Linux as well as PiNet/Ubuntu.   
   
If you have a [powerful enough computer](hardware.html), creating a virtual PiNet server is a great way to try PiNet out without much upfront investment. There are a number of different software platforms for creating/running virtual machines including Hyper-V (Windows only and commercial), VMWare (cross platform and commercial) or VirtualBox (cross platform and open source).   
The recommended platform for setting up a PiNet server is [VirtualBox](https://www.virtualbox.org/) given it is completely free and open source.   
    
{% include info.html title="Want to try out PiNet with VirtualBox?" message="For more info on Virtualbox setup with PiNet, check the <a href='virtualbox.html'>Virtualbox install guide</a>."%}   

Installing
-----------

Once you have the needed equipment, you will need to install Ubuntu 16.04 onto your server computer and then install PiNet.   
Overall this takes roughly 2-3 hours. Of that 2-3 hours, you are required at the computer for 20-30 minutes.   
Finally when the installation is complete you must [copy the generated SD card boot files to a blank SD card](sd-card-copy.html).   
If your school or organisation uses any form of web filtering or a proxy to access the internet, make sure to first read the [web filtering information page](../advanced/web-filtering.html).   

1. [Installing Ubuntu server](installing-ubuntu.html)
1. [Installing PiNet](installing-PiNet.html)
1. [Copying files to SD card](sd-card-copy.html)

Once completed, you may want to play with some of the other options in PiNet, the full documentation list can be found back on the [guides page](../guides.html).   
{% include info.html title="Currently running Raspi-LTSP?" message="Raspi-LTSP is now no longer supported, check out the <a href='../manage-users/migration.html'>user migration guide</a> for details on how to upgrade to PiNet."%}   
