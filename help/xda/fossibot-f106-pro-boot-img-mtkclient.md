# FOSSiBOT F106 Pro: getting the stock boot.img for free

XDA post: https://xdaforums.com/posts/90777264/

Hey, totally get it, those paid "dump" sites are a pain, and honestly you don't need them. Since it's a Helio G85 (MediaTek), you can pull the boot.img straight from your own tablet for free with mtkclient (open source, on GitHub: bkerler/mtkclient).

Rough steps:

1. Install mtkclient on a PC (Linux is easiest; on Windows you'll need the UsbDk driver).
2. Power the tablet off completely, hold Vol+ and Vol- together and plug in the USB cable so it enters BROM mode.
3. Before touching anything, make a full backup: `python mtk.py rl backup` (this dumps every partition, so you've always got a way back).
4. Then grab the bits you need: `python mtk.py r boot_a,vbmeta_a boot_a.img,vbmeta_a.img` (if your device has no A/B slots, it's just `boot` and `vbmeta`).
5. Patch boot_a.img with the Magisk app on the tablet, copy the patched file back to the PC.

You'll also need an unlocked bootloader. First try Developer options > OEM unlocking, then `fastboot flashing unlock`. If fastboot unlocking is blocked, mtkclient can do it: `python mtk.py da seccfg unlock`. Heads up: unlocking wipes all your data, so back up your photos and files first.

Then flash the patched image (`fastboot flash boot_a magisk_patched.img`, or `python mtk.py w boot_a magisk_patched.img`) and reboot.

Keep that full backup somewhere safe. If anything goes wrong, you can write the original partitions back. Happy to help if you get stuck on any step!
