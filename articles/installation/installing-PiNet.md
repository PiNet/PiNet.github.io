---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---

Installing PiNet
---------------------
#### **Warning** - Make sure you are installing PiNet onto a fresh installation. **Do not** install PiNet onto an Ubuntu installation running other services as PiNet can not be easily uninstalled.   
   
Now you have an Ubuntu 16.04 server setup, it is time to actually install PiNet. PiNet is run through a terminal.
This allows you use it locally or even run the software over SSH!
Lets get started!

1.  Once the machine reboots, login with your credentials you set up
    earlier.   
    ![](/assets/images/PiNet/Install/01_Login.jpg) 

2.  Select the search button in the top left corner.   
    ![](/assets/images/PiNet/Install/02_Search_your_computer.jpg) 

3.  Search for and select “Terminal”. You can also just hit Ctrl + Alt +
    T.   
    ![](/assets/images/PiNet/Install/03_termintal.jpg) 

4.  You will then be presented with a terminal. PiNet runs inside a
    terminal window. You may find it useful to resize the terminal
    window to make it larger or put it in full screen.   
    ![](/assets/images/PiNet/Install/04_show_terminal.jpg) 

5.  Enter ```wget --content-disposition http://bit.ly/pinetbeta```
    and hit enter. This downloads the PiNet script. The main script is called ```pinet```.    
    (note the all new PiNet Jessie is now available in [Beta for testing](../wheezy-jessie.html).)    
    ![](/assets/images/PiNet/Install/05_wget_pinet.jpg) 

6.  Once that completes, enter ```sudo bash pinet``` which will launch
    PiNet. A desktop icon will be created when the software installs but 
    you can always use this command to manually launch PiNet.   
    ![](/assets/images/PiNet/Install/06_sudo_bash_pinet.jpg) 

7.  Enter your password as the application must be run as administrator 
    (nothing will look like it is being entered, this is a Linux security feature so don't worry, it is being entered).   
    ![](/assets/images/PiNet/Install/07_sudo_password.jpg)   
          
8.  PiNet will offer to run a full install, select yes.  
    ![](/assets/images/PiNet/Install/10_Pinet_Welcome.jpg)   
    
9. PiNet supports importing user data from an older PiNet server. 
    See the [migration guide](../manage-users/migration.html) for details. Select No.   
    ![](/assets/images/PiNet/Install/11_Pinet_Importing_Users.jpg)   

10. Select which release channel you wish to use. If using in a production environment, it is recommended you
    select Stable. If you wish to test out new bleeding edge features, select Development.   
    ![](/assets/images/PiNet/Install/12_Release_channels.jpg)   


11. Select Ok to continue after reading how to select additional software.     
    ![](/assets/images/PiNet/Install/13_Additional_Software.jpg)   
    

12. Select any extra software you wish to include.  
    ( Screenshot shows several non-default selections)    
    ![](/assets/images/PiNet/Install/14_Extra_Software_Submenu.jpg)   

13. If extra software specified, select Yes to confirm  
    ![](/assets/images/PiNet/Install/15_Extra_Software_Are_you_sure.jpg)   
    
14. If extra software 'Custom-package' selected, enter package name.  
    ![](/assets/images/PiNet/Install/16_Custom_package.jpg)   

15. If extra software 'Custom-python' selected, enter package name.  
    ![](/assets/images/PiNet/Install/17_Custom_python_package.jpg)   
    
16. The install will take roughly 1-2 hours depending on processor speed
    and internet speed. Select ok and it will start the installation.
    You can now leave it to work.   
    ![](/assets/images/PiNet/Install/18_Full_Install_info.jpg)

17. After 1-2 hours, select choice whether to give students Sudo access on
    the Raspberry Pi. If you intend to work with the GPIO pins on the
    Raspberry Pi they will need it. You can really easily later enable
    or disable Sudo use in the Manage-Users submenu in the main software
    options. If in doubt, is recommended to enable it by selecting yes.   
    ![](/assets/images/PiNet/Install/19_Warning_Give_students_sudo.jpg)   

18. If using 2 network interface cards then check the IP address is
    correct. If you are only using 1 (most people), then the default
    will likely be correct. Select yes.   
    ![](/assets/images/PiNet/Install/20_IP_Address.jpg)   

19. Select OK after reading notice about collected statistics.
    ![](/assets/images/PiNet/Install/21_Stats_usage_clean.jpg)   
    
20. Select OK after reading notice about additional information.
    ![](/assets/images/PiNet/Install/22_Additional_Information.jpg)   
        
21. (Optional) Select OK after entering nearest major city.
    ![](/assets/images/PiNet/Install/23_Nearest_major_city_2_with_OK.jpg)   
            
22. (Optional) Select OK after entering organisation type.
    ![](/assets/images/PiNet/Install/24_Organisation_type.jpg)   

23. (Optional) Select OK after entering school/organisation name.
    ![](/assets/images/PiNet/Install/25_School_Org_name.jpg)   

24. Select OK after reading how to edit additional information.
    ![](/assets/images/PiNet/Install/26_Additional_info_thanks.jpg)   
    
25. The operating system will now be compressed. After every change made
    to the operating system, it must be recompressed which takes roughly
    5 minutes normally. Select ok.   
    ![](/assets/images/PiNet/Install/27_Compression.jpg)

26. PiNet installation is now complete. The server has generated an
    SD card image which is located in /home/YourUser/piboot.
    You need to copy these files onto a blank formatted SD card and
    connect the Raspberry Pi to the network.   
    ![](/assets/images/PiNet/Install/28_Main_install_complete.jpg)

27. You are recommended to check the Backup section of this manual on
    setting up an automatic backup of your students work to an external
    hard drive in case of hard drive failure.   

## Copying to SD card
Now that you have installed PiNet, you need to [copy the boot files to an SD card](sd-card-copy.html).
