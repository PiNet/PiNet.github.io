---
title: "PiNet, a centralised user accounts and file storage system for a Raspberry Pi classroom."
layout: article
---
# Supported addon boards

   
PiNet supports a number of different addon boards, although some need to be installed separately via the Python-hardware package available in the extra software menu.     
**Warning** - There is no guarentees all boards below will work as advertised with PiNet due to subtle differences from Raspbian.   
All boards with a * have been tested with PiNet and confirmed to work.   
      
## Boards
      
| Board name  | Manufacturer | Supported? | Supported since |    
| ------------- | ------------- | ------------- | ------------- |     
| Pibrella *  | Pimoroni/Cyntech  | Yes, via Python-hardware package | PiNet Release 1.0.0 |  
| Unicorn HAT * | Pimoroni  | Yes, via Python-hardware package | PiNet Release 1.0.0 | 
| LEDBorg * | PiBorg  | Yes, uses standard RPi.GPIO library | PiNet Release 1.0.0 | 
| Ryantech motor driver  | Ryantech  | Yes, uses standard RPi.GPIO library | PiNet Release 1.0.0 | 
| Traffic HAT  | Ryantech  | Yes, uses standard RPi.GPIO library | PiNet Release 1.0.0 | 
| PiDie  | 4Tronix  | Yes, uses standard RPi.GPIO library | PiNet Release 1.0.0 | 
| PicoBorg  | PiBorg  | Yes, uses standard RPi.GPIO library | PiNet Release 1.0.0 | 
| PiStop  | Meltwater  | Yes, uses standard RPi.GPIO library | PiNet Release 1.0.0 | 
| Piglow   | Pimoroni  | Yes, via Python-hardware package | PiNet Release 1.0.15 |  
| Skywriter HAT  | Pimoroni  | Yes, via Python-hardware package | PiNet Release 1.0.15 | 
| Sense HAT * | Raspberry Pi Foundation  | Yes, built in | PiNet Release 1.0.15 | 
| Piano HAT  | Pimoroni  | Yes, via Python-hardware package | PiNet Release 1.0.16 | 
| Explorer HAT  | Pimoroni  | Yes, via Python-hardware package | PiNet Release 1.0.16 | 
| Explorer HAT Pro  | Pimoroni  | Yes, via Python-hardware package | PiNet Release 1.0.16 | 
| Microstack Accelerometer  | Microstack  | Yes, via Python-hardware package | PiNet Release 1.0.16 | 
| Microstack GPS  | Microstack  | No, requires UART | N/A | 
| PiFace Digital  | PiFace  | No, requires SPI | N/A | 
| PiFace Control and Display  | PiFace  | No, requires SPI | N/A | 
| UltraBorg  | PiBorg  | No, no library available from PyPI | N/A | 
| XLoBorg  | PiBorg  | No, no library available from PyPI | N/A | 
| PicoBorg Reverse  | PiBorg  | No, no library available from PyPI | N/A | 
| Play HAT  | 4Tronix  | No, no library available from PyPI | N/A | 
| 16-Channel Servo HAT  | Adafruit  | No, no library available from PyPI | N/A | 
| Capactive touch HAT | Adafruit  | No, no library available from PyPI | N/A | 
    
    
## The board I am looking for is not on that list?   
There are hundreds of addon boards for the Raspberry Pi out there, it would be pretty difficult for me to research and test them all.   
In general, if it just uses the GPIO pins in their standard input/output modes, then it should work without issue.   
If the board uses I2C then it should work on PiNet Release 1.0.15 and above.   
If the board uses SPI, UART or custom kernel modules, it is unlikely to work without a decent bit of fiddling around with configuration files unless it follows the official Raspberry Pi Foundation HATs spec and includes an EEPROM with the device tree fragment.   
If it has an EEPROM with the device tree fragment, it should be able to use the other interfaces (for example SPI) as device tree is enabled with PiNet.   
    
If you see any boards missing or have changes to suggest to the list, drop us an [email or a tweet](../support.html). 
