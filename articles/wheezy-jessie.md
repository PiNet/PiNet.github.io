---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---

# PiNet Wheezy vs PiNet Jessie
Wheezy and Jessie are words thrown around the Raspberry Pi community frequently. What do they mean and why should you care?   

## What is this Wheezy/Jessie you speak of?
Wheezy and Jessie are both codenames for the Debian operating system releases. As Raspbian is based off Debian, it too uses these same codenames to describe the releases. Think of them kind of like Windows release (XP, Vista, 7, 8 10 etc).     

- Raspbian Wheezy - Released back in 2012 and is classed as very stable, but no longer receiving security updates etc.     
- Raspbian Jessie - Released near the end of 2015, all future updates are only provided for Jessie. Jessie though can suffer from the odd stability issue when new updates are released for it.   

## So how do these releases work with PiNet?   
PiNet has until December 2016, only supported Raspbian Wheezy. There were a number of reasons for this, primarily around stability for educators. This primary issue has been resoled with [a PiNet package repository of its own](https://github.com/PiNet/PiNet/issues/63) allowing the upgrade process to PiNet Jessie progress.  
As of right now (26th Dec 2016), PiNet Jessie is available in Alpha only and **is not recommended** for production use (in a school for example). Over time, the release will make its way to the Beta channel and eventually Stable.   

## What has changed between PiNet Wheezy and PiNet Jessie?   
The short answer, a lot! The slightly longer answer can be found in the [initial release changelog](https://github.com/PiNet/PiNet/commit/07cb9dd5a721bca20167c41c0c0454092b8ff0f0).   

## I want to help test out PiNet Jessie Alpha   
Great, there are 2 separate processes depending on if you already have a PiNet server setup.   

### I already have a PiNet server setup running PiNet Wheezy that I want to upgrade.   
1. Open a terminal on your PiNet server and type the following commands.   
  ```cd ~```  
  ```wget https://raw.githubusercontent.com/PiNet/PiNet/wheezy-alpha/pinet```   
  ```wget https://raw.githubusercontent.com/PiNet/PiNet/wheezy-alpha/Scripts/pinet-functions-python.py```      
  ```sudo mv pinet-functions-python.py /usr/local/bin```    
  ```sudo bash pinet```   

2. Follow onscreen instructions to upgrade. Make sure to select Alpha as your release channel.   
   
### I want to set up a fresh PiNet server with PiNet Jessie.  
1. Follow the normal [installation instructions for Ubuntu](installation/installing-ubuntu.html), then open a terminal and run the following commands.   
  ```cd ~```   
  ```wget --content-disposition http://links.pinet.org.uk/jessie-alpha-pinet```   
  ```sudo bash pinet```    

2. Follow onscreen instructions for the installation. Make sure to select Alpha as your release channel.    

## Found a bug or got feedback on PiNet Jessie?   
Fantastic! The best bet is report it by opening a [Github Issue](https://github.com/PiNet/PiNet/issues). You can also simply drop support an email/tweet etc. Details for getting in contact can be found on the [support page](support.html).   
