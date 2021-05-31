# Convertidor de Video a GIF    

    $ sudo apt-get install ffmpeg
    $ ffmpeg \
      -i video.mp4 \
      -r 15 \
      -vf scale=512:-1 \
      -ss 00:00:01 -to 00:01:51 \
      video.gif
    
---

Fuentes:

+ https://askubuntu.com/questions/648603/how-to-create-an-animated-gif-from-mp4-video-via-command-line