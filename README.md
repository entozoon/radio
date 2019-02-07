# Radio

Omega2 based, voice-controlled, Youtube streaming audio player (maybe radio too, who knows).

## Install

    sudo apt-get update

## Install pip/mps-youtube

    sudo apt-get install python3-pip
    pip3 install --user mps-youtube

## Dev version (necessary!)

    pip3 install --user -U git+https://github.com/mps-youtube/mps-youtube.git

## youtube-dl

    pip3 install --user youtube-dl

## Set mpsyt to use mplayer

    sudo apt-get install mplayer
    mpsyt set player mplayer
    exit

## Through usb

    mpsyt set playerargs -really-quiet -ao alsa:device=hw=1.0

## Mono (probably don't do this though, eh), add to above

    -af extrastereo=0

## Play a song

    mpsyt /chandelier, 1
    mpsyt --debug /chandelier, 1

## Node context / closing

Stick an & on the end of mpsyt command probs. Then smash it closed with

    sudo killall -q mpsyt

## Equaliser (alsamixer)

    https://docs.onion.io/omega2-docs/usb-playing-audio.html

## Alternative version

There's some way of streaming, supposedly:

    url="$my_url";
    file=$(youtube-dl -s -e https://www.youtube.com/watch?v=fWvKvOViM3g);
    wget -q -O - `youtube-dl -b -g https://www.youtube.com/watch?v=fWvKvOViM3g`| ffmpeg -i - -f mp3 -vn -acodec libmp3lame -| mpg123 -
