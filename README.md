# Vim-ish Key Bindings for PaperWM

These key bindings were heavily modelled after my personal configuration of i3/Sway and are quite similar to the [DWM-ish](https://github.com/paperwm/PaperWM/files/3794708/dwm-ish-bindings.txt) key bindings that emerged from this [issue](https://github.com/paperwm/PaperWM/issues/196).

**Note:** I'm not super happy with the display switching behaviour tied to the <kbd>Alt</kbd> key. If you have suggestions, feel free to open an issue.

## Preview Key Bindings

| Key bindings | Description |
| ----------- | ----------- |
| <kbd>Super</kbd><kbd>j</kbd> | Switch to the below window |
| <kbd>Shift</kbd><kbd>Alt</kbd><kbd>l</kbd> | Move the active window to the right monitor |
| <kbd>Super</kbd><kbd>.</kbd> | Switch to previously active window |
| <kbd>Primary</kbd><kbd>Super</kbd><kbd>k</kbd> | Switch to workspace above |
| <kbd>Super</kbd><kbd>l</kbd> | Switch to the right window |
| <kbd>Alt</kbd><kbd>j</kbd> | Switch to the below monitor |
| <kbd>Shift</kbd><kbd>Alt</kbd><kbd>k</kbd> | Move the active window to the above monitor |
| <kbd>Primary</kbd><kbd>Shift</kbd><kbd>Super</kbd><kbd>k</kbd> | Move window one workspace up |
| <kbd>Shift</kbd><kbd>Super</kbd><kbd>k</kbd> | Move the active window up |
| <kbd>Shift</kbd><kbd>Super</kbd><kbd>g</kbd> | Switch to the last window |
| <kbd>Super</kbd><kbd>g</kbd> | Switch to the first window |
| <kbd>Super</kbd><kbd>,</kbd> | Switch to previously active window, backward order |
| <kbd>Primary</kbd><kbd>Shift</kbd><kbd>Super</kbd><kbd>j</kbd> | Move window one workspace down |
| <kbd>Primary</kbd><kbd>space</kbd> | Toggles the floating scratch layer |
| <kbd>Super</kbd><kbd>h</kbd> | Switch to the left window |
|  | Switch to the next window |
|  | Close the active window |
| <kbd>Primary</kbd><kbd>Super</kbd><kbd>j</kbd> | Switch to workspace below |
| <kbd>Super</kbd><kbd>k</kbd> | Switch to the above window |
| <kbd>Primary</kbd><kbd>Shift</kbd><kbd>Super</kbd><kbd>h</kbd> | Switch to the previously active workspace, backward order |
| <kbd>Shift</kbd><kbd>Super</kbd><kbd>h</kbd> or <kbd>Super</kbd><kbd>Shift</kbd><kbd>,</kbd> or <kbd>Super</kbd><kbd>Ctrl</kbd><kbd>Left</kbd> | Move the active window to the left |
| <kbd>Shift</kbd><kbd>Super</kbd><kbd>l</kbd> or <kbd>Super</kbd><kbd>Shift</kbd><kbd>.</kbd> or <kbd>Super</kbd><kbd>Ctrl</kbd><kbd>Right</kbd> | Move the active window to the right |
| <kbd>Alt</kbd><kbd>l</kbd> | Switch to the right monitor |
| <kbd>Primary</kbd><kbd>Shift</kbd><kbd>Super</kbd><kbd>l</kbd> | Move the active window to the previously active workspace, backward order |
| <kbd>Shift</kbd><kbd>Alt</kbd><kbd>j</kbd> | Move the active window to the below monitor |
| <kbd>Alt</kbd><kbd>h</kbd> | Switch to the left monitor |
|  | Switch to the previous window |
| <kbd>Primary</kbd><kbd>Super</kbd><kbd>l</kbd> | Move the active window to the previously active workspace |
| <kbd>Alt</kbd><kbd>k</kbd> | Switch to the above monitor |
| <kbd>Primary</kbd><kbd>Shift</kbd><kbd>space</kbd> | Attach/detach the active window into the scratch layer |
| <kbd>Shift</kbd><kbd>Super</kbd><kbd>j</kbd> | Move the active window down |
| <kbd>Primary</kbd><kbd>Super</kbd><kbd>h</kbd> | Switch to previously active workspace |
| <kbd>Shift</kbd><kbd>Alt</kbd><kbd>h</kbd> | Move the active window to the left monitor |

**Note:** there is a conflict with the default <kbd>Super</kbd> + <kbd>Shift</kbd> + <kbd>h</kbd> and <kbd>Super</kbd> + <kbd>Shift</kbd> + <kbd>j</kbd> shortcuts in Gnome. I simply disabled those before coming up with my own, so be aware of that fact before proceeding.

## Install

_This section has been entirely poached from the [Alternative keybindings](https://github.com/paperwm/PaperWM/wiki/Alternative-keybindings) page. So my thanks to [Ole Jørgen Brønner](https://github.com/olejorgenb) for his original contributions!_

```
# Backup your original key bindings for PaperWM
PREV_BINDINGS=paperwm-bindings-$(date +%F_%T).txt
dconf dump /org/gnome/shell/extensions/paperwm/keybindings/ > $PREV_BINDINGS

# Download Vim-ish PaperWM Key Bindings
wget https://raw.githubusercontent.com/trst/PaperWM-Vim-ish-Keybindings/master/paperwm-vim-ish-keybindings.txt

# Reset PaperWM to default; Skip this if you haven't made any modifications
dconf reset -f /org/gnome/shell/extensions/paperwm/keybindings/

# Load Vim-ish PaperWM Key Bindings
cat paperwm-vim-ish-keybindings.txt | dconf load /org/gnome/shell/extensions/paperwm/keybindings/
```

## Restore Your Previous Key Bindings

Oh no, has something gone wrong? Don't worry, you can easily revert to your previous key bindings, or go back to the default bindings.

To restore your previously backed up key bindings (see the Install section above):

```
# Reset PaperWM to default
dconf reset -f /org/gnome/shell/extensions/paperwm/keybindings/

# Load Backed Up PaperWM Key Bindings
cat $PREV_BINDINGS | dconf load /org/gnome/shell/extensions/paperwm/keybindings/
```

Or, to simply nuke and pave (i.e., restore the default PaperWM key bindings):

```
# Reset PaperWM to default
dconf reset -f /org/gnome/shell/extensions/paperwm/keybindings/
```
