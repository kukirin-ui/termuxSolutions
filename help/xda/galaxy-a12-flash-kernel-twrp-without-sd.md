# Galaxy A12: flashing a kernel in TWRP without a microSD

XDA post: https://xdaforums.com/t/4805104/post-90778052

**Question:** How to flash a kernel zip or boot.img with no SD card.

## Answer

You don't need a microSD for this, TWRP installs straight from internal storage. Copy the kernel zip to the phone (Download folder is fine), boot into TWRP, tap Install, browse to the zip and swipe to flash. If the kernel came as a boot.img instead of a zip, tap Install Image at the bottom of that same screen, pick the img, choose Boot as the partition and swipe.

Before flashing anything go to Backup and tick Boot (and DTBO if it shows up) so you can restore it if the phone bootloops. After the flash, wipe Cache and Dalvik and reboot to system.

If TWRP can't see your files on internal storage you can skip storage completely. In TWRP go to Advanced, ADB Sideload, swipe, then with the phone plugged into the PC run `adb sideload kernel.zip`. That only works for zips though, not img files.

And make sure the kernel was built for your exact model. A125F and A127F take different kernels, and the wrong one just won't boot.
