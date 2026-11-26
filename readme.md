This will be the home for the binary files to be able to boot and test FYSOSv3.

For now, see [https://www.fysnet.net/blog/2026/07/index.html](https://www.fysnet.net/blog/2026/07/index.html)

A few notes:
- When updating your test machine/image with new files from this github, please make sure you have the latest kernel64.sys *and* BOOTx64.EFI files. Don't use one without making sure the other is the latest as well.
- If you see colored lines drawn across the top of the screen at boot time, don't worry, this is just the debug part of the boot. However, if for some reason it doesn't boot, please let me know how many lines you see and what colors they are and in what order.
- As long as your firmware supports USB legacy mode, A USB mouse will be available until the USB controller is detected and Legacy mode is turned off. Then there will be a short delay while the USB is enumerated, then the USB mouse will work again, in native mode.
- Not all of the features are implemented and some of the apps don't do a whole lot.
- If you shutdown the system using the File menu, there is a considerable delay before it shuts down. This is due to compressing the registry file and saving to disk. The file is considerably small (3k or so), so there has to be a bottle-neck somewhere in my compression code. It takes way to long...

The Notepad app, when launched, will automatically show all of the debug log up to this point as the body text. If you have waited long enough for the USB to enumerate the booted thumb drive, you can save this text to that thumb drive (defaults to that drive). I would appreciate seeing that text file if you don't mind sending it to me at fys [at] fysnet [dot] net.
    
I know there are a lot of issues and bugs that need to be fixed. This is a big project that has taken years to get to this state, and I know it still needs plenty of work. Please if you find an issue, please let me know: fys [at] fysnet [dot] net

## News:
26 Nov 2026:
  - A bit of work has been done to see why certain test machines would not boot to the desktop.
  - I believe I have fixed a few items that would cause these issues.
  - One test machine still does not allow the touchpad to work, even in PS2 mode.
  - It looks like most newer laptops now use I2C protocol for their touchpads with at least two
    different devices listed in the ACPI device list. One for the touchpad and one to filter multi-touch gestures.
  - See below for a screen shot
    
15 Nov 2026:
  - Updated the Paging system. Hopefully this fixes an error on a fellow readers test machine.
  - Added a settings menu to the boot file. Press F7 when the system shows "Looking for key events" and you can adjust settings.
    These settings simply allow you to disable the detection/use of these items within the kernel.
    Since these settings are meant to be temporary and only for the current session, they are not saved. 
    You must press F7 on each boot if you desire to adjust these settings.
  - Press F8 to choose a video mode.

16 Oct 2026:
  - A new ACPI driver has been installed, mostly thanks to [https://github.com/uACPI/uACPI](https://github.com/uACPI/uACPI).
  - With a hack to part of that code (due to a faulty DSDT?), this fixes the touchpad on one of my laptop test machines.
  - The Battery enumeration code has been installed, now I just need to display the found information.
  - A few fixes to the xHCI controller code and now a device attached should enumerate as expected.
  - A fix to the time of day code has been applied.
  - A speed up of the memory management has sped up a lot of the system function.
  - Other minor fixes have been applied.
  - The hardware announcement dialogs are re-enabled. Please let me know if you get a GPF.
    
30 Aug 2026:
  - I now use the decompression feature of the UEFI instead of BZ2 (though it is still included).
  - Therefore, if you update to any one of these files, you will need to update them all.
  - I found an error in my multiprocessor detection so I have disabled it until further notice.
  - I disabled the hardware announcement dialogs due to an unknown GPF.

## Screenshot(s):
(Click on image to see full size)
![26Nov2026](https://www.fysnet.net/grafx/fysos_screenshots/26nov2026.png)
