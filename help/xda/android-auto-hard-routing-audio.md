# Android Auto: hard routing audio away from a second stereo

XDA post: https://xdaforums.com/t/android-auto-keeps-hard-routing-audio-need-help.4805031/

Follow-up: https://xdaforums.com/posts/90778743/

Yeah, that's just how AA behaves, not something you missed. Once it's projecting, it grabs the media stream for itself and the output switcher stops applying, which is why your earbuds get ignored too. On wireless AA the Bluetooth link to the head unit only carries calls, the music goes over the Wi-Fi connection, so a second BT device never sees it.

One phone-side thing is worth a shot, but only if you connect with a cable. Go to Settings > System > Developer options, scroll down to the Media section, turn on "Disable USB audio routing" and reconnect. Some people get media playing over Bluetooth that way while AA keeps running on USB. It doesn't work for everyone, and it does nothing for wireless AA.

The fix that actually holds up is wiring. The NAM5240 has RCA pre-outs (front L/R plus sub, and rears on the 4.1 versions), so run the front pre-outs into an aux or RCA input on your second stereo, or straight into the amps if you'd rather. Then whatever AA plays, music and nav, comes out of your real system and the Bluetooth problem stops mattering.

## Follow-up (wireless AA)

For wireless AA, no, not that I know of. Media goes over the Wi-Fi link to the head unit and there's no setting on the phone side, dev options included, to send it to a second Bluetooth device while AA is running.

The static you got on the RCAs is very likely a ground loop, not the cables. Easy test: with the engine running, unplug the RCAs at the second unit or amp. If the noise is gone, it's coming in from upstream. Then run the head unit and the amp/second stereo ground to the same bare metal point, keep the RCAs away from power wires, and only if that doesn't fix it try a ground loop isolator (that can cost you a bit of bass).

That doesn't help with the 2V pre-outs, I know. If you want to keep your second unit doing the processing, the only clean way I see is getting it the audio by wire from the Nakamichi, since the phone won't share it over Bluetooth.
