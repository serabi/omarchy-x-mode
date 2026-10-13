# Glass dock

This fork makes the dock a rounded, translucent, frosted pane instead of a
square card. The QML changes are in `quickshell/x-mode/Dock.qml` (radius,
fill, rim, sheen) and `DockMenu.qml` (matching right-click menu). The frost
itself comes from Hyprland, which lives outside the pack:

## Hyprland blur (`~/.config/hypr/looknfeel.lua`)

Append [`looknfeel.lua`](looknfeel.lua) to `~/.config/hypr/looknfeel.lua`,
then `hyprctl reload` and check `hyprctl configerrors` is empty.

## Tuning

- Corner roundness: `dockRadius` in `Dock.qml` (16, capped at half the dock width)
- See-through amount: `Util.alpha(Color.background, 0.45)` on `dockBg`
- Frost strength: blur `size` / `passes` in `looknfeel.lua`

## Restoring on a fresh install

```bash
git clone https://github.com/serabi/omarchy-x-mode
cd omarchy-x-mode && ./install.sh
```

Then add the Hyprland snippet above.

## Pulling in upstream updates

```bash
git fetch upstream
git merge upstream/main
git push origin main
./install.sh
```
