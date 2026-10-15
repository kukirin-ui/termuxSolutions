# Galaxy Tab S8+: running Ubuntu or Linux

XDA post: https://xdaforums.com/goto/post?id=90778054

**Question:** Can Ubuntu Touch or another Linux run on the Tab S8+?

## Answer

Ubuntu Touch itself isn't an option right now, the S8+ isn't on the UBports device list so there's no port to install. Someone has already done the harder thing though. aaronsb has mainline Linux (postmarketOS) running on the S8+ Wi-Fi model with the display, GPU, touch, keyboard cover, Wi-Fi, audio and S Pen working, and Plasma 6 on top:

https://github.com/aaronsb/sm-x800-linux

A few catches before you lend it to anyone. It's the Wi-Fi SM-X800 only, so if yours is the 5G X806B it isn't covered yet. It also needs a bootloader you can still unlock. Look at Settings > About tablet > Software information > Build number, the fifth character from the end is the bootloader binary. 9 or lower and you're in, A or B (which is what you'll have if it took the normal updates since February 2026) and the repo says there's no known way back in. Unlocking wipes the tablet and trips Knox for good, so back up first. And it doesn't dual boot, uniLoader takes the boot partition and Linux lives in userdata, so Android is gone until you Odin stock back on.

If you only want an Ubuntu userland next to Android, Termux (from F-Droid, not the Play Store) does that with no unlock at all: `pkg install proot-distro`, then `proot-distro install ubuntu` and `proot-distro login ubuntu`.
