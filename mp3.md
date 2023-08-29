# MP3's for music
MP3 files have the benefit of being very small at the cost of being generally low quality. They're also much easier to obtain than FLAC's, especially when talking about a large library (or playlist).

There are multiple programs for this across both Windows and Linux.

The first one you should use if you can is [spotdl](https://github.com/spotDL/spotify-downloader). 
This will allow you to download songs with proper metadata (so things likesong album/song name basically), embedded lyrics (meaning a local player can show lyrics- though this isn't generally too accurate), and a proper image for the song to show on a local player.

## Windows
### Spotdl
Download python from [the python website](https://www.python.org/downloads/) (if it isn't already installed), choose the newest download, and when installing it make sure to check the box that says `Add python <PYTHONVERSION> to PATH`, `<PYTHONVERSION>` being the version of python you downloaded. This ensures that it works.

Then, open up command prompt and type `pip install spotdl`. This should install spotdl on your computer. It may give you warning, but it should still work.

Once you do this, you can run `spotdl --version` in the command prompt to ensure that spotdl is installed properly. If it returns a number, that means you're good to continue.

From here you can run `cd` (which means `c`hange `d`irectory) and navigate to the place you want to download songs. Simply running `cd music` will place you in the `music` directory you can easily see in file explorer.
If you want to change to a specific spot or seperate drive, open the spot you want to go to in file explorer, then click on the adress bar on the top (shown below), hit `ctrl c` to copy it, then run `cd PastedFileLocation`, `PastedFileLocation` being replaced by the location you copied earlier

After doing this, you can simply run `spotdl <SPOTIFYLINKHERE>`, replacing `<SPOTIFYLINKHERE>` with a song or playlist link (as long as it's public), and it'll download the entire playlist in MP3 format.\
This does however have some caveats. Namely, it uses YouTube music to download the files, so if a song isn't on there, you won't be able to use spotdl to get it.\
There's also a chance spotdl grabs a cover of the song, or just the wrong song entirely when downloading a song.\
These can both (usually) be solved by using yt-dlp to fill in the gaps, which will be discussed here:

### yt-dlp

[yt-dlp](https://github.com/yt-dlp/yt-dlp) is a program that lets you download YouTube videos from command prompt easily.

To download it, go to the [releases page](https://github.com/yt-dlp/yt-dlp/releases), download the `yt-dlp.exe` file, then simply run the `.exe` that gets downloaded. 

Once you do this, you can use `cd` in the way we did before to get to the place you want to download music again (though I'd suggest you try using `cd downloads` to place the file in your downloads instead. Note that the date created will be the date of the video, so it may be far back in your downloads)

Then, run `yt-dlp -x --audio-format mp3 --embed-thumbnail --convert-thumbnails jpg --embed-metadata --add-metadata --compat-options embed-metadata -o "%(uploader)s - %(title)s.%(ext)s" <YOUTUBELINKHERE>`, replacing `<YOUTUBELINKHERE>` with a YouTube link to the song you want to download.\
The way this command works is that you run `yt-dlp` with the `-x` argument to extract the audio from the video, `--audio-format mp3` to tell yt-dlp to change the end file to be an mp3, `--embed-thumbnail` to tell yt-dlp to embed the thumbnail in the video as the cover art, 
`--convert-thumbnails jpg` to convert the previous thumbnail to a `.jpg`, then `--embed-metadata` and `--add-metadata` to add metadata to the file, then `--compat-options` to tell yt-dlp to use `youtube-dl` options (basically the older version of yt-dlp),
`-o` tells yt-dlp to prepare for changing the output file, and then the `"%(uploader)s - %(title)s.%(ext)s"` section tells yt-dlp to name the file as `Uploader - Title`.

This will download the specified video in mp3 quality to the directory that you're in.\
This does have some issues however, mainly regarding the metadata.

This will download the YouTube thumbnails as is. Music on YouTube (not YouTube music) seems to have proper album art, but it doesn't in reality. It has colors on the left and right side of the image that are generally dropped out when listening to it.\
This doesn't actually matter, but if it's only a few songs it can be nice to change it to be proper.\
This will also download the 
This is covered in the [changing metadata section](metadata.md).

### Playing music

For Windows, you can simply open the songs and they'll open in Windows Media Player. This is fine, but if you're locally hosting music you may want to look into an actual music player. 
You can look at the [music player section](players.md) to see how to use some that I use and recommend.
