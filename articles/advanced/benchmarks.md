---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---

Benchmarks
======
A number of benchmarks have been done with PiNet stacked up against standard Raspbian off an SD card.   
   
The tests use PiNet running on Ubuntu 14.04 on a fully gigabit (10/100/1000) ethernet network. They should be similar on a 100mbit network if the server is connected to the main switch via a gigabit port (also known as a stacking port).   
The local SD card image is running a clean Raspbian 2014.01.07 with the test applications installed.   
I am running only 1 Raspberry Pi on the network so loading time between NFS and NBD should be similar.   
For PiNet there are 2 modes it can be run in    
**1. NFS mode** - NFS is an older network technology. It is uncompressed and so any change made to the master operating system is live on the clients. It is good for testing and monitoring the exact amount of data needed to be loaded for a test to run. It is not recommended for production use due to it being slower than NBD mode. Do not use for more than 8 Raspberry Pis at one time!   
**2. NBD mode** -  Uses NBD and squashFS compression to compress the operating system beforehand. After every change to the master operating system, the OS must be recompressed, which takes roughly 5-10 minutes. It is recommended for production use. The compression normally involves the amount of data cross the network dropping to roughly 40% of what NFS mode uses making it very useful for slower networks or networks running 8+ Raspberry Pis.   
   
The tests were completed on a Raspberry Pi model B revision 2 and the SD card used in these tests was a class 10 SanDisk Ultra card rated at 30MB/s.
##Results
####Boot to login
Test | SD card | NFS | NBD (with compression)   
----|----|----|----   
Time | 35s* |66s| 63s   

####Open Libreoffice Writer   
    | SD card | NFS | NBD (with compression)   
----|----|----|----   
Time | 15s |24s| 20s   
Data crossing network | N/A |75mb| 28mb   

####Open Chromium web browser   
    | SD card | NFS | NBD (with compression)   
----|----|----|----   
Time | 13s |20s| 12s   
Data crossing network | N/A |45mb| 30mb   

####Open Scratch   
    | SD card | NFS | NBD (with compression)   
----|----|----|----   
Time | 6s |7s| 6s   
Data crossing network | N/A |4.7mb| 3.6mb   

####Open Sonic-Pi version 2 RC3   
    | SD card | NFS | NBD (with compression)   
----|----|----|----   
Time | 37s |42s| 36s   
Data crossing network | N/A |11.2mb| 11.1mb   
   

*This is with boot to desktop enabled as LTSP loads a graphical login window.   
