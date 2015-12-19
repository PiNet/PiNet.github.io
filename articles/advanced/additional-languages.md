---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---
# Additional languages   
If you wish to use PiNet with languages other than English, you have a few options.    

## PiNet control panel   
Unfortunately right now, the PiNet control panel is only available in English.   
Work is though in progress to start supporting internationalisation. If you are able to help with translating the project, please sign up on the translators mailing list [here](http://eepurl.com/bDCdZb).   

## Raspbian   
Sometimes it is ok to just have the Raspbian operating system (chroot) available to students in your home language.   
By default, the Raspbian chroot will pull the locale settings from the main Ubuntu server, but if you wish to change the locales used on Raspbian, or add multiple options, follow the instructions below.   
**Note** - Not all software may have available localisation for your language, many still only support English.   
1. Open a terminal on the server.   
2. Enter ```sudo ltsp-chroot``` to enter the Raspbian chroot.   
3. To launch the standard Debian locales selector, enter ```dpkg-reconfigure locales```.   
4. Select any locales you wish to add to the chroot using the space key. Make sure to take note of the full locale name. Once you are finished, hit enter.   
5. Select your default locale you wish to use. **Warning** - LTSP sometimes ignores the default locale, so a few extra steps are needed.     
6. To force the default, first open the main Raspbian lts.conf file using ```sudo nano /etc/lts.conf```.   
7. Inside the file, navigate to the bottom and add the line ```LDM_LANGUAGE="en_US.UTF-8"``` (replacing en_US.UTF-8 with the locale you added earlier). Once finished, exit out of Nano by entering ctrl+x, y, enter.      
8. Finally, recompress the chroot by from inside the PiNet control panel, selecting ```Other``` followed by ```NBD-recompress```.   
