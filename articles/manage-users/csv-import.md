---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---

#Import users from CSV file

PiNet includes a utility to batch import users from other systems using a CSV file. It was initially designed for use with SIMS.net, but there is no reason it couldn't be used with any application that can export users as a CSV file.   

##Data format
The CSV file must be in the form of an MS-DOS Comma Separated Values file (Microsoft Excel) or a Text CSV file (Libreoffice). Other CSV file formats may not be supported.   
   
The formatting required is very simple   

1 | 2
--- | ---   
Username | Password   
Username | Password   
Username | Password   
   
Or just  
  
1 | 2
--- | ---   
Username |   
Username |    
Username |  

An example CSV file can be found [here](/assets/images/csvExample.csv).
   
<iframe width="960" height="720" src="https://www.youtube-nocookie.com/embed/3v8U76s3kEs?start=22" frameborder="0" allowfullscreen></iframe>
   
##Importing CSV file

You will be asked to enter a default password when importing the users, if any of your users don't have an attached password (in column 2), then the selected default password will be used.   

1. Open PiNet and select ```Manage-Users```.   
![](/assets/images/csv-import1.jpeg)  
  
2. Select ```Import-Users```.   
![](/assets/images/csv-import2.jpeg)    

3. Select ```Yes``` to continue.   
![](/assets/images/csv-import3.jpeg)    

4. Select Ok to continue.   
![](/assets/images/csv-import4.jpeg)    

5. Using the folder navigator, select the .csv file you have copied to the server. All folders are preceeded by a ```/``` and to move up a folder, select ```../```.      
![](/assets/images/csv-import5.jpeg)    

6. Next, enter a password to use as the default password if any of the users don't have a password assigned to them.   
![](/assets/images/csv-import6.jpeg)    

7. Finally, verify the correct credentials for each user are shown on screen. If you are happy with them, select ```import```. If not, select ```cancel``` and double check your CSV file, make sure you have followed the required pattern.   
![](/assets/images/csv-import7.jpeg)    

8. The users will then be imported 1 by 1 and once the process is complete, a dialog box will be displayed informing you it is complete.   
![](/assets/images/csv-import8.jpeg)    
