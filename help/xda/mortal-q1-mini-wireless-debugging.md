# Mortal Q1 Mini (RK3518): wireless debugging keeps turning off

XDA post: https://xdaforums.com/posts/90778048/

That wireless debugging switch flipping itself off is most likely because the box is on Ethernet. On Android 14 TV builds wireless debugging only stays on while you're connected over Wi-Fi, and as soon as it sees a wired connection it turns itself back off. People hit the exact same thing on the Chromecast with Google TV and on Sony's A14 update, so your box isn't broken.

The third party apps won't get you around that. Get developer options the normal way: Settings, Device Preferences (or Device), About, then highlight Build and press OK on the remote quickly several times until it says you're a developer. On some RK3518 firmware the entry is called system version and it takes about 10 presses. Developer options then shows up back in Settings, usually under Device Preferences.

Now unplug the Ethernet cable and connect the box to Wi-Fi on the same network as your PC. Turn on Wireless debugging, open Pair device with pairing code, and on the PC run

adb pair <box-ip>:<pairing-port>
adb connect <box-ip>:<port shown on the wireless debugging screen>
adb tcpip 5555

After that, adb connect <box-ip>:5555 keeps working even if you switch back to Ethernet, until the box reboots. After a reboot you have to do the Wi-Fi part again.

For flashing later you don't really depend on ADB anyway. Rockchip boxes get flashed with RKDevTool over USB, ADB is mainly handy for backing up partitions before you start.

If the pairing step throws an error, post it here and I'll tell you what it means.
