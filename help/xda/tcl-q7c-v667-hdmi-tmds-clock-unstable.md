# TCL Q7C (V667): HDMI drops to NoSignal with "TMDS clock unstable"

XDA post: https://xdaforums.com/posts/90777415/

Your log pretty much tells the story: the first frame comes through, then about a second later the TV's receiver loses the TMDS clock and drops to NoSignal. The Zidoo keeps outputting (your capture shows that), and standby/wake brings it back. So it looks like the link getting renegotiated right after the first frame and the TV not relocking, not a crash.

Since it happens direct too, I'd look at what the Zidoo changes at playback start:

- Its manual says Auto Frame Rate (Settings > Playback) makes HDMI re-handshake at the start and end of playback, so turn it off for both local and third-party playback as a test.
- Set HDMI signal format to Standard instead of Enhanced (Display > Color Settings).

And yes, moving to HDMI 2 is a meaningful test, TCL's own HDMI troubleshooting suggests a different input first. Unplug both from power for 60 seconds before you retest. If it holds on HDMI 2 with AFR off, you've narrowed it down a lot.
