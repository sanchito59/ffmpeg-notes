# ffmpeg notes

# **Useful Commands**

## Trim a video

### 1. `ffmpeg -i testvid.mp4 -ss 00:00:14 -codec copy -t 8 shortenedTestVid.mp4`

This command will trim a video clip to a shorter time. It takes an input `-i` testVid.mp4 and at `-ss` 00:00:14 creates an 8 second shortenedTestVid.mp4. The flag `-ss` indicates the starting second of the clip, and `-t` indicates how long we want to trim the clip down to, in our case 8 seconds.

## Extract frames from a video

### 2. `ffmpeg -i testVid.mp4 -r 100 -f image2 image-%2d.png`

This command will create frames from a video. `-i` flags the input video. `-r` sets the framerate, i.e. 100 frames per second. `-f` sets the output format and creates the files. In this case, `testVid.mp4` is 8 seconds long, at an `-r` of 100 it will extract and output **800** new images created from frames of the inputted video titled `image-01.png` all the way to approximately `image-800.png`.  

**To save space, you can also output images to `.bmp` file format.**

## Test/Preview video

### 3. `ffplay testVid.mp4`

This command will preview a video in your system's default player.

## Test/Preview audio track

### 4. `ffplay testAudio.mp3`

This command will preview an audio track in your system's default player.

## Decrease video playback speed

### 5. `ffmpeg -i testVid.mp4 -vf "setpts=4.0*PTS" playbackDecreased.mp4`

This command will decrease the playback speed of a video. `"setpts=4.0*PTS"` To decrease the playback speed of a video, your must multiply by a number that is **greater than** 1, i.e. your value in `num*PTS"`.

## Increase video playback speed

### 6. `ffmpeg -i testVid.mp4 -vf "setpts=0.5*PTS" playbackIncreased.mp4`

This command will increase the playback speed of a video. `"setspts=0.5*PTS"` will double the speed of your video. To increase the speed of your video, you must multiply by a number **less than** 1, i.e. your value in `num*PTS`.


