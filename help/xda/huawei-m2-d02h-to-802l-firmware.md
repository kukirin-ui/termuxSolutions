# Huawei MediaPad M2 (d-02H): wrong resolution, getting to 802L firmware

XDA post: https://xdaforums.com/goto/post?id=90778056

**Question:** Converted d-02H shows the wrong resolution, looking for the right 802L / Marshmallow firmware.

## Answer

The wrong resolution is basically what you get when an 801L system lands on a d-02H that should be running as 802L. Skip chasing B207 first and put a proper 802L Android 5.1.1 base on it, then local-update to Marshmallow.

Free mirror of M2-802L_V100R001C209B003CUSTC209D002 (Android 5.1.1 / EMUI 3.1) is still up on Android File Host:

https://androidfilehost.com/?fid=14655340768118478840

That is the same build people used as the replacement for the dead M2.zip in the conversion threads. Unzip it, grab UPDATE.APP, extract BOOT/CUST/SYSTEM/RECOVERY with Huawei Update Extractor using the Mediapad M2 8.0 (M2-802L) profile. This needs an unlocked bootloader and wipes nothing by itself, but back up anything you care about first and check your battery is above 50%. Then in fastboot:

```sh
fastboot flash boot BOOT.img
fastboot flash cust CUST.img
fastboot flash system SYSTEM.img
fastboot flash recovery RECOVERY.img
fastboot reboot
```

Full d-02H to 802L path and extract guide:

- https://xdaforums.com/t/convert-docomo-dtab-d-02h-into-global-version-802l.4061713/
- https://xdaforums.com/t/guide-m2-8-0-extract-and-flash-device-partitions-from-official-huawei-roms.3541909/

The old Huawei hicloud URLs for B207 (M2-802LC229B207CUSTC229D006) have been dead for years, so ignore those. Once you are on that 5.1.1 802L base with stock recovery, search for a mirror of that B207 update.zip and install it via Settings > Updater > Local Update from a dload folder. I could not find a verified free B209 package for 802L; the documented Marshmallow builds there are B203 and B207. The C209 in the B003 filename is the cust channel, not a B209 ROM.

If the extract or fastboot step goes sideways, post the error here and I'll take a look.
