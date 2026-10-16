# Moto G55 China ROM: OEM unlocking kicks you out of Developer options

XDA post: https://xdaforums.com/posts/90778776/

Not normal, but it's a known thing on the China G55 (XT2435-3). On Android 15 and newer the system refuses to save the OEM unlocking flag while Factory Reset Protection is still active, and Settings crashes instead of showing an error, so you get thrown out of Developer options. FRP stays active when a Google account that was on the phone earlier (for example from a global ROM it had before) never got verified after the reset or reflash.

To confirm, with USB debugging on:

adb logcat -c
(tap the OEM unlocking switch once on the phone)
adb logcat -d | findstr /i "FRP PersistentDataBlock"

(On Linux/Mac use grep -iE "FRP|PersistentDataBlock" instead of findstr.) If you see "Attempt to update PDB was blocked because FRP is active", that's it.

The China ROM ships the Google apps disabled, so turn them back on:

adb shell pm enable com.google.android.gsf
adb shell pm enable com.google.android.gms
adb shell pm enable com.android.vending
adb reboot

Then get on Wi-Fi, add the same Google account that was on the phone before, give it 5 to 10 minutes and try the switch again. If it's greyed out at first, leave it online for 10 to 30 minutes.

It has to be the account that was actually on the phone. If that was the seller's, they're the one who has to sign in or remove it.
