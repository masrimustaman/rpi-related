# Raspberry Pi Related
## Taking screenshot (Select Area)
Usually I use Flameshot but at this point of time it is not yet supported in wayland. Therfore we are going to edit the `~/.config/wayfire.ini` and add below
```
binding_screenshot_interactive = <shift> KEY_SYSRQ
command_screenshot_interactive = slurp | grim -g -
```
