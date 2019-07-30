# radio-play

### it is a BASH Script to listen to any radio (including Youtube Live streams) on the background of your computer.

## Creation
It was develop on a Linux OS (but will work on any OS. If it isn't working on your OS, you just need to edit some configuration files).  
This script source code was made to be very flexible, so that easily integrates any OS.  

Some dependencies are needed...  

## Dependencies

* Any Multimedia Player (`mpv` is recommended and is the default one. `vlc` may also work - but it is not the one I recommend)
* `youtube-dl` (which is for playing Youtube Live streams using `mpv`)

The rest of the dependencies you may already have on your Linux OS, which are:

* `notify-send`
* `mkdir`
* `egrep`
* `dirname`
* `basename`
* `cut`
* `which`
* `pkill`
* `sed`
* `wc`
* `touch`
* `curl`
* `head`

* the rest are built-in bash shell commands such as `echo`, `exit`, `return`, `test`/`[`, `printf` and control flow bash constructs (if, then. else, fi, ... - well check the damn source code if you want to know more :smile: ! :sunrise_over_mountains: )

## Installation

### Easy way

Open a terminal window (optionally `cd` to a `$PATH` directory) and do:
```
wget https://raw.githubusercontent.com/alexandre1985/radio-play/master/radio-play && chmod +x radio-play
```

### Complete explanation

Just download `radio-play` script. You may want to put the script in a `$PATH` directory (for running `radio-play` without needing `radio-play` full path for its execution).

After you have made the download, don't forget to give `radio-play` executable permissions. You can give those by using the command `chmod +x radio-play`.

## Configurations

### Configuration Directory

If `XDG_CONFIG_HOME` variable is set, `$XDG_CONFIG_HOME/radio-play/` will be the configuration directory. Or else will be `$HOME/.config/radio-play/`.

### Configuration Files

There are two configuration files for this script, that live inside the [Configuration Directory](#configuration-directory) (which probably is located on `$HOME/.config/radio-play/`). They are `main.conf` and `radios.conf`.  

#### main.conf

This configuration file is generated automatically by running this script (`radio-play`) for the first time.  
Generally you should not need to modify this file for the `radio-play` bash script to work. If `radio-play` is not working, you may modify some variables of `main.conf` to match your OS.  
I have tried my best to document well `main.conf`, so you can understand how to modify/configure it.  

#### radios.conf

This file it is not generated automatically, and is optional.  
It is meant for creating easy to remember alias of your `radio-play` usage.  

For example, you have this radio that you listen all the time. It is called Chillhop and its URL is `http://www.youtube.com/watch?v=hHW1oY26kxQ`. So instead of running `radio-play http://www.youtube.com/watch?v=hHW1oY26kxQ` all the time you want to listen to it, you may put this line in your `radios.conf` file.

```
chillhop=http://www.youtube.com/watch?v=hHW1oY26kxQ
```

Now you may use `radio-play chillhop` the next time you want to listen to your favorite radio :wink: 

`radios.conf` may have any number of alias (in the *alias*=*streamURL* format).

## Limitation

`radio-play` in the future, will make a check to only accept online URL, but - when it does - it has no way to verify if the URL is referring to a playable URL (such as for example .ogg, .m3u, .mp3, .mpg). So, insert only URLs that the program in the variable `PLAYER_COMMAND` (locate in the `main.conf` configuration file. The default player program is `mpv`) accepts.

## Conclusion

I believe that is everything. I want you to be able to learn/edit/share this code with anyone, so for lack of knowledge of the licenses world, I will put this code under MIT license.  

If you want to give me some gift for creating this code, or just want to say something to me, go to [my personal page](https://alexandre1985.github.io/) and you can contact me throw there (using the personal page contact form).

Have fun :wink:
