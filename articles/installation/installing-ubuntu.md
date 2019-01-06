---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---

# Ubuntu

Linux itself is actually a family of different distributions, all their
own Operating Systems but based on the Linux Kernel. Ubuntu is one of
these distributions. It was specifically designed to be really simple
and easy to use for new users of Linux and is the single most popular
Linux distribution. The current LTS (Long Term Support) version of
Ubuntu is 16.04 (with the previous being 14.04). 16.04 has guaranteed
software and security updates till April 2021.   
PiNet also maintains support for the previous Ubuntu 14.04 release, but it is highly recommended with a new install to use Ubuntu Desktop 16.04.

The codename for 16.04 is Xenial Xerus.

# Installation

## Creating Ubuntu Installation Disk
First you need to create an installation media for installing Ubuntu on your server computer. This can be in the form of
a disk or a USB flash drive. Creating and booting from a disk is easier for beginners.   
Ubuntu have a number of guides for different operating systems for creating an Ubuntu 16.04 installation disk from 
different operating systems.   
Select the one you are going to create the installation DVD from. You will need a standard writeable DVD (and not a CD) for this.      
- [Windows](http://www.ubuntu.com/download/desktop/burn-a-dvd-on-windows)   
- [Mac](http://www.ubuntu.com/download/desktop/burn-a-dvd-on-mac-osx)   
- [Ubuntu Linux](http://www.ubuntu.com/download/desktop/burn-a-dvd-on-ubuntu)   

## Installing Ubuntu 16.04

{% include danger.html title="Warning" message="The process below will involve completely wiping the hard drive of the chosen server machine. All data (unless you choose to partition the drive) will be lost."%}

For the following process, you will need a working (**if possible unfiltered**) Internet connection.
Wired Ethernet is preferable for installation.

1.  Insert your Ubuntu 16.04 installation disk into the computer you
    intend to use as a server

2.  Shutdown the computer

3.  Hold the “Boot from CD” key or “Boot menu” key. This is commonly F3.
    If in doubt, refer to your computer’s manual.

4.  Ubuntu installer screen should load up as below. Select “Install
    Ubuntu”   
    ![](/assets/images/image2.jpeg)   
   
5.  Select English and hit continue   
    ![](/assets/images/image3.jpeg)
   
6.  Check both the “Download updates while installing” and
    “Install-third party software” and click
    continue.   
    ![](/assets/images/image4.jpeg)   
   
7.  Select to “Erase disk and install Ubuntu”. This will completely wipe
    your hard drive! No information currently stored on this computer
    will remain. It will all be deleted    
    ![](/assets/images/image5.jpeg)   
   
8.  Select your location and time zone. For the UK, select London and
    hit continue       
    ![](/assets/images/image6.jpeg)   
   
9.  Select your keyboard. The default is likely correct. If living in
    the UK, select “English (UK)” and select
    continue.   
    ![](/assets/images/image7.jpeg)
   
10. Now enter your login details. These will be the administer login
    details on the server. It is recommended you leave the computer name
    at default. When selecting a username, note this will be the admin account and shouldn't be used with the Raspberry Pis.
    You can create yourself an account for day to day use later on. **Do not set the username to ```teacher``` or ```pupil``` as this may cause issues later!**       
    ![](/assets/images/image8.jpeg)

11. Now wait for Ubuntu to install. This normally takes roughly 10-20
    minutes, depending on internet speed and computer processing power.   
    ![](/assets/images/image9.jpeg)

12. Once it finishes it will ask to reboot. Remove your installation CD
    from the drive and select “Restart now”.   
    ![](/assets/images/image10.jpeg)

## Installing PiNet

Now that Ubuntu is installed, you can move onto installing PiNet.   
[Installing PiNet](installing-PiNet.html)
