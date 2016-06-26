---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---

User data migration
----
PiNet includes a migration utility for migrating user data out of your server for transferring to another PiNet server.    
This can be especially useful if you want to reinstall your server or move it to a new piece of hardware but don't want to manually recreate all your users and copy their data across manually.   
   
It is also required if you are moving from a previous RaspberryPi-LTSP server to PiNet (which requires a fresh reinstall).
   
**Note** - You are responsible to check all data has been transferred correctly.

1. Open PiNet or Raspi-LTSP and select ```manage-users```.   
![](/assets/images/migration1.jpeg)   
2. Then select ```Export users```.   
![](/assets/images/migration2.jpeg)   
3. Select ```Yes``` to proceed after reading the warning dialog box.   
![](/assets/images/migration3.jpeg)   
4. PiNet (or Raspi-LTSP) will then go away and zip up all the users home folders, the users file, the passwords (encrypted) file and the groups file into a single zip file called toMove.tar.gz which is stored in your home folder ready to be transfered. Select OK.   
![](/assets/images/migration4.jpeg)   
5. Open up the file manager and find the ```toMove.tar.gz``` file.     
![](/assets/images/migration5.jpeg) 
6. Right click the file and select ```Copy```.     
![](/assets/images/migration6.jpeg)   
7. Insert your flash drive or external hard drive into the server. It should pop up. Right click and select ```Paste```. Once the file is copied, eject the removeable media.    
![](/assets/images/migration7.jpeg)   
8. Follow the [Ubuntu 16.04 install guide](../installation/installing-ubuntu.html) as normal on the new server.   
9. Insert your flash drive or external hard drive into the new server and copy and paste the toMove.tar.gz file into your home folder.  
10. When you start PiNet for the first time, it will ask if you want to import user data, select ```yes```. When it asks to reboot, select ```yes```.   
11. Continue on as normal with the [installing PiNet guide](../installation/installing-PiNet.html) as usual.   
   
And don't forget, **if you are having issues with this process, feel free to drop me a message** via the contact details found on the [Support page](../support.html).   
