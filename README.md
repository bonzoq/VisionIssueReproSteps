## Vision + CoreML + YUV buffers memory leak issue

### Description

There seems to be a memory leak when Vision framework is used with CoreML to process images coming from ARKit (YUV encoded CVPixelBuffers). 

### Steps to reproduce

1. Download sample Apple's app that uses Vision, CoreML and ARKit from https://developer.apple.com/documentation/arkit/using_vision_in_real_time_with_arkit?language=objc
2. Change `classificationRequest`'s `imageCropAndScaleOption` property from `.centerCrop` to `.scaleFit`.
3. Run the app and observer memory usage. It grows by 1 MB every 1-2 seconds. 

I've submitted an Apple Radar report #39832723.








