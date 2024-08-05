An example of a scientific term that features the combining form *tacho-* is *tachometer*, a term for a variety of instruments that measure velocity or speed, such as how fast an engine goes.
 
Initially I removed the resistor in the tacho (46k) and swapped this for a 1k resistor. I then taped the ecu aux output into the factory tacho signal wire (used to come from the ignitor). The tacho wouldn't read. After a lot of trial and error I've got the tacho to work, but hoping to get some opinions if this is correct.
 
**DOWNLOAD > [https://sioburcietek.blogspot.com/?c=2A0SF8](https://sioburcietek.blogspot.com/?c=2A0SF8)**


 
Currently, the ecu output is taped into the tacho signal wire under the dash, also on that same tacho wire is now a relay coil, the tacho wire is connected to pin 85, and a 12v ignition feed is connected to the 85pin (coming from the old ignitor 12v supply). This makes the tacho work. Another way that works is by removing that relay and just plugging the factory ignitor back in (ignitor is doing nothing anymore).
 
I would have thought that the ECU signal alone, taped into the tacho signal wire, with the resistor changed inside the tacho would be enough? Or does it also need that 12v feed supplied on the same wire? Wouldn't this back feed to the ecu?
 
The ignition outputs are only pulled up to about 6V so your tacho may want more than that. You could try a 1kohm pull-up resistor connected to 12V. Or if you have an aux output you can swap with the ignition output, as they are already pulled up to 12V.
 
I can get it to work how it is at the moment, (tach output from ignition output 4 to tacho signal wire, also spliced into that tacho wire is a relay coil attached to pin 85, and a 12v ignition switched feed to the pin 86. It also works if I removed the relay and added a resistor from 1k upto 67k. Does that sound correct?
 
Since I have wired my coil packs and no longer using distributor for ignition but only for cam/crank signal, I have no tacho, I've been ready about a relay is needed to up the current, how exactly do I wiring it up ? It is a supralink ecu, 2JZGE NON VVTI SUPRA JZA80 1995
 
Furthermore, the 2JZGE engine loom does not have a tachometer connection on Pin A16 (AUX1) from factory. So you will need to add a terminal to A16 on the ECU header. Run your new AUX1 & splice it into the wire going into Pin29 on the Orange 36 pin passenger footwell connector.
 
If you dont want to pull the cluster out, then you will either need to use the relay coil or buy a commercially available tacho booster. I have always used these with good sucess: Or since you are in Aussie, this is the same device with a different sticker: -tacho-booster-signal-adapter

**Tacho** (meaning *pot*[1] or *pan*[2]), also known as **Chau-Chau Pele**,[3] is a type of meat and vegetable stew or casserole of Macanese cuisine that is a local variant of cozido Portuguesa, found in Portuguese cuisine, which heavily influenced Macanese cuisine during colonization.[1][4] Its preparation and serving is similar to a pot-au-feu or boiled dinner.[2]
 
The dish has both Portuguese and Cantonese influences. It evolved from cozido Portuguesa, but many of the substitutions were to Cantonese ingredients.[8] Even though there are variations depending on recipes, tacho is, in general, noted to have swapped the chourios that is found in *cozido* with Chinese sausage,[2] and the turnips found in *cozido* with daikon.[1] Some tachos include pork rind, pig's trotters, and balicho.[9][8] One recipe also calls for the use of fish maw.[2] Often cabbage is an ingredient.[4][8]
 
Results were unsatisfactory with an analog tacho into the 6009 (buffer overflows if rate set too high etc...) so I would like to use the counter instead but I'm having trouble figuring out how to do this.
 
I'm not quite sure what you mean by "the speed simply increments upwards of 500M" but I would recommend you take a look at the example VI titled Even Angle Reference Signal Processing (Digital Tacho, DAQmx).vi. It is located in the LabVIEW example finder (HelpFind Examples...) under Toolkits and ModulesSound and VibrationAnalyzing and Processing SignalsOrder Analysis
 
The reason for my confusion is that page 6 of the data sheet states that analog feedback needs to be 0-5v, whereas the dc tacho would deliver +v and -v depending on direction. How do I get around that problem?
 
I had an intermittent tacho, which gradually declined into a full non-working tacho for the past month or so. After finally getting the time to rip the cluster out again and doing what I described below, the tacho started working straight away. I'm not 100% sure this is what fixed it but I'm fairly confident it has. This procedure may apply to different cars with similar setups, just check the correct pins and plugs etc. It's fairly straightforward.
 
What I found is the metal tag on the black loom plug that goes into the tacho (the lower one on the side with 2 plugs on it, the right side as you look forwards) was sitting a bit lower than the other 2 on either side of it. Since this plugs into a socket which has a stiff plastic sheet for holding the connectors, I imagine that the 2 higher tags were lifting the sheet up and out of the way to make the contact with the tacho signal wire dodgy at best, and depending on how the car flexes and moves as you drive, possibly breaking all contact.
 
3. Find the tacho signal wire pin/tag on the loom plug. On mine, it's the pin that goes into something labelled "TAM" in the cluster socket, which is a track that goes directly into a bolt that holds the tacho on. The signal pin on mine sits between 2 other metal tags in the only group of 3 tags on the black plug.
 
5. With a pair of jeweler's screwdrivers or similar (safety pins should be fine), very gently prise up the metal tag on either side of the middle, where the bend in the metal is, to make it flush with the 2 on either side of it. Try to keep the pressure uniform on both sides to avoid over stressing the metal.
 
When I had everything apart, I checked the resistance on the tacho signal wire for the hell of it. The resistance went quickly from some high value to open circuit, each time I tested it and swapped to the earth next to it and back again. Since my tacho now works, I imagine this reading is indicative of a properly working tacho signal wire. If you have an earth here instead, or it doesn't skip from high resistance to open circuit, or some uniform low resistance value, then you might have a problem with your signal wire. I'm not an expert here, so this is just speculation and something for you to try while it's all apart.
 
So on the weekend I pulled it out and did pretty much what is described here. I filed the plug (all contacts) so that they were shiny, then got contact cleaner and went over all the tracks in the sockets on the back. Initially I had it loose and started the car, fiddled with the wires and couldn't make it play up.
 
After the cleaning, I put it back in (not screwed in) and turned the car on and off about 5 times. I revved it past 5K (the point at which it used to fall down to 9+) and it was fine. Put it back in, put the dash all back together, tested in the driveway while pushing all over the cluster and banging the dash... it was fine.
 
My tacho hasn't worked for awhile now. Everytime I pull it out of the dash to do something it seems to fix it for a few days or weeks, then eventually it dies again and sometimes comes back by itself, and sometimes (most of the time in my last few attempts) whatever I do doesn't fix it at all and it stays dead indefinitely. It used to start working by itself more often when the car's been sitting in really hot or cold weather for a long time (usually hot) but again, not lately. In extreme weather conditions I'm guessing a loose contact somewhere is expanding or contracting enough to make a better contact with something else in there, but where that is exactly I am not longer sure. It could the plug contact in the dash or it could be a dry joint or failing component in the tacho itself.
 
Does anyone know how to test a tacho with some cheap parts or a Jaycar kit? I might head down to Jaycar on the weekend and see what they have, they must have some sort of 12v variable pulse generator I can rig up and pretend it's an engine. Gravedigging this thread has inspired me to suddenly care more about my inability to read revs
 
Well took my cluster apart today (R33 GTST) and looked to see if i could find any issues as my cluster is messing up. All contacts were good and continuous (thank god for multimeter's) I went to undo the three screws the from the back of the cluster which hold the tacho in and noticed that one of the screws was different and severely corroded.
 
I cleaned the screw and tried to clean the corrosion out of the screw slot and after stating the car it seemed a little better. Maybe tomorrow (if its a clear day) ill get a new screw and some contact cleaner to try and clear the terminal on the tacho.
 
I have a bung tacho as well. Am used to it by now, but in a way am bummed about it. Clearly some design or manufacturing fault at play. Once in a blue moon it actually works, but then it goes back to it's "seeking" mode and will be sitting at 9000rpm when I'm actually at a stop light lol.
 a2f82b0cb4
 
