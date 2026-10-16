# OnePlus 15: is ADB safe for a Private DNS toggle?

XDA post: https://xdaforums.com/posts/90778884/

ADB won't hurt the phone. It's just a debugging connection to Android itself, it doesn't touch the bootloader or firmware, and giving one app one permission is about as low risk as it gets. Nothing in that writes anything to the board.

If the toggle you mean is Private DNS Quick Toggle, it's one command once USB debugging is on and the phone is plugged into the PC:

adb shell pm grant ru.karasevm.privatednstoggle android.permission.WRITE_SECURE_SETTINGS

And if you ever want it undone:

adb shell pm revoke ru.karasevm.privatednstoggle android.permission.WRITE_SECURE_SETTINGS

The app can also get the permission through Shizuku if you'd rather skip the PC.
