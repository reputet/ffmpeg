# ffmpeg

## Youtube
[Youtube recommended upload encoding settings](https://support.google.com/youtube/answer/1722171?hl=en)

### ffmpeg options to convert video for youtube

`ffmpeg -i <input_file> -codec:v libx264 -crf 18 -bf 2 -flags +cgop -pix_fmt yuv420p -codec:a aac -ar 48000 -b:a 384k -movflags faststart <output_file.mp4>`

----

## Streamable
[Streamable recommended Video Settings](https://support.streamable.com/recommended-video-settings)

### ffmpeg options to convert video for streamable (it also works for FullHD video prepaired for youtube)

`ffmpeg -i <input_file> -codec:v libx264 -s hd720 -crf 18 -bf 2 -flags +cgop -pix_fmt yuv420p -codec:a copy -movflags faststart <output_file>.mp4`

> Note that these settings are the same as in Youtube section, but the keys \
> `-s hd720` was added \
> `-codec:a aac -ar 48000 -b:a 384k` was changed to `-codec:a copy`
