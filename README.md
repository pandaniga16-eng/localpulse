# Low quality video (about 8 MB per 4 min)
ffmpeg -i in.mp4 -vf scale=-2:360 -c:v libx264 -crf 30 -preset slow -c:a aac -b:a 64k -movflags +faststart media/name-360p.mp4
# Mid quality video (about 14 MB per 4 min)
ffmpeg -i in.mp4 -vf scale=-2:480 -c:v libx264 -crf 28 -preset slow -c:a aac -b:a 80k -movflags +faststart media/name-480p.mp4
# HD video
ffmpeg -i in.mp4 -vf scale=-2:720 -c:v libx264 -crf 26 -preset slow -c:a aac -b:a 96k -movflags +faststart media/name-720p.mp4
# MP3 (small)
ffmpeg -i in.mp4 -vn -c:a libmp3lame -b:a 96k media/name.mp3
# Thumbnail
ffmpeg -i in.mp4 -ss 5 -vframes 1 -vf scale=480:-2 -q:v 8 thumbs/name.jpg
