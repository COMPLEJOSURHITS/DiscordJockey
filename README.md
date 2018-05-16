# DiscordJockey

DiscordJockey is an open source, lightweight musicbot for Discord. It was written in python using [Discord.py](https://discordpy.readthedocs.io/en/rewrite/). It can stream music from sites like youtube straight to your Discord voice channels and helps you create a more chill atmosphere while enjoying your favourite games.

## Getting Started

I am offering a hosted version of the bot, you just need to go to the following link and add it to your server. Easy as that.
https://discordapp.com/oauth2/authorize?client_id=444808632706662400&scope=bot

To learn more about the features of DiscordJockey, type !help in your serverchat or read the documentation below.

If you want to run the bot on your local machine or a server, see the instructions below.

### Prerequisites

You need to have a version of python3 installed on your machine.
If you are windows, make sure that the executable is added to PATH. [How to do it on Windows 10](https://stackoverflow.com/questions/44272416/how-to-add-a-folder-to-path-environment-variable-in-windows-10-with-screensho)

You also need the newest versions of aiohttp, youtube-dl and bs4, as well as the rewrite version of Discord.py. To install those, simply us ethe following pip command
```
pip install -U aiohttp youtube-dl bs4 git+https://github.com/Rapptz/discord.py@rewrite#egg=discord.py[voice]
```

On Linux, you might also need to install some additional packages:

```
apt-get install libffi-dev libnacl-dev python3-dev ffmpeg
```

### Installing - Hosting the bot yourself

The setup is really straight forward, you just need to download this repository, copy it to wherever you like and run the startup.bat or startup.sh script, based on you OS. Alternatively, you can also run the run.py script with python via your console from the root directory of the project. 

After you got the bot running, you need to create a new application [here](https://discordapp.com/developers/applications/me) and turn it into a Bot-User via the "Create a Bot User" button on the lower half of you app review. At last, you need to add the bot to your server. [Here is a simple explanation on how to do that.](https://github.com/jagrosh/MusicBot/wiki/Adding-Your-Bot-To-Your-Server) 

The bot should join you server automatically. If nothing happens, just try restarting the python script and everything should work as intended ;-)

## Usage

After the bot has joined your server, you can pm him !help or write it in a textchannel to get an overview of the available commands. At the moment, the following commands are supported:

```
!connect [channel (optional)]
```

* Connects the bot to a voice channel. Connects to the first one if no name is specified or the channel does not exist.

```
!disconnect
```

* Disconnects the bot from the current voice channel.

```
!cc [channel]
```

* Moves the bot to another channel.

```
!addbot
```

* Displays information on how to add the bot to another server of yours.

```
!yt [link/video title/key words/playlist-link]
```

* Plays the audio of a Youtube video. The argument can either be:
    - A link to the video (https://ww...)
    - The title of a video (Rick Astley - Never Gonna Give You Up)
    - Keywords for a search(lofi hip-hop) - the bot plays the first result
    - A link to a playlist - the bot plays the songs in order
 * If the player is already playing, the command adds the song to a queue and plays them in succession
 
```
!spotify [nickname (optional)]
```

* Gives you an easy way to share a song from Spotify via the bot.
    * Spotify needs to be linked to your Discord account for this to work.
    * The command takes the song that is being played by your Spotify client and plays it on the bot via Youtube.
    * You can target another users client by specifying his nickname as an argument.
    * The song has to be playing for the command to launch, so you need to listen for the first few seconds of the song while the bot loads it up.
    * If the player is already playing, the command adds the song to the playingqueue.
    * The bot is not 100% accurate and plays slightly different versions of the songs every now and then.
    
```
!pause
```

* Pauses the current song.

```
!resume
```

* Resumes the paused song.

```
!stop
```

* Stops the current song and clears the playqueue.

```
!skip
```

* Stops the current song and plays the next one in the queue.

```
!prev
```

* Goes back one song and plays the last song again.

```
!vol [volume in %]
```

* Changes the volume of the music player. (0-200%)

```
!songinfo
```

* Shows more details about the current song.

```
!history
```

* Shows you the titles of the 15 last played songs.


## Authors

* **Adrian Steffan**


## License

This program is free software: you can redistribute it and/or modify
it under the terms of the [GNU General Public License](LICENSE.txt) as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

## Acknowledgments

Shoutout to the community over at the Discord-API Discord servers, who gave me a helping hand when the Rewrite library gave me headaches.

