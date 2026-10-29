# dwm-status

A status bar script for dwm that updates every second.

It shows:
- RAM use
- average CPU use and the busiest core
- the CPU governor (🐢 powersave, 🚀 performance)
- GPU use and VRAM, if `nvidia-smi` is available
- battery level and charging state, with a notification at 10% and 5%
- the wifi network, or "eth" when connected by ethernet
- the date and time
- the current track from [music-menu](https://github.com/sw1jari/music-menu), or else from Spotify (via playerctl) with the time into the song and its length, when something is playing or paused. Titles longer than 50 characters scroll left like a ticker; set `MUSIC_WIDTH` to change that limit

## Requirements
bash, xsetroot, procps (`free`), NetworkManager (`nmcli`), optionally nvidia-smi.

For the low battery notifications it uses `dunstify` if installed, otherwise `notify-send`. Without either, it still works but stays silent.

## Install
```sh
cp dwm-status ~/.local/bin/
```
Start it from `~/.xinitrc` before dwm:
```sh
dwm-status &
exec dwm
```
