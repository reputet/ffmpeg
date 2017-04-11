# ffmpeg
ffmpeg options to convert video for youtube

`ffmpeg -i <input_file> -codec:v libx264 -crf 18 -bf 2 -flags +cgop -pix_fmt yuv420p -codec:a aac -ar 48000 -b:a 384k -movflags faststart <output_file>`
