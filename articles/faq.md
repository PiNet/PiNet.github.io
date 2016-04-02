---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---

## Frequently asked questions


I get a number of frequently asked questions about PiNet, here are the answers to a few.

- ### How much does PiNet software cost?
PiNet is completely free. The software is free and opensource. It is released under the GNU General Public Licence version 2 which you can view [here](https://raw.githubusercontent.com/pinet/PiNet/master/LICENSE).

- ### Can I run the server off a Raspberry Pi?  
Although there is nothing stopping it in theory, doing this is unsupported and not recommended. The Raspberry Pi only has a 100mbit Ethernet port, 10 times slower than the modern standard available on most computers in the past few years of 1000mbit (or gigabit) Ethernet. This means boots will be slow for more than 1 or 2 Raspberry Pis.

- ### Does it support wifi?
No. PiNet does not support wifi. Wifi is way too slow for this type of thing unless you use an expensive wifi high quality adapter. As most people buy cheap ones that aren't great (although claim to be!), boot speed would be drastically hit. Plus, keep in mind how wifi works. It has a shared bandwidth, for wireless N, the standard is roughly 150mbit/s. This 150mbit/s is shared between all devices on the network (unless using 2 networks via 2.4GHz and 5GHz, in this case you have 300mbit). A Raspberry Pi basically requires 50mbit/s to boot at a decent speed, so you could just about get 3 Raspberry Pis booting. But with wireless you have a number of other overheads and stuff like walls in the way and just general interference dropping the speed further.
To put this into perspective, standard gigabit Ethernet provides 1000mbit/s... 150mbit/s vs 1000mbit/s.
So although it is possible, the amount of work required to integrate common drivers etc into the initramfs and get it all tested massively outweighs the benefits, so no, PiNet does not support wifi.

- ### Is it much slower than running standard Raspbian off a normal SD card?
Other than bootup, for most application no. Bootup takes roughly 30 seconds longer with the Raspberry Pi 1 (including B+) on most networks. The new Raspberry Pi 2 though boots just as fast as from an SD card, off the PiNet server. For more detailed benchmarks, check out the [benchmark section](advanced/benchmarks).

- ### Is the Raspberry Pi model B+ supported by PiNet?
Yes! As long as you are running at least version 0.7.2.

- ### Is the Raspberry Pi 2 (model B) supported by PiNet?   
Yes! As long as you are running at least version 0.10.42.   

- ### Is the Raspberry Pi 3 (model B) supported by PiNet?   
Partially right now. The Raspberry Pi 3 model B is supported in PiNet 1.1.12 and beyond. This is currently only available in the [jessiedev branch](advanced/custom-branches-repositories.html).        

- ### I was running Release 0.10.25 and can't update to newer versions?   
There was a bug in version 0.10.25 which broke the auto updater. If you applied this update, please manually redownload PiNet using ```wget --content-disposition http://pi-ltsp.net/downloadalpha``` followed by ```sudo bash pinet```. This should manually apply the most recent update.   

- ### I see "LTSP" mentioned in a number of places, what is it?   
The [Linux Terminal Server Project (LTSP)](http://www.ltsp.org/) is the base that PiNet is built upon. It includes a number of scripts for setting up and managing thin and fat clients. It has the issue though that the documentation for it is limited and is all managed from the commandline. Another major issue is that the Raspbian SD card images provided by the Raspberry Pi Foundation are very heavily tweaked versions of base Raspbian. These tweaks need to all be added afterwards when simply using LTSP itself.   
To get around the difficulties of LTSP for new users and to add the required tweaks, PiNet (previously RaspberryPi-LTSP) was born. It adds an easy to use graphical frontend to the system and includes a number of extra features including shared folders, student work handin and automated backups.   
PiNet was built with help and support from a number of the awesome LTSP developers. The list can be found in the [thanks section](thanks.html).

![](/assets/images/raspi-desktop.jpeg)
