---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---

Hardware   
--------   

To set up a PiNet classroom network, hardware is commonly a stumbling block. Below explains the type of hardware you need for different setups and a few suggestions.   

<iframe width="960" height="720" src="https://www.youtube-nocookie.com/embed/Wyy8wb2D_y4?rel=0" frameborder="0" allowfullscreen></iframe>   

## PiNet Server  
A common misconception is that a PiNet server needs to be a beefy, powerful desktop machine with many processor cores, stacks of RAM and a super fast SSD.    
In fact, PiNet requires extremely limited resources to run by default.   
There are though some limited use cases where the server does need to be powerful.    

### So what type of PC hardware do I need for my PiNet server?    
This is an extremely wide ranging question and it is impossible to say. A few rough guidelines though for a class set (20) Raspberry Pis would be.  
#### Minimum   
- Single core 1GHz processor (Intel Celeron or greater)   
- 1GB of RAM   
- 20GB of hard disk space   
- A gigabit ethernet port (100mbit/s is not officially supported)

#### Recommended 
- Duel core 1.5GHz processor (Intel Pentium or greater)   
- 2GB of RAM   
- 40GB of hard disk space   
- A gigabit ethernet port (100mbit/s is not officially supported)   

#### Large setup recommended (80+ Pis)
- Duel core 2GHz processor (Intel Core I3 or greater)   
- 4GB of RAM   
- 40GB of hard disk space   
- A gigabit ethernet port (100mbit/s is not officially supported)  
   
For anything greater than 100 Raspberry Pis, it would be recommended to look into port trunking or 10gbit/s core networking.   

### Remoteapps   
PiNet has built in support (from LTSP) for Remoteapps. Remoteapps allows you to run applications on the server and share them with the Raspberry Pis. This is great when you have an application that is only available for x86 or is too heavy for the Raspberry Pi usually.   
If using Remoteapps, it hugely depends on the application being used remotely and by how many users. Linux can be pretty smart with sharing memory etc if users are all using the same application, but if different applications are in use, then large amounts of RAM may be required.   

## Networking   
As well as having sufficient server hardware, networking equipment is also required.   
Networking equipment operates at a number of different speeds including   
- 10mbit/s (1.25 megabytes per second)   
- 100mbit/s - Fast Ethernet (12.5 megabytes per second)    
- 1000mbit/s - Gigabit Ethernet (125 megabytes per second)   
- 10000mbit/s - 10 Gigabit Ethernet (1250 megabytes per second)   

PiNet requires at least 1000mbit/s (Gigabit Ethernet) from the server to a network switch.   
Although 100mbit/s (Fast Ethernet) may work for 2-3 Raspberry Pis, it is not supported officially with PiNet.   

### Router   
The first piece of equipment you are going to need is an old router. Chances are you have an old one sitting around the house.   
Routers typically have 4-5 Gigabit Ethernet ports on the back and make for a great starting point to try out PiNet with a few Pis.   
Even for the larger setup though, you still need a router somewhere on the network. The router is used for DHCP (assigning IP addresses to each device on the network). If though you are connecting in to another network (for example a school network), it will already have a router.   
** WARNING ** - Never have more than 1 router (or DHCP server) on a network, they will conflict.   

### Switch  
Networks are made up of network switches. They typically have 8, 16, 24 or 48 ports and will operate at the speeds above. With some switches, all the ports run at the same speed.   
Other switches include "uplink" or "trunking" ports. These ports are usually 1 level higher speed wise and are used to connect to servers or other switches.   
   
For example, it is very common to find network switches which have 22 100mbit/s ports, along with 2 1000mbit/s (Gigabit) ports. These are perfect for PiNet, as you can connect the server into one of these Gigabit ports and Raspberry Pis into the other 22 100mbit/s ports.   

### Networking rules   
When you get beyond a single switch and router, your core network becomes extremely important. A few rules to consider when building your network.   
- All core links should be at 1 Gigabit - This includes from server to switch and from switch to any other switches.
- Never daisy-chain switches more than 2 levels - Daisy chaining switches can create sizable bottlenecks if done wrong. A general rule of thumb is to stick to 2 levels max from the source of the data. For example, a main core switch and one additional level off it.   

### Example network   
![](/assets/images/network1.png)   
The example network above is a common setup for PiNet networks. It can be broken down into multiple sections.   
- A core switch (with all core links to other switches and the server connected to Gigabit ports).   
- A PiNet server (connected via Gigabit ethernet to the core switch).   
- Additional switches (connected via Gigabit ethernet to the core switch).   
- A router connected to the internet (connected to core switch by 100mbit/s, or optional Gigabit port).   
- Raspberry Pis (connected to any of the switches by at least 100mbit/s port).   
   
### Buying equipment   
Buying networking equipment can be difficult. There are so many different brands and types, it can be very difficult to find the correct hardware.   
For a simple standalone PiNet network with 20 Raspberry Pis, the recommended setup is   
- x1 old router.   
- x1 100mbit/s 24 port switch with x2 Gigabit "stacking"/"trunking" ports (can be picked up second hand on eBay for ~£20).   
- x1 Old desktop or laptop with above recommended specs.   
- A box of Ethernet cables.   
   
For a network with 21-40 Raspberry Pis you can also get away pretty cheaply by copying the list above, just adding an additional switch as described then using the extra one of the x2 Gigabit ethernet ports on your core switch to link up your 2nd switch.   

If you have any questions around PiNet hardware/networking, feel free to get [in touch](../support.html).
