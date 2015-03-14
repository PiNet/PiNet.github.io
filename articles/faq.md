---
title: "PiNet, a system for setting up and managing a classroom set of Raspberry Pis."
layout: article
---

##Frequently asked questions


I get a number of frequently asked questions about PiNet, here are the answers to a few.

- ###How much does PiNet software cost?
PiNet is completely free. The software is free and opensource. It is released under the GNU General Public Licence version 2 which you can view [here](https://raw.githubusercontent.com/pinet/PiNet/master/LICENSE).

- ###Can I run the server off a Raspberry Pi?  
Although there is nothing stopping it in theory, doing this is unsupported and not recommended. The Raspberry Pi only has a 100mbit Ethernet port, 10 times slower than the modern standard available on most computers in the past few years of 1000mbit (or gigabit) Ethernet. This means boots will be slow for more than 1 or 2 Raspberry Pis.

- ###Does it support wifi?
No. PiNet does not support wifi. Wifi is way too slow for this type of thing unless you use an expensive wifi high quality adapter. As most people buy cheap ones that aren't great (although claim to be!), boot speed would be drastically hit. Plus, keep in mind how wifi works. It has a shared bandwidth, for wireless N, the standard is roughly 150mbit/s. This 150mbit/s is shared between all devices on the network (unless using 2 networks via 2.4GHz and 5GHz, in this case you have 300mbit). A Raspberry Pi basically requires 50mbit/s to boot at a decent speed, so you could just about get 3 Raspberry Pis booting. But with wireless you have a number of other overheads and stuff like walls in the way and just general interference dropping the speed further.
To put this into perspective, standard gigabit Ethernet provides 1000mbit/s... 150mbit/s vs 1000mbit/s.
So although it is possible, the amount of work required to integrate common drivers etc into the initramfs and get it all tested massively outweighs the benefits, so no, PiNet does not support wifi.

- ###Is it much slower than running standard Raspbian off a normal SD card?
Other than bootup, for most application no. Bootup takes roughly 30 seconds longer on most networks. For more detailed benchmarks, check out the [benchmark section](advanced/benchmarks).

- ###Is the Raspberry Pi model B+ supported by PiNet?
Yes! As long as you are running at least version 0.7.2.

- ###Is the Raspberry Pi 2 (model B) supported by PiNet?   
Yes! As long as you are running at least version 0.10.42.   

- ###I was running Release 0.10.25 and can't update to newer versions?   
There was a bug in version 0.10.25 which broke the auto updater. If you applied this update, please manually redownload PiNet using ```wget --content-disposition http://pi-ltsp.net/downloadalpha``` followed by ```sudo bash pinet```. This should manually apply the most recent update.   

![](/assets/images/raspi-desktop.jpeg)
