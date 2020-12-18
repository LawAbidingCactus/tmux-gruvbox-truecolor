# Gruvbox colorscheme for tmux

Retro groove colorscheme for [tmux](https://github.com/tmux/tmux), based on the excellent [gruvbox](https://github.com/morhetz/gruvbox) theme for vim.

<img src="https://i.imgur.com/6IQCia6.png" style="width: 100%; max-width: 600px; text-align: center;"/>

This is a heavily modified fork of [tmux-gruvbox](https://github.com/egel/tmux-gruvbox).

Features/Differences:
- Uses gruvbox's hexadecimal colors (most terminal emulators have truecolor support)
- Indicates when the prefix key has been pressed
- If vi-mode is enabled (if `$EDITOR` contains `vi`), the statusbar will indicate its mode while being edited
- Highlights unfocused windows with activity or terminal bells
- Does not use custom glyphs

## Installation
### Manual
Just clone this repo and add `tmux-colorscheme.conf` to your `.tmux.conf`:
```bash
cat tmux-colorscheme.conf >> ~/.tmux.conf
```
Or move `tmux-colorscheme.conf` to your home directory and source it in `.tmux.conf`:
```tmux
source-file ~/tmux-colorscheme.conf
```
### Tmux Plugin Manager
Add this repo to the list of [TPM](https://github.com/tmux-plugins/tpm) plugins in your `.tmux.conf`:
```tmux
set -g @plugin 'lawabidingcactus/tmux-gruvbox-truecolor'
```
Press `<prefix> + I` to reload tmux with the plugin.

## Troubleshooting
### tmux's colors look weird
Try adding the following to your `.tmux.conf`:
```tmux
set-option -as terminal-overrides ",xterm*:RGB"
```

### Pane separator lines look weird
Something isn't correctly handling UTF-8 line drawing characters.
