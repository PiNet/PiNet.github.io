---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---

Changing keyboard mapping
======

If you are having issues with keys in the wrong place on PiNet on your keyboard, you may need to change your keyboard layout.
It is recommended you first test it on a running Raspberry Pi then select the final working layout on the server.

### Changing keyboard mapping on a Raspberry Pi
Launch a terminal and enter ```dpkg-reconfigure keyboard-configuration```. This will launch the configuration utility allowing you to select your keyboard model.
To test it, enter ```invoke-rc.d keyboard-setup start```.
If it does not fix it, try another option in the keyboard-configuration panel.  
If you loose control of your keyboard, just reboot your Raspberry Pi and all configuration changes will be reverted.

### Changing keyboard mapping for all Raspberry Pis via the server
Once you have figured out the needed keyboard mapping, open a terminal on the server and enter ```sudo ltsp-chroot dpkg-reconfigure keyboard-configuration```.
Select the required layout and then recompress the operating system with ```ltsp-update-image /opt/ltsp/armhf```.
