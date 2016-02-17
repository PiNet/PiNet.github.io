---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---

Configuring automatic backups
-----------------------------

PiNet includes an automated backup system. This separate piece of
software runs in the background at set times. Overall the system is
still in Alpha currently so it is recommended you also consider running
a full system backup regularly on top of these backups.

Note that these backups only back up the /home folder, aka all the users
files. The operating system is not backed up, nor is the Raspberry Pi
operating system backed up (this can easily be recreated later).

You should not save backups onto the same hard drive as you installed
Ubuntu and PiNet onto. Backups should be saved onto an external
hard drive for example.

## Configuring a backup

1.  Select backup-Menu.    
    ![](/assets/images/image57.jpeg)

2.  Note the warning and select ok.    
    ![](/assets/images/image58.jpeg)

3.  Select “Configure-backup” to launch the backup configuration wizard.   
    ![](/assets/images/image59.jpeg)

4.  Read the information box and select ok.   
    ![](/assets/images/image60.jpeg)

5.  Navigate to the folder you wish to save your backups in. External
    drives are mounted to /media/Username so you start in /media. To
    move up one level, select ../. To select this folder, select ./.   
    ![](/assets/images/image61.jpeg)

6.  Next decide how often you want the backup to run. Twice weekly is a
    good middle ground if you are unsure.    
    ![](/assets/images/image62.jpeg)

7.  Next select how long backups should be kept. The old backup checker
    only runs every time a new backup is made, so backups may sit a
    little longer than the chosen time. A good middle ground if you are
    unsure is Thirty days.    
    ![](/assets/images/image63.jpeg)

8.  The backup is now configured. It is very important you check
    Display-Logs in the Backup-submenu to check the backup has been
    successfully configured. You should check this regularly as any
    failed backups and their corresponding reasons will be displayed.   
    ![](/assets/images/image64.jpeg)

9.  To check the log file, select Display-Logs from the Backup-Submenu.   
    ![](/assets/images/image65.jpeg)

10. The log will be displayed in chronological order. Check the backup
    has been configured and the folder selected is correct. It is
    important to check this every week or 2.   
    ![](/assets/images/image66.jpeg)
