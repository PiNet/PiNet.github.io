---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---
# Using custom Git branches/repositories with PiNet   
By default, when checking for updates, PiNet will look to ```https://github.com/pinet/pinet``` and will either use the Master (stable) branch or Dev (development) branch.   
As of PiNet 1.1.7, both these are manually changeable via the PiNet config file.    

## Changing PiNet branch    
New experimental versions of PiNet may be released on different branches from the usual Master and Dev branches. To easily use these, you will need to tell PiNet about it.   
**Warning** - You must verify that the branch actually exists! You can do so by opening the following URL in a web browser (replacing branchname with your custom branch name) ```https://github.com/PiNet/PiNet/tree/branchname```.   
In this example, we will switch to the ```jessiedev``` branch, the experimental Raspbian Jessie build.   
1. On the server, open the PiNet configuration file with nano by running the following in a terminal ```sudo nano /etc/pinet```.    
2. Locate the ```ReleaseChannel=``` line.   
3. Change the section after the equals sign to ```custom:jessiedev```. So the line should now read ```ReleaseChannel=custom:jessiedev```
4. Save and close the file (using ctrl+x followed by y followed by enter)    

## Changing the used Github repository   
If you wish to use a custom Github repository, perhaps you want to write some custom PiNet code or test some possible new feature code using your own repository.   
You can do this, although it is a little complicated.
1. Make sure you have a repository with a similar structure to the normal [PiNet repository](https://github.com/pinet/pinet). It is far easier to start by forking the repository.   
2. You also must make sure you have a fork of the [PiNet boot repository](https://github.com/PiNet/PiNet-Boot)!
3. Open the PiNet config file (found at /etc/pinet) on the PiNet server and add 2 new values at the bottom, ```RepositoryBase=``` and ```RawRepositoryBase=```. **It is essential that you also have ```RawRepositoryBase=```!**     
4. Set these to your Github account root, then that is it. For example for myself it would be
```
RepositoryBase=https://github.com/gbaman
RawRepositoryBase=https://raw.github.com/gbaman
```
