# Galaxy S24 Ultra: System UI constantly accessing location (eSIM/IMS)

XDA post: https://xdaforums.com/posts/90779280/

eSIM failing in safe mode doesn't tell you much by itself. A lot of what's on your list (Phone, imslogger, the eSIM app) is calling/IMS stuff, so that's where I'd look next. All of this is easy to undo:

1. Turn off Wi-Fi Calling for a while (Settings > Connections > Wi-Fi Calling) and watch the indicator.
2. If nothing changes, temporarily switch off one eSIM line in Settings > Connections > SIM manager (switch it off, don't delete the eSIM), then try the other one.

Whichever change makes the indicator calm down points at the culprit.

If neither does, run this while the indicator is on and post the output with any personal info removed:

```bash
adb shell dumpsys appops --package com.samsung.euicc
```

(If that package isn't found, `adb shell pm list packages | grep -i euicc` shows the right name.)

That way we'd know for sure whether the eSIM app itself is pulling location, or whether it's just the Phone/IMS side.
