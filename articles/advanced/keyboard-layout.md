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
Once you have figured out the needed keyboard mapping, open a terminal on the server and enter ```sudo ltsp-chroot dpkg-reconfigure keyboard-configuration``` and select the required layout values.

- Below is an example of settings for Portuguese
  - After these changes you will have cedilla (letter ç) support using the ```right-ALT``` and ```,```. 
    - To enable using the keys ```'``` and ```c``` as you would on the Windows OS with US Internation Keyboard selection, enter the following line to append to the environment file:
      - ```echo "GTK_IM_MODULE=cedilla QT_IM_MODULE=cedilla" >> /etc/environment```
    - Still, some applications (e.g. LibreOffice) may still require the ```right-ALT``` + ```,``` sequence. 

  ![](/assets/images/dpkg-reconfigure/keyboard-configuration/pt.keyboard-configuration_01.jpg)
  ![](/assets/images/dpkg-reconfigure/keyboard-configuration/pt.keyboard-configuration_02.jpg)
  ![](/assets/images/dpkg-reconfigure/keyboard-configuration/pt.keyboard-configuration_03.jpg)
  ![](/assets/images/dpkg-reconfigure/keyboard-configuration/pt.keyboard-configuration_04.jpg)
  ![](/assets/images/dpkg-reconfigure/keyboard-configuration/pt.keyboard-configuration_05.jpg)


Finally, recompress the operating system with ```ltsp-update-image /opt/ltsp/armhf```.
