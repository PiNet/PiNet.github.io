---
title: "PiNet Jessie testing with Raspberry Pi 3!"
layout: blog
---

![](/assets/images/jessie.jpg)

## PiNet Jessie   
For the past few months, I have been working on getting Raspbian Jessie across to PiNet. Right now, PiNet uses Raspbian Wheezy, moving from Wheezy to Jessie requires a full Raspbian rebuild which logistically is a pain. The Raspberry Pi Foundation for example only provided new SD card images with no way to directly upgrade from Wheezy to Jessie.   
With PiNet though, I would prefer if it would be possible to make the upgrade as seamless as possible, avoiding the need for a full PiNet server reinstall.   
Because of this, the upgrade has taken quite a while, especially the testing.    
As many PiNet users know, with PiNet, reliability and stability are far more important than new features, hence why updates to the new latest and greatest new features can take a while.   
So, before releasing PiNet Jessie to the main release channels, I am in need of some help to help test PiNet Jessie!   

## What awesome new features do I get?   
A great question, quite a few actually.   
- New latest and greatest software updates for most of the packages on Raspbian.   
- New firmware updates **including support for the Raspberry Pi 3!**.   
- Support for Sudoless GPIO.    
- NuScratch support (with builtin GPIO support).   
- Ability to run the PiNet control panel (and Epoptes) from a Raspberry Pi.   
- Remove users via CSV file support.   
- Greenfoot and BlueJ built in.   
- Lots of bug fixes.   

## Raspberry Pi 3!    
Yes, you read right, PiNet Jessie supports Raspberry Pi 3 Model B! Unfortunately not using Wifi [(see FAQ for why not)](http://pinet.org.uk/articles/faq.html#does_it_support_wifi).   
It should simply work out of the box with PiNet and a micro sd card. Although the Raspberry Pi 3 does have support for PXE style network booting without an SD card, right now the required supporting firmware and documentation from Raspberry Pi Foundation is not yet available.   
Interested in some benchmarks with the Raspberry Pi 3 vs older Pis on PiNet? Check out the newly updated [benchmarks page](http://pinet.org.uk/articles/advanced/benchmarks.html).   


## I want to help test!    
Awesome, thanks! Before you do so though, a few warnings.   
- It probably has some bugs... Although I have [tried to test everything using a very long list of tests](http://goo.gl/forms/knSsUUXr57), I am bound to have missed something.    
- **Do not use in a production environment!** - This includes for day to day use in schools with classes or workshops. Small afterschool clubs or internal testing is fine though, but make sure to have a backup in place just in case!   
- If you find some bugs, please open a [Github issue](https://github.com/PiNet/PiNet/issues). It is very important you mention you are testing PiNet Jessie.   

If you are still happy to go ahead with testing, install PiNet as normal, then follow the documentation on the [custom branches](http://pinet.org.uk/articles/advanced/custom-branches-repositories.html) page to switch over to the ```jessiedev``` branch.   
