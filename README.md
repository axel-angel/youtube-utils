youtube-utils
=============

Super scripts to watch, download and search Youtube from the shell

youtube:
--
Script that eats a youtube url and play it with mplayer (youtube-dl backend).
This may be changed to open the preferred player or use a configuration file.
The options are hard-coded right now. I've written a quvi backend that I could
publish if necessary. You can give extra options to your player at the end of the line.

eg:
```
youtube 'http://www.youtube.com/watch?v=ofaNR_HnUMI' -loop 0
```

youtube-fast:
--
Download a youtube video given the url. This leverages the initial boost burst
in the youtube servers (wget). Use like `youtube`.


youtube-playlist:
--
Play a whole playlist given its PID. It invokes youtube for each video
separately. You can give extra parameters to your player.

eg:
```
youtube-playlist PLE75A1800C20D8675 -novideo
```


youtube-search:
--
Search youtube videos in an interactive and configurable prompt. By default the program show the video name and asks the user before playing each video. Arguments: first one is the query, then youtube-search arguments, then player extra options. Arguments eaten by youtube-search are all the understood options until it founds an unknown ones, which are passed rawly to `youtube`.

eg:
```
youtube-search 'my little pony'
youtube-search 'dark ambient music' --playlist -novideo
```

youtube-search options (long and short):
```
    -p|--playlist
        Play all videos without user interaction.
    -1|--first
        Stop after playing the first video.
    -s|--skip
        Number of videos to skip (without interaction).
    -u|--user
        Search among the given user videos.
    -m|--music
        Don't show the player window, only play the sound.
    -b|--batch
        Only prints in a usable formats and play nothing.
    --max
        The maximum number of videos to watch (useful with --batch)
```
