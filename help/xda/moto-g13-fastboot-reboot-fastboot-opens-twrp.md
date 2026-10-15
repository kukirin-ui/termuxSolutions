# Moto g13/g23: "fastboot reboot fastboot" opens TWRP

XDA post: https://xdaforums.com/posts/90777313/

That's expected on the g13/g23. On this phone there's no separate recovery partition, the recovery ramdisk lives in vendor_boot, and that's exactly where the TWRP guide has you flash twrp_penangf.img. fastbootd is part of recovery, so `fastboot reboot fastboot` now boots TWRP, and the TWRP build you have either doesn't do fastbootd at all or does it badly. Your PC is waiting for a fastbootd device that never shows up.

Easiest fix is to put the stock vendor_boot back for the flashing part. Grab the firmware zip that matches the build number you're on right now (Settings > About phone) from lolinet, https://mirrors.lolinet.com/firmware/lenomola/2023/penang/official/ , pick your channel folder (RETEU, TELEU etc.) and take vendor_boot.img out of it.

Then boot into the normal bootloader with Power + Vol down, which still works fine with TWRP installed, and run:

```
fastboot flash vendor_boot vendor_boot.img
fastboot reboot fastboot
```

Now you should land in the real stock fastbootd and the debloatedmotoweed steps will go through. Once you're done you can flash TWRP to vendor_boot again if you still want it.

If you get stuck on it I can walk you through it over a remote session, just DM me.
