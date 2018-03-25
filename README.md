# ffmpeg

## Envode video

### Youtube
[Youtube recommended upload encoding settings](https://support.google.com/youtube/answer/1722171?hl=en)

#### ffmpeg options to convert video for youtube

`ffmpeg -i <input_file> -codec:v libx264 -crf 18 -bf 2 -flags +cgop -pix_fmt yuv420p -codec:a aac -ar 48000 -b:a 384k -movflags faststart <output_file.mp4>`

----

### Streamable
[Streamable recommended Video Settings](https://support.streamable.com/recommended-video-settings)

#### ffmpeg options to convert video for streamable (it also works for FullHD video prepaired for youtube)

`ffmpeg -i <input_file> -codec:v libx264 -s hd720 -crf 18 -bf 2 -flags +cgop -pix_fmt yuv420p -codec:a copy -movflags faststart <output_file>.mp4`

> Note that these settings are the same as in Youtube section, but the keys \
> `-s hd720` was added \
> `-codec:a aac -ar 48000 -b:a 384k` was changed to `-codec:a copy`

## [Cut video](https://trac.ffmpeg.org/wiki/Seeking)

`ffmpeg -i <input_file> -c copy -ss <time_from> -to <time_to> <output_file>`

> **<time_from>** and **<time_to>** can be in two formats: **hh:mm:ss[.xxx]** or **ss[.xxx]**

## [Join video](https://trac.ffmpeg.org/wiki/Concatenate)

To concatenate two or more parts, create a file **list.txt** and add file names like there:
```
file 'file1.avi'
file 'file2.avi'
file 'file3.avi'
```
Then execute

`ffmpeg -f concat -i .\list.txt -c copy <output_file>`
