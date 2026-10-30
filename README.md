# dwm-status

A status bar script for dwm.

![the bar with a scrolling song title](docs/dwm-status.gif)

## What it shows

| Entry | Example | Notes |
|---|---|---|
| music | `♪ Daft Punk - Digital Love 1:23/5:01 🔁` | from [music-menu](https://github.com/sw1jari/music-menu), else Spotify via playerctl |
| focus | `🎯 13:00` or `☕ 14:00` | end of the current block or start of the next, from [focus](https://github.com/sw1jari/focus) |
| RAM | `RAM 16%` | |
| CPU | `CPU 5% Max 9%` | average and the busiest core |
| governor | 🐢 or 🚀 | powersave or performance |
| GPU | `GPU 3% VRAM 5%` | only with `nvidia-smi` |
| battery | `🔋 80%` | ⚡ charging, 🔌 full, notifications at 10% and 5% |
| network | `📶 Home` or `🌐 eth` | |
| date | `Fri 30 Oct 21:06` | |

Music details:
- titles longer than 26 characters scroll like a ticker
- 🔁 repeat all, 🔂 repeat one (Spotify)
- music paused for 10 minutes disappears until it plays again

## Settings

Environment variables, all optional:

| Variable | Default | What it does |
|---|---|---|
| `MUSIC_WIDTH` | 26 | characters before a title scrolls |
| `PAUSED_HIDE_SECONDS` | 600 | how long paused music stays on the bar |

## Install

Needs bash, xsetroot, procps (`free`) and NetworkManager (`nmcli`). Optional: nvidia-smi, playerctl, and dunst or notify-send for the battery notifications.

```sh
cp dwm-status ~/.local/bin/
```

Start it from `~/.xinitrc` before dwm:

```sh
dwm-status &
exec dwm
```
