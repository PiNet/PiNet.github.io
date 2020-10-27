---
title: "PiNet End of Life Announcement"
layout: blog
---

![](/assets/images/Raspberry-Pi-kids_PiNet-logo.jpg)

## A bit of background

7 years ago, I started the PiNet project (previously called Raspi-LTSP) to support educators in using Raspberry Pi computers in a real classroom environment, by providing network logins, shared folders, a centralised OS image and much more. This involved building a solution that a complete beginner to Linux could set up and maintain, that would just work day in, day out.   
The cherry on top was then direct (and free) [support](http://pinet.org.uk/articles/support.html) available by email (or later Twitter DMs), when something did go wrong.   

**PiNet has since had over 5000 completed installations** since logs began in 2015. These installations are spread across over 80 countries across the world and even now, there are hundreds of PiNet server check-ins for updates, each month. On top of this, **over 70,000 unique (student) users have been created on PiNet systems!**       
Although PiNet was built for schools, it has been picked up and used by researchers/universities, charities, commercial organisations, the odd postal service and even a prison and hospital.   

To date, I have invested thousands of hours into the project, into everything from writing code, putting together easy to follow documentation for educators (including a [series of videos](https://www.youtube.com/c/PiNetSupport)) and sending over 500 support email responses, to users from every corner of the planet.   

Unfortunately though, as many folks have noticed, my free time to invest in the project has significantly dropped over the past few years.   
Having switched from software development to a full time Computer Science teacher in a London boarding school, the standard work day of 9-5, Monday to Friday went out the window...   
With the new job and a number of other commitments, the amount of time I had available to spend on PiNet plummeted quite dramatically.   

PiNet to date, has yet to earn a penny, given it was never meant to. The project is [fully open source](https://github.com/PiNet) and was always provided free of charge to the community, including support.   

### PiNet end of life
With all of the above in mind, **I don't think it is wise to continue supporting PiNet long term, as I simply don't have the free time anymore.**     
A huge amount of work is outstanding to migrate PiNet to the new LTSP core, along with Raspbian Buster (to bring in support for the Raspberry Pi 4). This is work which I don't have the free time to do anymore.   

As such, I have come to the decision that I will **no longer be maintaining PiNet into the future**.    

**I will though continue to provide [technical support](http://pinet.org.uk/articles/support.html) for the rest of the 2020/2021 academic year** for already established PiNet setups, although this is unlikely to have as quick a turnaround as previous.    

More specifics on all this can be found in the FAQ below.

### Thanks
I want to thank everyone over the years that have been involved with the project. There are far too many to list here, but just a few worth mentioning include
- [Ben Smith](https://twitter.com/ManchesterBudo) - The original "end user" that PiNet was built for as part of my A-Level Computing.
- [Dave Honess](https://twitter.com/dave_spice), [Pete Lomas](https://twitter.com/PeteLomasPi), [Ben Nuttall](https://twitter.com/ben_nuttall) and [James Robinson](https://twitter.com/LegoJames) from the Raspberry Pi Foundation, for their support in the direction of the software.  
- Serge Schneider and [Gordon Hollingworth](https://twitter.com/gsholling) from Raspberry Pi Trading, for their engineering support over the years.   
- Alkis Georgopoulos and Vagrant Cascadian from the LTSP development team, for their significant engineering support (and answering of many many questions on IRC).
- [Tim Golden](https://twitter.com/tjguk) for his repeated engineering support.
- Tim Gamble (Dalriada School) and [John Bustard](https://pure.qub.ac.uk/en/persons/john-bustard) (Queen's University) for their support towards direction for the A-Level Computing project (*Raspberry Pi Classroom and Network Management Software*) and Computer Science degree final year project (*Wireless Network Booting of Low Power Computers*).   
- The entire [Northern Ireland Raspberry Jam](https://twitter.com/NIRaspJam) team, for putting up with my constant testing of new features at Raspberry Jam events.
- The amazing community of educators that were willing to give PiNet and a go and provide feedback. To name a few, [Alan O'Donohoe](https://twitter.com/teknoteacher), [Bob Irving](https://twitter.com/birv2), [Christine Harvey](https://twitter.com/TeachesCompSci) and [Sam Page](https://twitter.com/samdotpage).
- [Amy Mather](https://twitter.com/MiniGirlGeek) and Andy Hunt for their fantastic artwork, used on the website and within the software, along with [John Lemieux](https://www.flickr.com/photos/21051229@N06/7108632527) for his beautiful desktop background, used by PiNet.   

Finally, I want to thank all of the fantastic Raspberry Pi, for their support over the years.    
Although this is the end of the PiNet chapter, it by no means will be the end of my involvement in the Raspberry Pi, open source or CS education communities. I have always had plenty of other projects on the go. Hopefully this will allow me to put a little more time into those other ideas and projects.   

**So to everyone that has supported PiNet over the years, I thank you.**

*-- Andrew Mulholland - PiNet project coordinator*

<br>
<br>


## FAQ

### Why are you EOLing PiNet?
A number of reasons
1. **My free time is nothing like it used to be** when I was a student, especially now I am a full time Computer Science teacher.
2. **PiNet is long overdue a full rewrite.** Although I have attempted starting this, the amount of work involved is huge. This is a much more significant job by:
   - LTSP, of which PiNet is based upon, having been fully rewritten, requiring all PiNet integration to be rewritten.   
   - The migration to Raspbian Buster (to support the Raspberry Pi 4) brought up a significant amount of issues, many of these are still outstanding.   
   - Any new rewrites would have to include a fully supported upgrade pathway from previous versions of PiNet (this is much harder than it sounds).
3. **I simply don't want to keep folks hope up that a new version might land "any day now".** With hundreds of hours of time needed to bring PiNet back up to scratch for classrooms, I am not going to have this amount of time available to me any time soon.   

### I am currently using PiNet, what should I migrate to?
Although it doesn't provide exactly the same functionality, **the closest alternative is [PiServer](https://www.raspberrypi.org/blog/piserver/), from the Raspberry Pi Foundation.**   
PiServer is an excellent tool and very powerful. Although there are some classroom specific features that are missing from it, it does include support for some nice new features that never made their way to PiNet like SD-card-less booting for newer Pi models.   

### I have a PiNet server currently, how long will you continue to provide support?   
I hope to be able to continue providing [email support](http://pinet.org.uk/articles/support.html) for **existing** PiNet servers right up until the end of the 2020/2021 academic year. My hope is that this allows schools currently using PiNet, to continue doing so without interruption in this academic year.   

### What will happen to the PiNet infrastructure?   
My intention is to continue running the PiNet apt repository till the earliest of the end of the 2020/2021 academic year, although it will likely run well beyond that as the cost of doing so is minimal (only around 30GB/40GB a month). The backup mirror though will be retired earlier.   
The code will continue to be available long term, via [Github](https://github.com/PiNet) as usual.   

### I am interested in forking the project and building my own version, can I have some help?   
I should start by warning you, PiNet is a pretty huge project! If you are serious though about updating PiNet though, do feel free to [reach out](http://pinet.org.uk/articles/support.html) with any questions.   
<br>

![](/assets/images/classroom2.jpg)
