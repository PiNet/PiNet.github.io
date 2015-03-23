---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---

Understanding kernels on the Raspberry Pi and PiNet
-----------------------------------

***Note*** -  This guide is provided as is, it is unlikely any additional support will be offered for its contents if you get stuck. It is only designed for more advanced Raspberry Pi / Linux users. If you do have issues though, you could always try you luck at [contacting support](../support.html).   
***Note 2*** - Take this document as draft level quality as it has not been double checked by all relevant experts yet, it is only what I have been able to gather myself over the past year.

##What is a kernel?
"In computing, the kernel is a computer program that manages I/O (input/output) requests from software, and translates them into data processing instructions for the central processing unit and other electronic components of a computer. The kernel is a fundamental part of a modern computer's operating system." - [Wikipedia](http://en.wikipedia.org/wiki/Kernel_%28operating_system%29)        
   
The kernel is a vital part of Raspbian (and any operating system), it is the bridge between the computer hardware and the software on top. It is incredibly complex and is generally just huge! The standard Linux kernel currently (February 2015) has over 17 million lines of code contributed by over 13,000 people.   
It contains all the drivers/modules required to work with the hardware. Sometimes if you want a very specialist piece of hardware to work, you may need to compile your own kernel.
   
##Raspberry Pi kernels
The kernel for the Raspberry Pi can be found on the /boot partition (the FAT32 partition you can open on Windows, Mac and Linux).   
For the Raspberry Pi 1 (B, B+, A, A+) it is called kernel.img.   
For the Raspberry Pi 2 (B) it is called kernel7.img.  
    
The kernel is one of the few bits of software that wasn't able to run on both the Raspberry Pi 1 CPU (ARM6) and the Raspberry Pi 2 (ARM7) with the same version.   
Instead the 2 versions had to be compiled separately and the firmware selects the correct one depending on the hardware it detects on boot.   
   
##Kernel sources   
There are 2 main sources for Raspberry Pi kernels. Both have their advantages and disadvantages.     
- Official Raspberry Pi foundation kernels   
- Unofficial Raspbian team kernels

####Raspberry Pi foundation kernels   
The Raspberry Pi foundation kernels are the official kernels the Raspberry Pi is shipped with. They are considerably more stripped down than the Raspbian team kernels, but are always the most up to date. For new hardware (like the new USB chip in the B+ or new CPU in Raspberry Pi 2 B), they available on day 1 of the hardware release.   
They have a number of issues including not being correctly in line with the standard Debian kernels and lacking the header files, required to build custom kernel modules with.   
They also don't follow the normal installation method and package names in the Raspbian software repositories.
For the average user though, these 2 downsides make no difference.   
The kernel is though currently lacking AUFS support. AUFS is a virtual module for PiNet. 

####Raspbian team kernels   
The Raspbian team maintains their own kernels. The Raspbian team maintain the Raspbian software repositories. Their kernels are based off the standard Debian kernels, and so contain a larger array of modules to support even more hardware. Due to this fact alone, their kernels are larger and take longer to build, although this is rarely an issue.   
They include proper header files for compiling your own modules and generally more closely follow the standard Debian way of handling kernels, including the standard Debian way of packaging kernels and distributing them using apt.   
One of the extra modules they include is AUFS, a vital module for PiNet network booting that is currently missing from the Raspberry Pi foundation kernels.   
One of their major downsides though is they usually arrive quite a bit later than the Raspberry Pi foundation kernels, sometimes a number of weeks later.    

###Initramfs
When talking about kernels, another key thing to discuss is the initramfs (also sometimes known as initrd although they are slightly different).   
The initramfs is a tiny compressed entire filesystem in a single file. It contains a complete mini linux filesystem in 5mb-10mb.   
The idea behind it is it is an extension of the kernel, containing a number of modules and startup scripts. It can be easily edited, while editing the kernel would require completely recompiling it again! It also allows you to start a mini operating system to load more advanced modules to use as a springboard for loading more advanced operating systems in complicated circumstances, for example network booting!   
(If doing this on PiNet, enter run ```sudo ltsp-chroot``` before running the below commands).   
You can generate an initramfs using the ```mkinitramfs``` command. For example, to build one for the 3.18 kernels, first get the exact version you with to build with using ```ls /lib/modules/```   
Then use ```sudo mkinitramfs /boot/myAwesomeInitramfs3.18.img 3.18.6-v7+```.   
**Note - You must build the initramfs with the exact same kernel version you intend to use. Even if they are out by one minor version or they are out of date with the version on the server, devices (like keyboards and mice) may not work**


##So where does PiNet come into all this?
With PiNet, the kernel and initramfs version is extremely important.   
Both live on the SD card with normal Raspberry Pi firmware and all the config files.   
**PiNet currently uses the Raspbian team kernels as they contain the required extra modules (OverlayFS or AUFS, SquashFS and NBD) which are missing from the Raspberry Pi foundation kernels.** - this is being worked on though.   
You may notice after software updates to PiNet, sometimes your PiNet clients will randomly reboot just after hitting the login screen a single time. This is because they have detected they are running an out of date version of the kernel files (mismatch with the version on the server) and the server has automatically copied the new kernel and initramfs over to the SD card. It must restart the Pi to apply the update. It should only happen a single time for each SD card on a new kernel update.   
   
##I am impatient and want to try the new kernel features right now!   
You can do this if you compile your own kernel.   
Kernel compiling is an incredibly CPU intensive job. Although it could be done natively on the Raspberry Pi, it would take many hours. Fortunately we can cross compile (compile it on another more powerful computer) it.   
####Building the kernel   
Adafruit has an excellent kernel building tool that runs on Windows, Mac and Linux called the [Kernel-O-Matic](https://learn.adafruit.com/raspberry-pi-kernel-o-matic/overview) that is a great place to start.   
Once it is installed (and you have got as far as ```vagrant ssh```), you need to grab a few extra bits.   
The main one being AUFS.   
```cd /rpi_linux/```   
```git clone git://aufs.git.sourceforge.net/gitroot/aufs/aufs3-standalone.git```   
```cd aufs3-standalone```
```git checkout origin/aufs3.18``` (change the 3.18 to whatever version you are working with)   
```cp -rp *.patch ../```   
```cp -rp fs ../```   
```cp -rp Documentation/ ../```   
```cp -rp include/ ../```
```cd ..```   
```patch -p1 < aufs3-kbuild.patch``` (may be a few errors, don't worry)   
```patch -p1 < aufs3-base.patch```   
```patch -p1 < aufs3-proc_map.patch```   
```patch -p1 < aufs3-standalone.patch```   
```patch -p1 < aufs3-mmap.patch```   
Now that your kernel is now patched with AUFS support, is time to compile it.   
Launch adabuild with ```sudo adabuild```   
Give it a minuite or 2 for the kernel menu to appear. You must enable the 3 extra modules.     
To enable a module, hit y when it is selected.    
- Network block device : ```Device Drivers```, ```Block devices```, ```Network block device support```   
- SquashFS : ```File systems```, ```Miscellaneous filesystems```, ```SquashFS 4.0 - Squashed filesystem support```   
- AUFS : ```File systems```, ```Miscellaneous filesystems```, ```Aufs (Advanced multi layered unification filesystem)``` - It is right at the bottom.   

Finally, select exit at the bottom (tab then enter).   
The kernel will start compiling. You will need to do the same for the Pi 2 kernel once the Pi 1 kernel is completed.   
   
####Installing the new kernel
The new kernel is packaged up inside a .deb file. Follow the instructions on the kernel-o-matic guide on how to get the newly created .deb file.   
- Once you have it, move it to your PiNet server (via pendrive or FTP) and copy the file into somewhere like ```/opt/ltsp/armhf/tmp```.   
- Next, switch to the Raspbian OS with ```sudo ltsp-chroot --arch armhf```.   
- Install the .deb package using ```dpkg -i /tmp/whatYouNamedIt.deb```.    
    
####Generating the initramfs   
We now need to generate the initramfs for the new kernel. To do so (continuing on from above)   
- Build the initramfs with ```sudo mkinitramfs /boot/myAwesomeInitramfs3.18.img 3.18.6-v7+```. (Remember to change the version number if need be, see initramfs section above).   
- At this point it would be worth starting a manual recompress of the Raspbian install, the tool can be found in PiNet, in "other" and is called ```NBD-recompress```.   
    
####Install it on the SD card   
- First, start with a normal PiNet SD card.   
- Delete anything with pervious kernel versions in its name (e.g.```vmlinuz-3.12-1-rpi``` or ```initrd.img-3.12-1-rpi``` etc). Also, if you have it, delete the ```kernel.img``` and ```kernel7.img```.   
- Copy the new kernel and initramfs from /opt/ltsp/armhf/boot to the SD card. They will be named ```kernel.img```, ```kernel7.img```, ```myAwesomeInitramfs3.18.img```.   
- Finally, you need to edit the config.txt file to make sure it knows what to look for when booting. Find the ```initramfs``` line. Change it to ```initramfs myAwesomeInitramfs3.18.img```. If there is a line containing ```kernel```, remove the line.      

You are now ready to boot your Raspberry Pi with your custom kernel. You can use the same instructions to add additional modules you may need.   
Note that PiNet auto updates its kernel files if new version are released by the normal channels, so they may overwrite your kernels, so always keep a backup of them.   
   
**Instructions for building AUFS based off [this excellent blog post](http://rpitc.blogspot.co.uk/p/kernel-rebuild.html).**
