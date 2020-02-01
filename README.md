# ffmpeg notes

### **Useful Commands**

1. `ffmpeg -i testvid.mp4 -ss 00:00:14 -codec copy -t 8 shortenedTestVid.mp4`

This command will trim a video clip to a shorter time. It takes an input (`-i`) testVid.mp4 and at `-ss` 00:00:14 creates an 8 second shortenedTestVid.mp4. `-ss` indicates the starting second of the clip. `-t` indicates how long we want to trim the clip down to, in our case 8 seconds.

2. `ffmpeg -i testVid.mp4 -r 100 -f image2 image-%2d.png`

This command will create frames from a video. `-i` flags the input video. `-r` sets the framerate, i.e. 100 frames per second. `-f` sets the output format and creates the files. In this case, `testVid.mp4` is 8 seconds long, at an `-r` of 100 it will extract and output **800** new images created from frames of the inputted video titled `image-01.png` all the way to ~ `image-800.png`

