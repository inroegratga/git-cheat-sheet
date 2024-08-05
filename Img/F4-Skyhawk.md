
 
Any opinions on whether Seagates latest drives in 10TB form would be of any use for unRaid. The Ironwolf drives are specced for nas use but the Skyhawks for surveillance and are equally specced to power down when not in use and power up quickly which would seem just what unRaid needs. Problem is that they're both 7200rpm heat generators! Any thoughts anyone cos my array needs an upgrade from 8TBs soon.
 
I haven't used SkyHawks but I have some of WD's Purple surveillance drives and they are fine. I bought them because at the time I could get four of them significantly cheaper than four Reds. They have different firmware but I wouldn't be surprised if mechanically they had a lot in common.
 
**Download ✶ [https://sioburcietek.blogspot.com/?c=2A0SId](https://sioburcietek.blogspot.com/?c=2A0SId)**


 
Depends. Got a good deal on a pair of oem drives. Bit risky but ... Ironwolf at 7200rpm seem comparable yet skyhawk drives seem the better choice although maybe being powered down a lot of the time might not be ideal givem that theyre designed as surveillance drives. I'm going to free up a couple of 8TB drives by putting them in as 1 of a parity pair across a couple of microservers. So my parity will be a mix of 10TB / 8TB (data drives are 8TB) rather than throw two into one server which may not be a wise idea. If there's any failures i can return the 8TB freed up.
 
Surveillance drives are optimised not to drop frames when recording a steady stream of video data. NAS drives are optimised not to be thrown out of a RAID array by retrying failed reads. Otherwise they're pretty similar. Both are designed to spin 24/7 but both can be spun down to save power. What neither likes is repeated spinning up and spinning down.
 
An IronWolf has the same mechanicals as a SkyHawk, a WD Red has the same mechanicals as a Purple, etc, etc. Heck, my WD White-labels, WD Reds and WD Purple (all 8TB drives) all even have the same firmware revision on them, just different features turned on/off depending on the drive. Physically they're identical.
 
I understand you points but think that optimised for surveillance must trump a drive designed for desktop or a quick shuck from an external backup. We'll soon see as theyre on their way ...

Sent from my LG-D855 using Tapatalk


 
Doesn't that also imply that non-surveillance drives will drop frames (ie: data) on a continual stream of writes? If that's the case, then I'm switching over to be 100% surveillance drives if they're the only ones that won't lose data when I'm writing to them....
 
Short delays while copying files just cause the copy process to slow down for a while. When you record live video streams there isn't much scope for pausing for long. Once the DRAM cache is full frames will get dropped.

What the Backblaze statistics shows is that you don't need to buy the really expensive enterprise disks for server use - at least as long as you don't use them as database disks where there will be really huge amounts of disk seeks.
 
Cloud storage companies are using more complex redundancy methods which means individual data blocks are stored in multiple pools which makes it easy to rewrite data that gives read errors by making use of alternative storage clusters.
 
In the end, the Backblaze statistics gives some form of indication about expected failure rate for the specific models used in their disk pools. Nothing can be deduced about other drive models, or newer production batches or other model sizes.
 
One thing I noticed about the Seagate IronWolf and SkyHawk is that (for the higher capacity drives, at least) the uncorrectable read error rate is an order of magnitude better than the WD Red (1 in 10^15 vs. 1 in 10^14).
 
One thing I noticed about the Seagate IronWolf and SkyHawk is that (for the higher capacity drives, at least) the uncorrectable read error rate is an order of magnitude better than the WD Red (10e-15 vs. 10e-14).
 
It's necessary for large disks to improve the probability of uncorrectable read errors because of the huge amount of data they handle. So they have had to improve the detection of vibrations so they can pause writing new data if vibrations might knock the write head off alignment.
 
When the drive prepares to write it uses the read head to locate the correct track and pick up which sector of the track that is currently passing under the read head. Then the drive performs a blind realign to move the write head on top of the track (how much realign that is needed depends on how far off-center the track is) and then the drive blindly counts time until the expected sector rotates in under the write head so the write operation can be started. Any bump after the read-align would send the write head off-track, and the required tolerances are so small that vibrations from other disks can be enough. And with higher track density, it's also more important to handle that the tracks aren't perfectly round circles - both because of the servo-track mastering and because of mechanical tolerances.
 
After the blind write, the drive does not return back to the just written sectors to verify that the writes did go well - at best it does a read-align to check how well it follows the track. So it isn't until the drive gets a read request for the sectors or the user issues a long SMART test that it will know if the new data is readable. So lots of care is needed to minimize the danger that the writes ended up misaligned. This is a reason why Seagate writes "Drive balance with Rotational Vibration (RV) sensors manage multi-bay vibration for long-term consistent performance and reliability".
 
It's astonishing they work at all, but I thought that 30 years ago and they still keep squeezing more and more into the same space. While capacities have increased almost by a factor of a million (my first hard disk had a capacity of 20 MB) the chance of reading the whole disk without getting an unrecoverable read error has not kept pace. If I remember correctly the figure was typically 1 in 10^12 back then.
 

WD and Seagate have R&D budgets like small countries - it was many years since normal, simple, physics could improve a HDD. And they get into big troubles if one of them gets too much ahead of the other with the research into new technology. A huge number of HDD manufacturers have already had to close shop because they couldn't keep up. Bye Maxtor, Connor, Micropolis, MiniScribe, ...
 
So, recently I installed the A-4E skyhawk mod for dcs world. I followed the GR tutorial for the install, and just checked some other youtubers on how to install the skyhawk as well. When I check the installed modules page, it's there, but I cant play it! When I open DCS world, it says "the following modules are not authorized and will be deleted: A-4E Skyhawk". I have heard things regarding the skyhawk that you need FC3 installed, which I don't. However some others have said that they didn't have FC3 and still got it to work. I don't know what i'm doing wrong. Please help.
 
... I followed the GR tutorial for the install ... just checked some other youtubers on how to install the skyhawk as well ... I have heard things regarding the skyhawk ... some others have said ... I don't know what i'm doing wrong.
 
Can you upload a screenshot showing your A-4E folder, the one with the A-4E-C.lua file on it, with the full path showing on the shot? .. Also, it is not enough to place the Mod on the correct place at /Saved Games/ ... you also have to delete any prior install that you may have made at the wrong location.
 
Actually, the Mod works also on Stable version of DCS, not only Open Beta. The user just have to place it on the correct /Saved Games/ subfolder (and delete it from /Program Files/ if he first erroneously installed it there).
 
so I deleted all the A-4E-C folders in DCS. In the input and in the mods folder and downloaded the newest version, I do have just have DCS world stable version and downloaded the A-4E-C folder into (C:)/Users/XXX/Saved Games/DCS/, just like that. I check the A-4 location and its in the Mods folder. I deleted my previous mods folder (I do not have any other mods installed) and according to the official instructions I did it right. When I open DCS world it still gives me the notification "the following DLC are not authorized and will be removed: A-4E-C Skyhawk" It doesn't show up at the list of aircraft at the bottom of the main menu screen, but when I go look at the installed modules its there, but wont let me fly
 
I'm also having a problem getting DCS world to see my A-4E-C 2.0 download on this computer. Does not show up on the list. I did the install exactly as outlined and have the same download on another computer and its runs fine from the same location on C drive. Is there a number I can call or can someone do a screen share to see what the problem amounts to. I have checked security settings, etc and both computers are set the same. I'm missing something but don't know what it is. Can I contact support in Switzerland??? New to this game and everything else runs fine on DCS. I'm not going to pay for other downloads if I can't be sure it will run. Happy to pay for help if it can be made to work. Thanks
 
Thanks for the suggestion for the other Forum. I have posted there also. Did not pay for this one just downloaded it according to the instructions. I'm fearful about purchasing anything from DCS before I solve this problem.
 
Well, some mods do alter official game files and thus do affect how official content works (in a negative way every now and then). That's why the very first thing devs tell you here when troubleshooting problems is to remove or disable all unofficial mods. That's inherent thing about every custom product in the world, though, so you just have to be aware of it and deal with it.
 a2f82b0cb4
 
