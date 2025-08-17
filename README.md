# wofi-emoji 🥞

Simple emoji selector for Wayland using [wofi](https://cloudninja.pw/docs/wofi.html) with localization support through [emojibase](https://github.com/milesj/emojibase).
It relies on [wtype](https://github.com/atx/wtype) to paste the emojis when it's supported, otherwise,
it just tries to copy it using [wl-clipboard](https://github.com/bugaevc/wl-clipboard) instead.

In comparison to the original maintained repo [Zeioth/wofi-emoji](https://github.com/Zeioth/wofi-emoji) this one has multi-language support by fetching the latest [emojibase](https://github.com/milesj/emojibase) and caching it for subsequent uses.

![Screenshot of wofi-emoji in action](https://i.imgur.com/8XiUoh6.png)

## Usage
```bash
Usage: wofi-emoji [OPTIONS]

OPTIONS:
    -l, --languages LANG1,LANG2    Specify languages to fetch (comma-separated)
                                   Available: en, de, es, fr, it, pt, ru, ja, ko, zh, etc.
                                   Default: en
    -f, --force                    Force refresh of cached database
    -h, --help                     Show this help message

Examples:
    wofi-emoji                            # Use English only (default)
    wofi-emoji -l en,de                   # Use English and German
    wofi-emoji -l de,fr,es -f             # Use German, French, Spanish and force refresh even if same languages
```


## Example Configuration for Sway and Hyprland

Download [wofi-emoji](https://github.com/BasicallyPolaris/wofi-emoji/raw/master/wofi-emoji), ensure it's executable and somewhere in your `$PATH`.

Add a shortcut key in your [sway](https://swaywm.org/) config:

```
# ~/.config/sway/config

bindsym Mod4+e exec wofi-emoji
```

Or in your [Hyprland](https://wiki.hypr.land/) Config for Windows-Style emoji functionality:

```
# ~/.config/hypr/config/keybindings.conf

bindd = $mainMod, PERIOD, Emoji Picker, exec, wofi-emoji
```
