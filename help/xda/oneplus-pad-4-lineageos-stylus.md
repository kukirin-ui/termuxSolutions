# OnePlus Pad 4: does LineageOS break the stylus?

XDA post: https://xdaforums.com/posts/90777377/

Short version, going off the iceland device tree rather than weeks of note-taking on it: the pen is supported, it just isn't the OxygenOS experience.

The build ships LineageOS's own OplusPen service plus the wireless pen charging firmware. When you attach the pen to charge you get a "Pen attached / Tap to connect" notification, tapping it pairs the pen over Bluetooth, and from then on the pressure data gets relayed from the pen to the touch side. So pressure depends on that pairing being done.

While the pen is connected the screen gets capped at 120Hz (default peak on this build is 144Hz). That's on purpose, not a bug.

What you lose is the stuff that lived in OxygenOS itself: the pen settings page, the side-button shortcut mapping and the pen battery widget. The Lineage service only handles pairing, pressure and that refresh cap.

Palm rejection I can't vouch for either way, I haven't seen anyone report on it yet since official builds only showed up this month.

No modules or overlay tweaks needed for the basics, it's all baked in. The firmware part is just the normal install requirement: be on the latest Android 16 OxygenOS before flashing, and make sure your model is OPD2514 since that's the only one the wiki lists.

A GSI won't have that pen service at all, so if the stylus is your daily driver, go official Lineage and skip GSIs.
