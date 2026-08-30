This will be the home for the binary files to be able to boot and test FYSOSv3.

For now, see [https://www.fysnet.net/blog/2026/07/index.html](https://www.fysnet.net/blog/2026/07/index.html)

A few notes:
- A USB mouse will not be available until later in the boot up.
  If your UEFI doesn't emulate a PS2 mouse at boot, the mouse will not be available at start.
- Same for a keyboard.
- If the UEFI does emulate a PS2 keyboard, or you have an actual PS2 keyboard attached,
  you can press enter at each "hardware announcement" until the USB is enumerated,
  where you can then use the USB devices.
- If your UEFI doesn't emulate either the keyboard or the mouse at start up, you
  won't get very far.
  (I have a machine that doesn't emulate the PS2 keyboard or mouse at startup)
  (It's an older machine, just about the time UEFI was getting popular)

I know there are a lot of issues and bugs that need to be fixed. This is a big project that has taken years to get to this state, and I know it still needs plenty of work. Please if you find an issue, please let me know: fys [at] fysnet [dot] net

## News:
30 Aug 2026:
  - I now use the decompression feature of the UEFI instead of BZ2 (though it is still included).
  - Therefore, if you update to any one of these files, you will need to update them all.
  - I found an error in my multiprocessor detection so I have disabled it until further notice.
  - I disabled the hardware announcement dialogs due to an unknown GPF.
