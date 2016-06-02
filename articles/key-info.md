---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---

# PiNet Key Information

This page contains some key information for PiNet that may be useful, especially when trying to diagnose issues.   

## General
- PiNet is licensed under the [GNU General Public License version 2](https://github.com/PiNet/PiNet/blob/dev/LICENSE).
- PiNet documentation is licensed under the [MIT license](https://github.com/PiNet/PiNet.github.io/blob/master/LICENSE).
- Both licenses allow the full PiNet system to be used in commercial and non commercial environments.
- PiNet sets up the Raspberry Pis as **fat clients!** Not thin clients! Fat clients do all the processing locally on the Raspberry Pi, meaning you have full access to all the local hardware features like the GPIO pins and the camera module port.
- PiNet is based on the [Linux Terminal Server Project](http://www.ltsp.org/).   

## Hardware requipments
- The server must be able to reliably run Ubuntu 14.04 and have a gigabit ethernet port. There are no minimum hardware requirements provided, but a machine with at least 2gb of RAM is recommended.
- The supported Raspberry Pi models are
  - Raspberry Pi 1 Model B revision 1 - Can sometimes have issues due to very limited RAM.
  - Raspberry Pi 1 Model B revision 2
  - Raspberry Pi 1 Model B+
  - Raspberry Pi 2 Model B   
  - Raspberry Pi 3 Model B (PiNet Jessie only)    
- Raspberry Pi based hardware not officially supported includes
  - Raspberry Pi 1 Model A
  - Raspberry Pi 1 Model A+
  - Raspberry Pi 1 Compute Module
  - Raspberry Pi Zero    
- Hardware that will never be supported as clients includes
  - Banana Pi
  - Odroid C1
  - BeagleBone Black
  - PandaBoard
  - Cubieboard
  - UDOO


## Data
- All user data is stored on the server, not the Raspberry Pis. It is stored in ```/home/```.   
- The Raspbian based operating system is built from the base packages from the Raspbian repositories. **It is not built from a Raspbian SD card image.** Instead, it is built a very similar way to the Raspbian images are, using a lot of code from Alex Bradbury's excellent [Spindle](https://github.com/asb/spindle) tool. This approach means that the PiNet Raspbian version will lag a little behind the Raspberry Pi Foundations SD card images. **Not all features may be brought across from the Raspberry Pi Foundation SD card images if they are deemed unnecessary or unneeded for PiNet.**   
- Raspbian files are stored in ```/opt/ltsp/armhf```.
- By default, NBD (Network Block Device) is used (instead of NFS) to make the image available across the network to the Raspberry Pis.
- By default, SquashFS is also used. The idea is that the operating system stored in ```/opt/ltsp/armhf``` is compressed into a single file which is then stored in ```/opt/ltsp/images```. By compressing the image, on average we get a 40% reduction in network traffic between the server and the Raspberry Pis.
- If using SquashFS, you must recompress the SD card image after every change you make to Raspbian. PiNet automatically does this, but if you manually edit it outside PiNet, you must force it yourself. More info on this on the [editing outside](advanced/editing-outside.html) page.

## Users and groups
- All users on PiNet are just normal Linux users.
- They must be in the ```pupil```, ```dialout``` and ```video``` groups as a minimum. PiNet automatically does this when added a new user inside the software.
- PiNet can also manually be told to check every user is in the correct groups by running the ```Group-check``` menu option in ```Manage-Users```.
- Teachers should also be in ```teacher``` group. This gives them access to Epoptes control panel and shared all shared folders read/write.

## SD Card
- The SD card image contains just the required files to start the Raspberry Pi booting and connect it to the server.
- In the ```cmdline.txt``` file is the IP address for the server. This is fixed on the SD card image. You can though edit it to a different address if your server changes IP address. If you wish to edit it, change the address after ```nbbroot=```.
- The main things contained on the SD card are the Kernel, the Initramfs, Raspberry Pi firmware blobs and the configuration files (main ones being ```cmdline.txt``` and ```config.txt```). There is also a ```version.txt``` file which is used by the server to verify the SD card image is in sync with the server.   
- The Kernels and Initramfs are built together with the kernel modules (stored on the server). Their versions must match, or else the kernel modules won't correctly load. A tell-tale sign they are mismatched is the keyboard and mouse will stop working.
- Sometimes, updates are released for the kernels. As the SD card images are manually built, they must be updated. This can take a few days.
- Once a PiNet SD card image update is released, you are notified the next time your server is connected to the internet and it is auto applied to SD cards. This works most of the time, but if you have issues just run ```Update-SD``` to build a new SD card image and copy it across.

## Project
- The project is completely open source and free. It contains no advertising.
- The lead developer is [Andrew Mulholland](http://pi.gbaman.info/?page_id=90).
- The main code is split into 2 branches, stable and dev (also know as bleeding edge). Dev branch has new experimental features that may or may not make it into PiNet stable.
- The project code stable branch can be found at [https://github.com/PiNet/PiNet](https://github.com/PiNet/PiNet).
- The project code dev branch can be found at [https://github.com/PiNet/PiNet/tree/dev](https://github.com/PiNet/PiNet/tree/dev).
- The project documentation code can be found at [https://github.com/PiNet/PiNet.github.io](https://github.com/PiNet/PiNet.github.io).
- The main site for the project can be found at [http://PiNet.org.uk](http://PiNet.org.uk).
- PiNet is mainly written in BASH with a number of supporting functions also written in Python 3.

## Networking
- PiNet server is by default completely passive on a network. **It does not include a DHCP server.** It just Raspberry Pis to be able to connect to it.
- An internet connection to at least the server is recommended for updates, but not required.   
- For any more than a few Raspberry Pis, a gigabit (1000/100/10mbit/s) network is required.
- The Raspberry Pis can only support 100/10mbit/s, but the server must have a gigabit ethernet cable coming into the network switch which is then shared by all the Raspberry Pis.
- A network switch with 100mbit/s ports and at least 1 gigabit uplink port works well and can usually be picked up cheaply.
- Try not to daisy chain lots of smaller switches off each other, using 1 or 2 larger switches is always better and more reliable.
- **Wifi is not supported!** Wireless N bandwidth is extremely limited and on a good day, you may get 100mbit/s unidirectional shared with all the Raspberry Pis. This is compared to gigabit ethernet which gets 1000mbit/s bidirection. More details on this can be found on the [FAQ page](faq.html).
