---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---
# Web filtering  
If your school or organisation uses web filtering/blocking, it may be a good idea to manually whitelist the domains PiNet needs to access to install and build the Raspbian chroot.   
- raspbian.org   
- raspberrypi.org   
- github.com   
- bitbucket.org   
- bluej.org   
- bit.ly     
- ubuntu.com   
    
If you are unable to whitelist these domains, consider doing the initial installation on an unfiltered internet connection. It is recommended that you connect your PiNet server to an internet connection with access to these domains at least once every 3 months for updates.      

## Proxies   
Many schools and organisations use proxies to route the web traffic through a filter. Although proxies are not officially supported with PiNet, it is easy to manually add them to Raspbian and Ubuntu.  

### Ubuntu   
In Ubuntu, search for ```proxy``` and select ```Network```    
![Searching for proxy](/assets/images/ubuntu-proxy-1.jpg)   
Then enter your network settings and click ```Apply system wide```.   
![Adding proxy settings](ubuntu-proxy-2)   

### Raspbian   
Adding proxy settings into Raspbian is a little more complicated. Make sure to read over the [Editing outside](editing-outside.html) guide as it includes a little more information about directly editing the Raspbian chroot.   
1. Open a terminal on the Ubuntu server and enter ```sudo ltsp-chroot --arch armhf``` to enter the Raspbian chroot.   
2. Enter ```nano /etc/apt/apt.conf.d/10proxy``` to create a text file there and open it with the nano text editor.   
3. Add in ```Acquire::http::Proxy "http://username:password@proxy_server_address:port"; ``` where you have changed the details, for example ```Acquire::http::Proxy "http://username:password@10.0.0.1:8080"; ```   
If your proxy does not include authentication, use this instead ```Acquire::http::Proxy "http://proxy_server_address:port/";
```.   
   
Some applications ignore this and for those, you may need to search the web for an answer.   
