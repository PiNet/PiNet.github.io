---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---
# PiNet Metrics   
Starting with PiNet Release 1.0.18, PiNet collects very basic stats/metrics when it "phones home" to check for updates. The metrics are are sent over an [encrypted SSL/TLS connection](http://www.networking4all.com/en/support/tools/site+check/report/?fqdn=secure.pinet.org.uk).    
The reason for the metrics is to allow us to see the usage of PiNet across the world and it will allow us to prioritise internationalisation/localisation for countries with a large number of PiNet servers.    

## What data is collected?   
The following data is by default collected and uploaded.     
- PiNet version   
- Raspbian kernel version being used   
- Number of users added to the system   
- Selected release channel (Stable or Dev)   
- A randomly generated unique server ID   
- Server external IP address   

## I want to disable general stats/metrics uploading   
You can disable the uploading of the stats/metrics by adding   
```DisableMetrics=true``` into your PiNet config file, which is by default located at ```/etc/pinet```.    
PiNet will still send your randomly generated unique ID, the PiNet version and external IP address, but the rest of the metrics will simply be set as empty.   

## I want to disable all stats/metrics uploading/collecting   
The only way to disable all stats/metrics being uploaded/collected is to disable PiNet automatic update checking, you can still though manually check for updates.   
It is recommended you keep automatic update checking enabled to get the most current PiNet bug fixes and security releases.    
To disable all update checking and status/metrics, add ```DisableUpdateChecking=true``` to your PiNet config file, which is by default located at ```/etc/pinet```.    
