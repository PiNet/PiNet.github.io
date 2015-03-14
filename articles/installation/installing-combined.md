---
title: "PiNet, a system for setting up and managing a classroom set of Raspberry Pis."
layout: article
---

#Ubuntu

Linux itself is actually a family of different distributions, all their
own Operating Systems but based on the Linux Kernel. Ubuntu is one of
these distributions. It was specifically designed to be really simple
and easy to use for new users of Linux and is the single most popular
Linux distribution. The current LTS (Long Term Support) version of
Ubuntu is 14.04 (with the previous being 12.04). 14.04 has guaranteed
software and security updates till April 2019.

The codename for 14.04 is Trusty Tahr.

#Installation

##Creating Ubuntu Installation Disk
First you need to create an installation media for installing Ubuntu on your server computer. This can be in the form of
a disk or a USB flash drive. Creating and booting from a disk is easier for beginners.   
Ubuntu have a number of guides for different operating systems for creating an Ubuntu 14.04 installation disk from 
different operating systems.   
Select the one you are going to create the installation DVD from.    
You will need a standard writeable DVD (and not a CD) for this.      
- [Windows](http://www.ubuntu.com/download/desktop/burn-a-dvd-on-windows)   
- [Mac](http://www.ubuntu.com/download/desktop/burn-a-dvd-on-mac-osx)   
- [Ubuntu Linux](http://www.ubuntu.com/download/desktop/burn-a-dvd-on-ubuntu)   

##Installing Ubuntu 14.04


Please make sure your server machine has no important information left
on it, as we will be ***deleting everything***. You have been warned!
You also need a working (if possible unfiltered) Internet connection.
Wired Ethernet is preferable for installation.

1.  Insert your Ubuntu 14.04 installation disk into the computer you
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
    at default.   
    ![](/assets/images/image8.jpeg)

11. Now wait for Ubuntu to install. This normally takes roughly 10-20
    minutes, depending on internet speed and computer processing power.   
    ![](/assets/images/image9.jpeg)

12. Once it finishes it will ask to reboot. Remove your installation CD
    from the drive and select “Restart now”.   
    ![](/assets/images/image10.jpeg)   

---

##Installing PiNet
Now you have an Ubuntu 14.04 server setup, it is time to actually install PiNet. PiNet is run through a terminal.
This allows you use it locally or even run the software over SSH!
Lets get started!   

1.  Once the machine reboots, login with your credentials you set up
    earlier.   
    ![](/assets/images/image11.jpeg)

2.  Select the search button in the top left corner.   
    ![](/assets/images/install-ltsp-3.jpeg)

3.  Search for and select “Terminal”. You can also just hit Ctrl + Alt +
    T.   
    ![](/assets/images/install-ltsp-4.jpeg)

4.  You will then be presented with a terminal. PiNet runs inside a
    terminal window. You may find it useful to resize the terminal
    window to make it larger or put it in full screen.   
    ![](/assets/images/install-ltsp-5.jpeg)

5.  Enter ```wget --content-disposition http://pi-ltsp.net/downloadalpha```
    and hit enter. This downloads the PiNet script. The main script is called ```pinet```.    
    ![](/assets/images/install-ltsp-7.jpeg)

6.  Once that completes, enter ```sudo bash pinet``` which will launch
    PiNet. A desktop icon will be created when the software installs but 
    you can always use this command to manually launch PiNet.   
    ![](/assets/images/install-ltsp-9.jpeg)

7.  Enter your password as the application must be run as administrator 
    (nothing will look like it is being entered, this is a Linux security feature so don't worry, it is being entered).   
    ![](/assets/images/install-ltsp-10.jpeg)   
       
8.  PiNet will detect its installation location is wrong. Don't worry, 
    it will fix it. Select ok.  
    ![](/assets/images/install-ltsp-11.jpeg)   
    
9.  PiNet will offer to run a full install, select yes.  
    ![](/assets/images/install-ltsp-12.jpeg)   
    
10. PiNet supports importing user data from an older PiNet server. 
    See the [migration guide](../manage-users/migration.html) for details. Select No.   
    ![](/assets/images/install-ltsp-14.jpeg)   

9.  The install will take roughly 1-2 hours depending on processor speed
    and internet speed. Select ok and it will start the installation.
    You can now leave it to work.   
    ![](/assets/images/install-ltsp-15.jpeg)

10. Around 1-2 hours later, the extra software dialog will be displayed.
    Here you can select any additional software you with to install.
    Libreoffice can be useful for a classroom; it is a free full office
    suit, similar to Microsoft Office. You can also install a custom
    package from the software repositories if you know its full name.
    Once you have finished, select cancel (or finished) to move on.   
    ![](/assets/images/image20.jpeg)

11. Select yes when asked if you are finished installing software.   
    ![](/assets/images/image21.jpeg)

12. The operating system will now be compressed. After every change made
    to the operating system, it must be recompressed which takes roughly
    5 minutes normally. Select ok.   
    ![](/assets/images/image22.jpeg)
  
14. You must decide if you need students to have Sudo access on
    the Raspberry Pi. If you intend to work with the GPIO pins on the
    Raspberry Pi they will need it. You can really easily later enable
    or disable Sudo use in the Manage-Users submenu in the main software
    options. If in doubt, is recommended to enable it by selecting yes.   
    ![](/assets/images/image24.jpeg)   

13. If using 2 network interface cards then check the IP address is
    correct. If you are only using 1 (most people), then the default
    will likely be correct. Select yes.   
    ![](/assets/images/image23.jpeg)   

15. PiNet installation is now complete. The server has generated an
    SD card image which is located in /home/YourUser/piboot.
    You need to copy these files onto a blank formatted SD card and
    connect the Raspberry Pi to the network.   
    ![](/assets/images/image25.jpeg)

16. You are recommended to check the Backup section of this manual on
    setting up an automatic backup of your students work to an external
    hard drive in case of hard drive failure. 

------

##Copying boot files to SD card on Ubuntu

When PiNet installs, it generates a folder of SD card files ready to be dropped onto an empty SD card for your Raspberry Pi.
Although this can be done on your Windows or Mac machine, it is even easier to plug in your SD card to the PiNet server.
If your server does not have an SD card slot, you may want to try a USB SD card reader.
There is also nothing stopping you copying the files onto a USB stick to another computer to use its SD card reader.

Assuming you are connecting the SD card to the server (via USB or internal SD card adapter), follow the guide below.

1.  Insert SD card into SD card reader on Ubuntu server. If the computer
    has an internal SD card reader, use it. If not, a USB reader is
    recommended.

2.  Open “Files” near top left.   
    ![](/assets/images/image26.jpeg)

3.  Piboot folder with the required boot files is stored in this
    folder.   
    ![](/assets/images/image27.jpeg)

4.  Open search again and search for “Disks”, Ubuntu’s disk manager.   
    ![](/assets/images/image28.jpeg)

5.  Select your SD card from the menu at the side. Be very careful to
    pick the correct device here! A good check is check the size, for
    example my SD card in the screenshot is an 8 gigabit SD card.   
    ![](/assets/images/image29.jpeg)

6.  Select the cog in the top right and select format.   
    ![](/assets/images/image30.jpeg)

7.  The default options should be correct in the format settings window.
    Select “Format…”.   
    ![](/assets/images/image31.jpeg)

8.  Check the device is correct and select format.   
    ![](/assets/images/image32.jpeg)

9.  Open the piBoot folder and select all the files by dragging while
    holding left mouse button down.    
    ![](/assets/images/image33.jpeg)

10. Right click any file in the selection and select “Copy to”.   
    ![](/assets/images/image34.jpeg)

11. Select the SD card from the side bar. It is usually called BOOT but
    may be named anything. It should be completely empty. Then hit
    select.   
    ![](/assets/images/image35.jpeg)

12. Finally hit the eject icon beside the SD card and remove it from the
    computer. Now insert it into a Raspberry Pi, plug the network cable
    in along with keyboard and mouse and plug in the power. The
    Raspberry Pi should then boot successfully. Don't worry if you get an error complaining about the desktop environment, this is only a notice and not a problem. It only occurs with accounts that have logged directly onto the server.    
    ![](/assets/images/image36.jpeg)

If the Raspberry Pi fails to boot, check out the [Support section](../support.html).
