The loft itself works, but if I try to use polyline guides, it fails (with the error code 98037 - not that there's any way of telling what that means!). I've redrawn the guides three or four times in different ways, but they fail each time. I'm absolutely certain the guides intersect the profiles (although I've been wrong before!), but now they've taken error messages out of CAD 2018, tracking down the problem is nigh on impossible...
 
I've had a play with the paths and different ways of creating them - the weird looping path seems to be the result of joining a 2d polyline and a 3d polyline. I've attached another version of the file with one path I've re-drawn. This time, I've created the path as a polyline in two parts, to see if I could get half the shape to loft, but still no luck...
 
**Download File ⚙⚙⚙ [https://sioburcietek.blogspot.com/?c=2A0SBb](https://sioburcietek.blogspot.com/?c=2A0SBb)**


 
Went back to the original file and split the yellow profiles in half. This seemed to work for the part I lofted with guides. It doesn't seem to work all the pieces however. Is this intended to be symmetrical? Perhaps constructing a top and then a bottom in pieces might work better.
 
I tried repeating what you did and breaking the profiles into quarters, then lofting to create surfaces, but I can't even get it to do that! The lofting works, but any sort of guide line I use throws the same 98037 error.
 
...actually, despite my despairing of CAD's 3d abilities, I couldn't close the file for good and walk away without trying one last thing. My original guide lines running forward from the mid-section profile were formed from a straight line, a spline and then a tighter spline to get the required radius at the front of the object, all joined together. Although it changes the shape of the object slightly (the front radius is larger), a re-drew the guides with only one spline at the front instead of two and all the guides now work - I've attached a revised drawing.
 
I can't find a reference for the error code numbers anywhere. Is there a way to increase the error message verbosity? Previous versions of AutoCAD generated descriptive error messages, not just error code numbers. Fixing modelling errors with a descriptive guide to the problem is only achievable through trial and error...
 
I too wish I had access to a definitive list of what the error codes identify. Apparently they are only helpful to the Dev team. Do you have a model you want me to take a look at to see if I can figure out what might be failing?
 
I've centred the view on the lofting operation I'm trying to get working - there are two profiles - a 6-sided polygon and a 4-sided, long thin rectangle, joined by six polylines I'm trying to use as guides. Selecting any of the guides during the loft causes a modelling error.
 
I took a look at your model and found that if I zoomed in very tight, many of the lines did not connect at all. I rebuilt much of the geometry and then lofted parts together, ran SURFSCULPT and ended up with this 3D solid.

I've always trued to avoid generating/using surfaces - I tend to only encounter them when a 3d modelling operation (like loft or extrude) goes wrong - I'll certainly review their usefulness based on what you say.
 
Simple question here. I have read most of the forums, but cannot seem to get the Assembly Code and Assembly list to work properly. I am not worried about the BOM reports as of now. I am dealing with fuse and fuse blocks and have put them in the same family. In the case below my 2CLASS 'CC' is my primary fuse component. I thought by adding CC-30A to the assembly code and CC-30A for the assembly list for 6SC30A1IC that it would automatically bring in this fuse block to the multiple bill, but this is not the case. Can someone tell me what I'm doing wrong please?
 
Okay thank you! That makes a bit more sense, so is there any way that to put in a primary component and have it automatically generate the second multiple bill dialogue box? On the other hand, if I'm understanding correctly if I change the Assembly Code/List in the database, I cannot change it from that multiple bill dialogue box?
 
Then in the catalog database, you need to fine the field TEXTVALUE. In this field you will put the part number and manufacturer for each item needed. For example, if you have a fuse as the primary, in the fuse's database entry, add CAT01=(Fuse Holder Part number); MFG01= (Fuse Holder Manufacturer).
 
I have been looking for some detailed instruction about location codes for a while now and haven't come across an answer, which I hope is simple I just missed somewhere. I attached an image of what I am doing below in ACADE 2018. I also attached a snip of the devices with the attributes.
 
I am creating some 1 line symbols. In the example attached shows panel box, then location box linked by using the Link Components with Dashed Line. This updates the location code, the problem is the dialog box come up asking if I want to update the other 3 items. These "Panel" boxes were inserted separately, on different lines. Not sure what is connecting them or why.
 
\*You said that you're working with location codes here. But what happens if you change some other attribute? Leave the location alone, add a description instead. Does that want to be pushed to the other 3 symbols too? If so, it's nothing to do with locations.
 
\*How did the symbols come to be in the drawing: -which command used\ -in what order\ -how did you link the children to the parents\ -anything in there have a fixed tag\ -inserted fresh, or copied with the Copy Component command?
 
If it's 'yes' to the first, and if you had a fixed tag, and if you did use ACADE's Copy Component command, then it sounds related to a known issue with the copy circuit command, see my post on the Idea Station here. If so, you could fix this by doing it over, and inserting each parent fresh from scratch (no copying). Then, insert the children individually (no copying).
 
The only other thing i can think of, is that on your VDV1\_\*\*\*\*\* (vertical symbol), that you are using TAG2 instead of TAG1. This could be making ACADE think that everything is a child to the horizontal symbol, depending on how they were all placed. We can't tell because you only posted shots of the horizontal symbol and the child.
 
If none of this applies, we need more info. Could you post the actual drawing from the screenshot, with the misbehaving symbols already in place? It \*looks\* like the symbols are OK based on the screenshots, but posting those wouldn't hurt either.
 
I also appreciate your comment about schematics in layout. We are just now starting to use some of the advanced features in ACADE and we have done schematics in layout for a long time. I will research the reasons and have to address this in our process so it doesn't impact us in the future.
 
At the end of the thread CADDapult writes out some code that seems to do what I want. Question is... how to do enter/use this code. I have not used code in autocad before (have done a small bit in excel).
 
In order to load lisp files, you have to issue the **Appload** command at the command line or in the Tools Menu, Load Application, and then in the command line again, type the command **BlkXplode**. In order to use other lisp files, you have to inspect the file for functions with the pattern: **(defun C:SomeNameHere()...) They are Autolisp defined commands.
**
 
If there are any nested Blocks as ingredients in the definitions of other Blocks, and you want all of those also Exploded, you would want to run that several times. Or you could alter it to run itself as many times as it continues to find Blocks. In simplest terms:
 
However, that [and gasty's original] would also find Xrefs [and, if you ever use them, Windows Metafiles] that can't be Exploded. So really, it ought to run through each item in a selection set, and only if it's an Explodable kind of Insert object, Explode it. [Also, doing it that way (Exploding only one at a time), no messing with the QAFLAGS System Variable is necessary.] There should also be some kind of marker so it will know once it has encountered a selection set that contains no ordinary Blocks among the Insert objects it found, and stop checking -- otherwise it would get into an endless loop. I would bet that there's something out there already that will do something like that, but if you don't find it, it wouldn't be hard to work out.
 
The following program will recursively explode all primary & nested block references (nested to any depth) excluding xrefs, in all drawing layouts (the EXPLODE command will ignore objects in inactive drawing layouts):
 
Gaston's initial response did what I initally needed (although as Kent mentioned, does need to be rerun for nested blocks). I therefore marked it as the solution. However, Lee's solution is super sweet as it takes the repeat running out of it.
 
**I've always used AutoCAD out the box to model some pretty sophisticated as well as simple items. I've worked AutoCAD since 1989. I've never ever received so many modeling errors. below are just a few I captured and copied to a log, just today. I"ve provided the error and the command it failed in and the text therein.**
 
Are you using 3D solid models created in prior versions in AutoCAD 2018? If so, my guess is that the updated ASM modeler that we introduced in AutoCAD 2018 is catching additional data errors that were previously overlooked (but will bite you later). Error messages are displayed for errors that the newest ASM can't fix.
 
anyway, I attempted to put a 1/2x45deg chamfer on the bottom outboard side of the part. first off, I drew half, did my extrusions and subtractions then mirrored it. then unioned it. cleaned it. checked it for "This object is a valid ShapeManager solid.".
 
1. if the mtext text box is used to change the text justification, the 