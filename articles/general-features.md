---
title: "PiNet, a system for setting up and managing a classroom set of Raspberry Pis."
layout: article
---

#General PiNet Features

PiNet has a number of other features designed to make setting up Raspberry Pis in a classroom even easier including shared folders, automated backups and collecting students work.

##Installing extra software
Although PiNet comes built in with every piece of software from standard Raspbian SD card images (including a number of extra pieces of software), you may want to add your own packages need for your class.   
To do this, you have 2 options.   
1. The easy way - If it is in the Raspbian repositories (aka can be installed via ```apt-get install```) or is one of the preconfigured packages ready to install automatically (like ```libreoffice```), use the [PiNet software installation tool](installation/installing-software.html).  
2. The hard way - If the package you want to install is not in the Raspbian repositories, you must install it manually outside PiNet, see the [editing-outside guide](http://pi-ltsp.net/advanced/editing-outsite.html).

##Automatic backups
It is **highly** recommended if your students are working on critical work (like controlled assessments or assessed work), that you enable backups of their work.   
If your server is already backed up automatically (for example if it is a virtual machine on the school server which is backed up every night), then you don't need to worry.   
If you set up your own system and it is not already being automatically backed up, you should enable the [PiNet backup utility](backups/backups.html).   
It allows you to configure the entire server home folder (which stores all the users files) to be backed up to an external location, for example an external hard drive.   
**DO NOT STORE THE BACKUP ON THE MAIN INTERNAL HARD DRIVE!** If you do this, there isn't much point of a backup as all it takes is for that hard drive to fail and you loose everything.   
**Do note, the PiNet backup utility is still pre-alpha and is supplied with no guarantee, it is your responsibility to frequently check the backups are successfully being created.**   

##Collecting students work
Collecting work from students can be a major issue with Raspberry Pis. The normal way to do it is by plugging in a USB flash drive into the Raspberry Pi or uploading it to the internet.   
PiNet comes with a built in solution called ```Collect work```.   
The collect work system system fetches the students work from each user account from the ```handin``` folder which can be found ```/home/username/handin```.   
More information on this can be found on the [handin page](collect-work.html).   

##Shared folders
PiNet comes with a shared folder system similar to a lot of Windows or Mac OS school networks.   
Shared folders on PiNet are available with 2 permission levels, pupil read only or pupil read/write. Teachers can always edit any file in a shared folder.   
To create a shared folder, check the [shared folder page](shared-folders/shared-folders.html).

##Updating SD card image
A number of boot files must be placed on the SD card to connect the Raspberry Pi to PiNet. These include a number of configuration files and the Kernel.   
From time to time updates for these will be provided.   
Also stored on the SD card is the IP address of the server so the Raspberry Pis know what to connect to. If this changes or if new boot files are released, you may want to update the SD card image folder.   
To do this, use the Update-SD option. For more information on Update-SD, check the [Update-SD page](sd-card-update.html).

##Epoptes classroom management software
PiNet comes with the ability to easily install Epoptes. Epoptes is a free classroom management suite for helping manage Linux computers.   
Although not all features work on the Raspberry Pi, it is still worth trying out as it does have a number of excellent features that do work with Raspberry Pis.   
These include
- Shutting down or rebooting all Raspberyr Pis
- Blanking all screens
- Remote controlling a students screen
- Watching all students screens from a single application
- Run a command on one or all of the Raspberry Pis in the classroom.

You can install Epoptes from the ```Epoptes submenu``` or from ```Install extra software```.
