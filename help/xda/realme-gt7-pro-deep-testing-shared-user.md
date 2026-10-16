# Realme GT7 Pro (CN): Deep Testing shared user signature error

XDA post: https://xdaforums.com/posts/90778310/

That error just means the apk you have is signed with a key your firmware doesn't accept. Deep Testing installs as part of the system shared user (android.uid.system), so its signature has to match what's on your build, and old or wrong-model versions get rejected exactly like that. Nothing is wrong with the phone itself.

Use the DeepTesting-realme.apk that Zerbrechl1ch attached in the CN GT7 Pro thread, it is the one the CN to global guide there uses:
https://xdaforums.com/t/realme-gt7-pro-global-rom-rmx5010.4702058/page-4

Before you apply, sign in with a Chinese HeyTap account in Settings, set the system language to English or Chinese and turn on OEM unlocking in developer options. If it installs but then says this device model does not support deep testing, check your build number. Someone on RMX5010_16.0.0.231 got that exact message, downgraded to Android 15 with the official CN package and then the application went through:
https://xdaforums.com/t/how-to-unlock-bootloader-of-chinese-version-rmx5010.4774520/
Downgrading usually wipes the phone as well, so back up before that step too.

Approval takes about a week and there are only around 200 slots a month, reset on the 1st. Once approved, press Start Deep Testing again, it reboots to fastboot, then run fastboot flashing unlock and confirm on the phone. That wipes everything, so back up first.
