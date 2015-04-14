---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---

#Boot issues
There are a number of reason your Raspberry Pi may fail to boot from the PiNet server.   

##Blank screen or rainbow screen
If you get a blank screen or a rainbow screen, this is most likely to be 1 of 2 possible issues

###Incorrectly formatted SD card
If the SD card does not have a FAT partition as the 1st partition with all the generated boot files, the Raspberry Pi will fail to load. The fix for this is reformat the entire card. See the [SD card guide](../installation/sd-card-copy.html) for how to do this.   

###Corrupt or missing boot files
If the SD card is formatted correctly, but the boot files are corrupt or missing, it will also fail to boot. Check the config.txt file and check the files defined after ```kernel``` and ```initramfs``` exist on the SD card root. If in any doubt, copy the entire folder over from the server PiBoot folder again.   

##It starts up but never reaches the login screen
This usually means it can't correctly connect to the PiNet server. This can be identified by if the console shows ```Giving up``` errors or if it drops out into an ```(initramfs)``` prompt.   

###Check the cmdline.txt file
As the server IP address is saved in the cmdline.txt file on the SD card, make sure it is correct. You can view the server IP address by opening PiNet. It is displayed in the top right. Check that this is the same as on the SD card in the cmdline.txt file. If not, change it to the correct address.   

###Can you ping the server?
If you are dropped out into an ```initramfs``` shell, trying entering ```ping``` followed by the server IP address from above. You should get something like ```64 bytes from...``` which means it is receveing a reply. If you get ```Request timeout for icmp_seq...``` then there isn't a direct link between the Raspberry Pi and the server. Check your cables. Is there perhaps some sort of firewall in the middle?   

###Check the OS installed correctly    
On the server, open a terminal and enter ```ls /opt/ltsp/armhf```.
If you see a folder titled ```debootstrap``` then this means the PiNet software failed to correctly build Raspbian. This usually happens because the internet drops out half way through or your network is blocking access to part of the Raspbian repositories.   
To fix this issue, it is highly recommended you start from the start again, reinstalling Ubuntu then PiNet to make sure everything is cleared out.   
If it continues to fail, try installing PiNet using a different internet connection, perhaps try taking the server home?

##I have an error not listed here or suggestions aren't working
If these suggestions don't help, you may want to contact [support](../support.html).
