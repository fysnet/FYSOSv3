This will be the home for the binary files to be able to boot and test FYSOSv3.

For now, see [https://www.fysnet.net/blog/2026/07/index.html](https://www.fysnet.net/blog/2026/07/index.html)

A few notes:
- As long as your firmware supports USB legacy mode, A USB mouse will be available until the USB controller is detected and Legacy mode is turned off. Then there will be a short delay while the USB is enumerated, then the USB mouse will work again, in native mode.
- Not all of the features are implemented and some of the apps don't do a whole lot.
- If you shutdown the system using the File menu, there is a considerable delay before it shuts down. This is due to compressing the registry file and saving to disk. The file is considerably small (3k or so), so there has to be a bottle-neck somewhere in my compression code. It takes way to long...
    
I know there are a lot of issues and bugs that need to be fixed. This is a big project that has taken years to get to this state, and I know it still needs plenty of work. Please if you find an issue, please let me know: fys [at] fysnet [dot] net

## News:
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
