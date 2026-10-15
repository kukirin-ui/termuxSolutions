# Galaxy S24 Ultra: System UI keeps using location

XDA post: https://xdaforums.com/t/4805125/post-90778051

**Question:** The location indicator stays on and the history blames System UI.

## Answer

Safe mode is the useful clue here. Samsung's safe mode only shuts off apps you downloaded, everything preinstalled still runs. So if the constant pinging stops there, something you installed is behind it, and System UI is just the process that ends up making the request, which is why the history blames it. The quick settings part still happens in safe mode, so that one is stock behaviour and a separate thing from the always-on part.

Quickest way to find it is adb while the indicator is showing. This shows the active location requests, with provider and interval:

adb shell "dumpsys location | grep -i -A3 systemui"

And this one shows System UI's app ops:

```sh
adb shell dumpsys appops --package com.android.systemui
```

Look at the COARSE_LOCATION and FINE_LOCATION entries. The access times should line up with when the indicator is on, and if there's an attribution tag on the entry it tells you which part of System UI asked.

If nothing obvious shows up, go the boring route. Disable or uninstall downloaded apps in batches, starting with anything that adds widgets, quick settings tiles, lock screen or notification features, or anything that got updated around the time this started. Reboot after each batch and watch the indicator for a while. Once it stays off, put them back one at a time until it comes back.
