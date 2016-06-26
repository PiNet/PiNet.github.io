---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---

Copying boot files to SD card on Ubuntu
---------------------------------------
When PiNet installs, it generates a folder of SD card files ready to be dropped onto an empty SD card for your Raspberry Pi.
Although this can be done on your Windows or Mac machine, it is even easier to plug in your SD card to the PiNet server.
If your server does not have an SD card slot, you may want to try a USB SD card reader.
There is also nothing stopping you copying the files onto a USB stick to another computer to use its SD card reader.

Assuming you are connecting the SD card to the server (via USB or internal SD card adapter), follow the guide below.

-------
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
