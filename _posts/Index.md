# yt-dlp & ffmpeg

## yt-dlp Choosing a Download Format

To view a comprehensive list of all the available formats for a video or playlist, utilize the following command:

yt-dlp -F [url]

By default, yt-dlp will download videos in the best available quality if you don't pass any options. However, you have the flexibility to download a video or playlist in a specific quality or format as per your preferences.

So for example. -F on this vid https://youtu.be/8zDX1hztNHA?si=5E9yTKkfZj4VoZDL
yt-dlp -f 243 https://youtu.be/8zDX1hztNHA?si=5E9yTKkfZj4VoZDL 

//or example, if you want to download the video in the best available quality for both audio and video, use this command:
//yt-dlp -f best https://www.youtube.com/watch?v=t5b20oLaIaw
//Similarly, to download audio-only with the best quality:
//yt-dlp -f bestaudio <URL>
//You can even download a video or playlist in a specific quality with a defined resolution. For example, to download the best quality video with a resolution of 480 pixels or lower (less than or equal to 480p), use this command:
//yt-dlp -f "best[height<=1440]" <URL>

## yt-dlp Audio
yt-dlp -x https://youtu.be/bXL13mGQ2sc


yt-dlp -x --audio-format mp3 [url]

## Using ffmpeg to convert audio files to mp3

If you already have an audio file downloaded, you can convert the format to mp3 using ffmpeg:

`
ffmpeg -i [inputfile].opus [outputfile].mp3
`
Where
-i: input