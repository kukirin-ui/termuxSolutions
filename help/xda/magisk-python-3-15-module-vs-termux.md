# Magisk Python 3.15 module: how is it different from Termux?

XDA post: https://xdaforums.com/posts/90777485/

Same Python, different place it lives.

Termux is a normal app, no root needed, and everything you install with `pkg` stays inside its own folder (`/data/data/com.termux/files/usr`), so you only get that python from within Termux.

This module needs Magisk and puts `python3` into the system itself (`/system/usr/bin`, with wrappers in `/system/bin`), so it works from any root or adb shell, scripts run by other apps, etc. pip packages go to `/data/local/tmp/home/python/site-packages`.

If you just want a Linux-ish terminal with python, Termux is easier. If you need python available system-wide on a rooted phone, that's what this is for.
