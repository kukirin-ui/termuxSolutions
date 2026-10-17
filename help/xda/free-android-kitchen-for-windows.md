# Free Android Kitchen for Windows: deodex, debloat and repack a ROM

XDA post: https://xdaforums.com/posts/90777399/

Follow-up: https://xdaforums.com/posts/90777495/

Follow-up: https://xdaforums.com/posts/90779281/

## On Windows

dsixda's Android Kitchen does all three and it's completely free. It runs on Windows through Cygwin, and there's a standalone build here on XDA with Cygwin already merged in (https://xdaforums.com/t/dsixdas-and...andalone-for-windows-cygwin-included.2413996/), unzip it and run `runme.bat`. You still need a Java JDK installed first, the deodex step calls baksmali/smali through java.

Drop the stock ROM into `original_update` (a zip, or PDA/CSC tar.md5 for Samsung), option 1 sets up the working folder, then 0 for advanced options and 11 to de-odex. Debloating is manual, just delete what you don't want from `WORKING_xxx/system/app` before you build. Then 99 to build, and lazy mode zipaligns, signs and names the zip for you, ready to flash in recovery.

Two catches. It's from 2013 and ships old baksmali, so it handles Dalvik odex (KitKat and older), not Lollipop+ oat/vdex. And under Cygwin it can't open Samsung .rfs images on its own, it walks you through pulling the files out with MagicISO instead.

SuperR's free kitchen deodexes and debloats newer ROMs too, but the free one is Linux only and SuperR says it doesn't work under Cygwin or WSL. The Windows build is the paid donate version.

## On Debian instead

Honestly, Debian is the nicer route anyway. The kitchen is just a set of bash scripts and runs natively on Linux, no Cygwin needed at all.

Grab the latest release from github.com/dsixda/Android-Kitchen/releases, unzip it, and before the first run make sure you have the tools it checks for: a JDK plus gcc, perl, wget, cpio, zip and unzip:

```
sudo apt install default-jdk gcc perl wget cpio zip unzip
```

Then cd into the folder and run `./menu`. Deodexing goes through the bundled smali/baksmali via java, so for older Dalvik ROMs like yours you're in good shape.

If something gets stuck along the way, feel free to DM me and we'll sort it out.

## Terminal or GUI?

Terminal. It's a text menu: `./menu` shows numbered options and you type the number. No GUI, but it's easy enough to follow.
