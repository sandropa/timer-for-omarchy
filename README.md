# timer

A minimal terminal timer with Waybar integration.

## Setup

```sh
git clone https://github.com/sandropa/timer-for-omarchy.git ~/.local/src/timer-for-omarchy
ln -s ~/.local/src/timer-for-omarchy/timer ~/.local/bin/timer
```

Add to your Waybar config (`~/.config/waybar/config`):

```jsonc
"custom/timer": {
    "exec": "cat /tmp/timer-status 2>/dev/null",
    "interval": 1,
    "format": "{}"
}
```

Then add `"custom/timer"` to `modules-left`, `modules-center`, or `modules-right` to place it on your bar.

## Usage

| Command | Description |
|---|---|
| `timer <minutes>` | Start a timer (replaces any running timer) |
| `timer pause` | Pause the current timer |
| `timer resume` | Resume a paused timer |
| `timer status` | Show remaining time (HH:MM:SS) |
| `timer stop` | Stop and clear the timer |

Waybar displays time as HH:MM. The `status` command gives HH:MM:SS.

### Examples

```sh
timer 90             # start a 90-minute timer
timer 25             # restart with a new 25-minute timer
timer pause          # Paused at 01:23:41
timer resume         # Resumed. 01:23:41 remaining
timer status         # 00:03:15 remaining
timer stop           # Timer stopped.
```