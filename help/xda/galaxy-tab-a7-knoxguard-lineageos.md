# Galaxy Tab A7: can't install LineageOS (KG Status Prenormal)

XDA post: https://xdaforums.com/t/cant-install-lineageos-on-my-galaxy-tab-a7.4805069/

Your steps are fine, it's the KG Status: Prenormal that kills it. That's Samsung's KnoxGuard, and while it sits in Prenormal the bootloader refuses anything that isn't Samsung signed, unlocked bootloader or not. So the moment it sees the LineageOS vbmeta you get that "go to a service center" screen, and trying other vbmeta files won't change a thing.

What usually clears it is boring. Flash the full stock Android 12 firmware with Odin (you already did that, so you're fine there), go through setup with Wi-Fi connected instead of skipping the network page, turn on automatic date and time, and just leave the tablet on and online. For some people it flips within a few hours, for others it takes a few days. You can check by booting into download mode (hold Vol Up + Vol Down while plugging in the USB cable) and looking at the KG line. Once it says Checking or Completed instead of Prenormal, and OEM unlocking is still on in Developer options, redo the samloader vbmeta step and it should go through.

One thing to keep in mind. If the tablet came second hand, from a carrier or on a payment plan, and KG never leaves Prenormal (or switches to Active), it's locked by whoever registered it in KnoxGuard and only they or Samsung can release it. No vbmeta file gets around that.

If it's still stuck after that, DM me your exact model and current firmware and I'll help you figure out the next step.
