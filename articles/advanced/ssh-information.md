---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---

Understanding SSH on the Raspberry Pis
======
By default, Raspberry Pis using PiNet do not by default allow ssh access.   
It though can be extremely useful for debugging to be able to access a Raspberry Pi over SSH.   
There is though a few things you need to be aware of.   
- The PiNet users are **not stored on the Raspberry Pis**. They are stored on the server.   
- The Raspberry Pi verifies the provided credentials when a user enters them by using an SSH connection to the server instead of storing the credentials locally.  
- SSH is enabled by default, although there are no valid user accounts enabled. To SSH into a Raspberry Pi on PiNet, you must enable the root account using ```sudo ltsp-chroot --arch armhf passwd```. Don't forget to recompress the operating system after changing it (can be found in other/NBD-recompress in PiNet). You can log in as root.   
   
## Troubleshooting
### I don't know what the IP address of the Raspberry Pi is?    
Open a terminal on the Raspberry Pi and enter ```hostname -I```. It should print the current IP address of the Raspberry Pi.   

### I am getting key errors when trying to connect to the Raspberry Pi or getting other random errors.   
Sometimes the ssh keys are not generated correctly on PiNet clients.   
To regenerate the keys, reconfigure the openssh-server using ```sudo ltsp-chroot --arch armhf dpkg-reconfigure openssh-server```. Don't forget to recompress the operating system after changing it (can be found in other/NBD-recompress in PiNet).   
