---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---

PiNet releases   
--------   

PiNet runs alongside the Raspberry Pi Foundations Raspbian releases. These releases are in turn based upon [Debian's releases](https://www.debian.org/releases/). Each major release has a codename which the Raspberry Pi Foundation and PiNet also use to mark their versions with.   

## Upgrading   
PiNet includes built in support to upgrade from different releases while still keeping user data in place. When a new major version is made available, PiNet will prompt to install it.   

{% include info.html title="Custom Configuration" message="Any custom configuration changed made or software installed on the Raspbian installation will be wiped on a major release upgrade. This will be explained in the upgrade dialog box further."%}
   
   
## PiNet release support
The following versions have been released by the Raspberry Pi Foundation.   
### Stretch   
  - Released by Raspberry Pi Foundation in June 2017.
  - Not currently supported by PiNet.
  - Soon to be available in [Stable](https://github.com/PiNet/PiNet/tree/stretch-stable), [Beta](https://github.com/PiNet/PiNet/tree/stretch-beta) and [Alpha](https://github.com/PiNet/PiNet/tree/stretch-alpha) releases.
  - Release PiNet 1.3.x onwards. (not yet available)
  - Status can be followed [over on the Github Issue](https://github.com/PiNet/PiNet/issues/142).
  
### Jessie   
  - Released by Raspberry Pi Foundation in September 2015.
  - No longer receiving updates from the Raspberry Pi Foundation, but receiving updates from the Debian team.
  - Recommended version of PiNet.
  - Available in [Stable](https://github.com/PiNet/PiNet/tree/jessie-stable), [Beta](https://github.com/PiNet/PiNet/tree/jessie-beta) and [Alpha](https://github.com/PiNet/PiNet/tree/jessie-alpha) releases.
  - Release PiNet 1.2.x onwards.
  - [Debian Long Term Support](https://www.debian.org/News/2016/20160425) team security support provided until 30th April 2020.
  - PiNet support provided until at a minimum of 30th September 2018.
  - Install Stable version with the following command   
  ```wget --content-disposition http://links.pinet.org.uk/jessie-stable-pinet```

### Wheezy 
  - Released by Raspberry Pi Foundation in June 2012.
  - Final update released by Raspberry Pi Foundation in March 2016.
  - **No longer recommended** for new PiNet installations.
  - Available in [Stable](https://github.com/PiNet/PiNet/tree/master) and [Development](https://github.com/PiNet/PiNet/tree/dev) releases.
  - Releases up to PiNet 1.1.x.
  - PiNet support provided until 31st December 2017.
  - [Debian Long Term Support](https://www.debian.org/News/2016/20160425) team security support provided until 31st May 2018.
  - Install Stable version with the following command     
  ```wget --content-disposition http://links.pinet.org.uk/wheezy-stable-pinet```
