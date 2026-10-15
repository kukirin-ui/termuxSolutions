# Android (Kotlin): isolating an object from the live camera

XDA post: https://xdaforums.com/goto/post?id=90778058

**Question:** Ready made segmentation APIs only partly select the object on a live camera feed.

## Answer

The partial select you are getting is pretty much what those ready made APIs do when you treat a live feed like a still cutout.

Google ML Kit Subject Segmentation is the closest built-in for isolating an object from the background, but it only runs on static images, not a continuous camera stream. MediaPipe Interactive Image Segmenter is the same idea with a tap or stroke: you feed it one MPImage, call setImage, then segment with a NormalizedKeypoint where the user touched. Their sample is gallery based (https://github.com/google-ai-edge/mediapipe-samples under examples/interactive_segmentation/android), so for live camera you grab a CameraX frame, freeze it, and run that on the bitmap.

If you want masks every frame without a tap, that is MediaPipe Image Segmenter in RunningMode.LIVE_STREAM with segmentAsync. That only works for the categories the model was trained on (person/selfie style masks and so on), not for picking an arbitrary object with hollows and ignoring neighbors.

So for what you described, freeze a frame and use Interactive Segmenter on the tap point, then draw the confidence mask. If edges and curves keep getting clipped, you are probably thresholding the mask too high or still using a detector bounding box instead of the mask pixels.
