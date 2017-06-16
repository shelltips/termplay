# play-youtube

Are you a terminal fanboy like me?  
Sure, but do you ever watch YouTube? In your terminal?

----------------------------------------------------

`play-youtube` is the tool to play YouTube... Converted to ANSI escape sequences...  
Written in the systems language Rust, it has more performance than any bash script could.

 - **Concurrency**
   - It's converting to ANSI while `ffmpeg` is still processing!
 - **Audio/Frame Sync**
   - If one frame takes longer to load and the audio continues on,
   - don't just pretend nothing happened! Skip a few frames!
   - Get back on track!
 - **TrueColor** and **256-bit color**
   - Choose whatever is supported by your terminal!
 - **Adapting size**
   - Automatically scales the video to fit your terminal
 - **Flexible**
   - Change framerate, size and more using command line switches

## Compatibility

This tool is tested in GNOME Terminal and Konsole.  
Might not be fully or supported at all by whatever terminal you use.

## Switches

```
play-youtube 0.1.0
LEGOlord208 <LEGOlord208@krake.one>
Play YouTube in your terminal!

USAGE:
    play-youtube [OPTIONS] <VIDEO>

FLAGS:
        --help       Prints help information
    -V, --version    Prints version information

OPTIONS:
    -w, --width <width>            The max width of the video
    -h, --height <height>          The max height of the video
        --converter <converter>    How to convert the video. [default: truecolor]  [values: truecolor, 256-color]
    -f, --format <format>          Pass format to youtube-dl. [default: worstvideo+bestaudio]
    -r, --rate <rate>              The framerate of the video [default: 10]

ARGS:
    <VIDEO>    The video URL to play
```

## Installing

... That said, it comes with a slight flaw. **For now**, you have to compile yourself.  
No big deal though.
The only external package libraries needed to install are the ones required by [ears](https://github.com/jhasse/ears).  

On Ubuntu, a full installation from nothing (not even Rust installed) would look like
```bash
curl https://sh.rustup.rs -sSf | sh
sudo apt install libopenal-dev libsndfile1-dev ffmpeg
sudo -H pip install --upgrade youtube-dl # Sudo is required if you're not using a single user python installation

git clone git@github.com:legolord208/play-youtube.git
cd play-youtube
cargo build --release
```
Poof! `targets/release/play-youtube` is created

# Future plans

This application will probably become `ansi-tool` with multiple subcommands like `image`, `video` and, of course, `youtube`.  
This would allow using this application for more videos/images than just YouTube.
