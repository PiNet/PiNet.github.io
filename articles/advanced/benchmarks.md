---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---

Benchmarks
======
A number of benchmarks have been done with PiNet stacked up against standard Raspbian off an SD card.   
   
The tests use PiNet running on Ubuntu 14.04 on a fully gigabit (10/100/1000) ethernet network. They should be similar on a 100mbit network if the server is connected to the main switch via a gigabit port (also known as a stacking port).   
The local SD card image is running an unmodified Raspbian Jessie 2016.02.26 with the test applications installed.   
   
The tests were completed on a Raspberry Pi model B+, Raspberry Pi 2 Model B and Raspberry Pi 3 Model B and the SD card used in these tests was a class 10 Kingston card rated at 30MB/s.
## Results
#### Boot to login (or to desktop in standalone card case)
Test | PiNet | SD card
----|----|---- 
Pi 1B+ | 49s | 42s    
Pi 2B | 20s | 20s   
Pi 3B | 18s | 18s   

#### Login to desktop from login screen
Test | PiNet | SD card
----|----|---- 
Pi 1B+ | 45s | N/A   
Pi 2B | 11s | N/A   
Pi 3B | 12s | N/A   

#### Open Libreoffice Writer   
Test | PiNet | SD card
----|----|---- 
Pi 1B+ | 29s | 27s   
Pi 2B | 12s | 11s   
Pi 3B | 9s | 9s    

#### Open Scratch   
Test | PiNet | SD card
----|----|---- 
Pi 1B+ | 14s | 12s   
Pi 2B | 6s | 6s   
Pi 3B | 4s | 4s   

#### Open Sonic-Pi 2.9
Test | PiNet | SD card
----|----|---- 
Pi 1B+ | 47s | 42s   
Pi 2B | 20s | 20s   
Pi 3B | 16s | 16s  

## Conclusion 
As can be clearly seen int he data, on many occasions booting from the local SD card is faster, especially with the old Raspberry Pi 1 Model B and B+. But, when you get to the Raspberry Pi 2 Model B and Raspberry Pi 3 Model B, the difference is barely noticeable with any of the applications.   
Is important to keep in mind, PiNet is more though about saving time in management of the Raspberry Pis and less so about optimising individual Raspberry Pi speeds. The amount of time wasted for example swapping cards between classes alone usually negates any speed improvements with standalone cards, let alone having to keep them up to date and backed up.
   
This page was last updated on 4th March 2016.   
