---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---

Editing the operating system outside of PiNet
--------------------------------------------------

Although PiNet allows you to perform most actions a standard user
would need to the Raspbian operating system from within PiNet, it
is understandable if advanced users may want to directly modify
configuration files or install programs on the Raspbian operating system
manually.

The key things you need to know are

- The Raspbian operating system is stored at ```/opt/ltsp/armhf```

- To “chroot” into it (basically allows you to interact with it like a normal Raspberry Pi ```sudo ltsp-chroot --arch armhf``` 
  To exit when you are finished, just type exit and hit enter.

- The lts.conf file (LTSP armhf configuration file) is stored at ```/opt/ltsp/armhf/etc/lts.conf```

- To manually compress the operating system for use after a change ```ltsp-update-image /opt/ltsp/armhf``` 
**(this is extremely important you do this after a change!)**

- The raw boot files before configuration changes have been made can be found at [here](https://github.com/gbaman/PiNet/tree/master/boot)

## An example - Deleting Minecraft Pi edtion

Lets say you want to run a command in the Raspbian operating system, which is stored on the server (and each Pi boots from).   
For example, lets say you want to remove Minecraft-Pi edition (which is installed by default).   
To do this, open a terminal on the server and enter ```sudo ltsp-chroot --arch armhf``` (```sudo ltsp-chroot``` also works on its own if you have no other LTSP chroots).   
You are now inside the Raspbian OS which is running emulated on the server (via chroot). You can run nearly any command you could run on a Raspberry Pi here, 
including ```apt-get purge minecraft-pi``` which deletes Minecraft-Pi edition. When you have finished all your changes, enter ```exit``` and you will be returned to a normal server shell.  
Finally, **you must recompress the operating system!** You have 2 options on how to do this.   
1. From the commandline with ```ltsp-update-image /opt/ltsp/armhf```.
2. From PiNet in the ```Other menu``` and ```NBD-recompress```.

## Executing code on all user accounts.   
Although you can add files/folders/desktop shortcuts etc to /etc/skel so will appear on new users home folders, adding to current users is a little more difficult.    
     
**Warning** Running any of the code below is dangerous. Only use it if you know how to use BASH and have dry run tested your code is actually doing what you expect, using for example echo.   
   
```bash
cut -d: -f1,3 /etc/passwd | egrep ':[0-9]{4}$' | cut -d: -f1 | while IFS= read -r user
do
  echo "$user is great."
  # Use the $user variable to get a username each iteration.
  # For example, to copy a file to every user you could use. This would copy it to the root of their home folder.
  # cp "/awesomefile.txt" "/home/$user/awesomefile.txt"
done
```   
Then make sure you also add the file to /etc/skel, which is used as a skeleton for creating new accounts.
