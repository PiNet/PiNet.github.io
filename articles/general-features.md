---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---

# General PiNet Features

PiNet includes many different features. A majority of these features come directly from educators using Raspberry Pis in their classrooms on a day to day basis.   
If you have any ideas for new features, [feel free to get in touch](support.html) .

## Network booting   
With PiNet, every Raspberry Pi network boots up off the PiNet server. This is implemented by having a small (40mb) set of boot files (including the kernel) on the SD card. The Raspberry Pi then pulls down the rest it needs as it needs it, just like an SD card.   
This means you maintain a single master copy of Raspbian on the server and if you ever want to make a change to it (add/update new software etc), all you have to do is make the change on the server and reboot all your Pis, that is it!   

## Network user accounts   
Students are already used to sitting down at any normal machine in their school and simply logging on, so why can't we have this with Raspberry Pis as well?   
With PiNet, every student has their own account on the system, allowing them to sit down at any Raspberry Pi and log in. From there, they get access to all their files/preferences.    
You can even batch import these from a CSV file into PiNet or connect into your schools Active Directory server.   

## Shared folders   
It is very common with systems used in schools to have shared folders as a simple option to distribute work to students. PiNet is no exception. It comes with an easy to use, shared folder system similar to a lot of Windows or Mac OS school networks.  
Shared folders on PiNet are available with 2 permission levels, pupil read only or pupil read/write. Teachers can always edit any file in a shared folder.   
To create a shared folder, check the [shared folder page](shared-folders/shared-folders.html).

## Collecting students work
Collecting work from students can be a major issue with Raspberry Pis. The normal way to do it is by plugging in a USB flash drive into the Raspberry Pi or uploading it to the internet.   
PiNet comes with a built in solution called ```Collect work```.   
The collect work system system fetches the students work from each user account from the ```handin``` folder which can be found ```/home/username/handin```.   
More information on this can be found on the [handin page](collect-work.html).   

## Simple additional software installation
Although PiNet comes built in with every piece of software from standard Raspbian SD card images (including a number of extra pieces of software), you may want to add your own packages need for your class.   
To do this, you have 2 options.   
1. The easy way - If it is in the Raspbian repositories (aka can be installed via ```apt-get install```) or is one of the preconfigured packages ready to install automatically (like ```libreoffice```), use the [PiNet software installation tool](installation/installing-software.html).  
2. The slightly more complex way - If the package you want to install is not in the Raspbian repositories, you must install it manually outside PiNet, see the [editing-outside guide](http://pi-ltsp.net/advanced/editing-outsite.html).

## Automatic backups   
Unfortunately hard drives or SSDs are not 100% reliable, they do fail now and then. PiNet offers a simple backup utility to create backups onto a removable drive.   
By default, the PiNet backup utility will save the entire home folder onto a specified removable drive every x days, weeks etc.
**Do note, the PiNet backup utility is still pre-alpha and is supplied with no guarantee, it is your responsibility to frequently check the backups are successfully being created.**   

## Epoptes classroom management software integration
PiNet comes with the ability to easily install Epoptes. Epoptes is a free classroom management suite for helping manage Linux computers.   
Although not all features work on the Raspberry Pi, it is still worth trying out as it does have a number of excellent features that do work with Raspberry Pis.   
These include
- Shutting down or rebooting all Raspberyr Pis
- Blanking all screens
- Remote controlling a students screen
- Watching all students screens from a single application
- Run a command on one or all of the Raspberry Pis in the classroom.

You can install Epoptes from the ```Epoptes submenu``` or from ```Install extra software```.

## Remote apps   
The Raspberry Pi is a fantastic tool, but sometimes there is the odd application which you just can't get working on it.   
Perhaps the application is too resource intensive or may be closed source without an ARM version.  
PiNet includes a built in possible answer to this issue (piggybacking off LTSP).   
You can with a single command, execute the application on the server machine (running Ubuntu) and then seamlessly forward the output of the application to the Raspberry Pi. More details on how to do this can be found on the [Remote Applications](http://pinet.org.uk/articles/advanced/remote-apps.html) page.
