# dwm-status

A status bar script for dwm that updates every second.

![the bar with a scrolling song title](docs/dwm-status.gif)

It shows:
- RAM use
- average CPU use and the busiest core
- the CPU governor (🐢 powersave, 🚀 performance)
- GPU use and VRAM, if `nvidia-smi` is available
- battery level and charging state, with a notification at 10% and 5%
- the wifi network, or "eth" when connected by ethernet
- the date and time
- the current track from [music-menu](https://github.com/sw1jari/music-menu), or else from Spotify (via playerctl), when something is playing or paused. It shows the time into the song and its length, and for Spotify 🔁 or 🔂 when on repeat all or repeat one. Titles longer than 26 characters scroll left like a ticker; set `MUSIC_WIDTH` to change that limit. Music that stays paused for 10 minutes drops off the bar until it plays again; set `PAUSED_HIDE_SECONDS` to change that
- the [focus](https://github.com/sw1jari/focus) blocker, 🎯 with the time the current focus block ends, or ☕ with the time the next one starts during a break

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
