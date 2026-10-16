# termuxSolutions

Answers to Termux, Android and Linux questions I've posted on XDA as **termuxSolutions**: adb, fastboot, flashing, recoveries, EDL, Magisk, custom ROMs and getting Linux onto phones and tablets.

Each answer is a copy of my post, kept here so it's easy to find, and links back to the original thread on XDA.

## Flashing, recoveries and boot images

- [Galaxy A12: flashing a kernel in TWRP without a microSD](help/xda/galaxy-a12-flash-kernel-twrp-without-sd.md): How to flash a kernel zip or boot.img with no SD card.
- [Moto g13/g23: "fastboot reboot fastboot" opens TWRP](help/xda/moto-g13-fastboot-reboot-fastboot-opens-twrp.md): Why that happens and how to get to the real fastbootd.
- [FOSSiBOT F106 Pro: getting the stock boot.img for free](help/xda/fossibot-f106-pro-boot-img-mtkclient.md): Pull your own boot.img with mtkclient instead of paying for a dump.
- [Moto G55 China ROM: OEM unlocking kicks you out of Developer options](help/xda/moto-g55-china-oem-unlock-frp.md): FRP blocks the OEM unlock flag on XT2435-3, and how to clear it.
- [OnePlus 15: does oplusreserve1 exist on global builds?](help/xda/oneplus-15-oplusreserve1-partition.md): Yes, and why you still shouldn't flash someone else's dump.
- [Realme GT7 Pro (CN): Deep Testing shared user signature error](help/xda/realme-gt7-pro-deep-testing-shared-user.md): Wrong Deep Testing apk signature, and which build to use.

## EDL and data recovery

- [Recovering data from a dead OnePlus 9 Pro via EDL](help/xda/oneplus-9-pro-edl-data-recovery.md): Why a raw dump stays encrypted and how to make a safe read-only copy first.

## Custom ROMs

- [Moto Edge 70 Fusion: any custom ROMs yet?](help/xda/moto-edge-70-fusion-custom-roms.md): Not yet, and why you shouldn't flash other Moto builds on it.
- [OnePlus Pad 4: does LineageOS break the stylus?](help/xda/oneplus-pad-4-lineageos-stylus.md): What still works with the pen on Lineage and what you lose.
- [Galaxy Tab A7: can't install LineageOS (KG Status Prenormal)](help/xda/galaxy-tab-a7-knoxguard-lineageos.md): KnoxGuard Prenormal blocks unsigned vbmeta until it clears.
- [Free Android Kitchen for Windows: deodex, debloat and repack a ROM](help/xda/free-android-kitchen-for-windows.md): Deodex, debloat and repack old ROMs for free, on Windows or Debian.

## Root, Magisk and Termux

- [Magisk Python 3.15 module: how is it different from Termux?](help/xda/magisk-python-3-15-module-vs-termux.md): Same Python, just installed in a different place.
- [OnePlus 15: is ADB safe for a Private DNS toggle?](help/xda/oneplus-15-adb-private-dns-toggle.md): ADB itself is low risk, plus the grant/revoke commands for the toggle app.

## Hardware and troubleshooting

- [TCL Q7C (V667): HDMI drops to NoSignal with "TMDS clock unstable"](help/xda/tcl-q7c-v667-hdmi-tmds-clock-unstable.md): Some things to test when the TV loses signal right after the first frame.
- [Mortal Q1 Mini (RK3518): wireless debugging keeps turning off](help/xda/mortal-q1-mini-wireless-debugging.md): Ethernet turns wireless debugging off on Android 14 TV builds.
- [Android Auto: hard routing audio away from a second stereo](help/xda/android-auto-hard-routing-audio.md): Why AA grabs the media stream, and what actually works around it.
- [Galaxy S24 Ultra: System UI constantly accessing location](help/xda/galaxy-s24-ultra-system-ui-location-esim.md): Narrowing it down to Wi-Fi Calling, an eSIM line or the eSIM app with appops.

## From X

- [Thanks from X](x-thanks.md): Replies from people I helped on X.

## Need help?

Stuck with a Termux, Android or Linux problem? [Open an issue](../../issues/new/choose) with your device, root/recovery setup and the exact commands you ran, and I'll take a look. You can also find me on [XDA](https://xdaforums.com/m/termuxsolutions.13482532/) or on X as [@termuxSolutions](https://x.com/termuxSolutions).

More answers get added as I keep posting.
