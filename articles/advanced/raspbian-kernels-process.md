---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---

Process to go from Raspbian boot files to PiNet boot files
-----------------------------------

This guide is mainly written as a reminder for the PiNet team on the process of building SD card images for PiNet.   
   
**WARNING** - This guide was written mainly for myself to on steps to build the SD card boot files. The guide may be missing parts or may be out of date. This guide is not an officially supported piece of documentation, follow at your own risk.

##Steps
###Getting up to date files
1. Enter chroot ```sudo ltsp-chroot```.
2. Update the package lists ```apt-get update```.
3. Make sure ```overlay``` is in ```/opt/ltsp/armhf/etc/initramfs-tools/modules```.
4. Download the updated boot file ```wget http://bazaar.launchpad.net/~ltsp-upstream/ltsp/ltsp-trunk/download/head:/ltsp-20111101201947-dgapvhpfim127xu6-2/ltsp -O /opt/ltsp/armhf/usr/share/initramfs-tools/scripts/init-bottom/ltsp```.
3. Install most recent kernel package, simplest way is usually ```apt-get install linux-image-rpi-rpfv linux-image-rpi2-rpfv``` in the Raspbian chroot. If you need to regenerate the initramfs's, uses ```sudo ltsp-chroot update-initramfs -k all -u```.   
4. It also would be a good idea to update the firmware packages, so also run ```apt-get install raspberrypi-bootloader```.   
5. Exit the chroot ```exit```.
6. Clone the current repository ```git clone https://github.com/PiNet/PiNet.git --depth 1```.
7. Make a new folder to work in ```mkdir newBootFiles```.
8. Copy current files from the repository ```cp -r PiNet/boot/* newBootFiles/```
9. Copy new firmware files ```cd /opt/ltsp/armhf/boot``` followed by ```cp -r bcm2708-rpi-b.dtb bcm2708-rpi-b-plus.dtb bcm2709-rpi-2-b.dtb bootcode.bin overlays start_cd.elf start.elf start_x.elf fixup_cd.dat fixup.dat fixup_x.dat /home/$USER/newBootFiles/``` then ```cd```.   
10. Copy the kernels. Remember you will need to change the names if you are using a different version other than 3.18. ```cd /opt/ltsp/armhf/boot``` followed by ```cp vmlinuz-3.18.0-trunk-rpi vmlinuz-3.18.0-trunk-rpi2 initrd.img-3.18.0-trunk-rpi initrd.img-3.18.0-trunk-rpi2 /home/$USER/newBootFiles/``` then ```cd```.   

###Adding OverlayFS support to boot files - No longer needed
This section is kept for reference but is no longer needed.   
   
In the 3.18 kernel release, overlayfs was renamed to overlay, which breaks LTSP support for it. We must manually fetch a more up to date version of the script.
1. Make a new folder to work in ```mkdir pi1Initrd```.   
2. Copy initramfs to the folder ```cp initrd.img-3.18.0-trunk-rpi pi1Initrd/```.
3. Change directory to the working folder ```cd pi1Initrd```.   
4. Unzip the initramfs ```gzip -dc initrd.img-3.18.0-trunk-rpi  | cpio -id```.   
5. Remove initramfs ```rm -f initrd.img-3.18.0-trunk-rpi```.   
6. Grab new script file ```wget http://bazaar.launchpad.net/~ltsp-upstream/ltsp/ltsp-trunk/download/head:/ltsp-20111101201947-dgapvhpfim127xu6-2/ltsp -O /home/$USER/ltsp-script```.   
7. Copy script to required location ```cp /home/$USER/ltsp-script /home/$USER/newBootFiles/pi1Initrd/scripts/init-bottom/ltsp```   
7. Zip the folder back up again ```find . | cpio -o -H newc | gzip -9 > ../initrd.img-3.18.0-trunk-rpi```.   
8. Repeat for Pi2 (initrd.img-3.18.0-trunk-rpi2)      

###Final steps
The boot files should now be ready. Verify the cmdline files have 1.1.1.1 in them and that the config.txt files are correct. Then copy to an SD card and test.   
