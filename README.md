<p align="center">
# dotfiles
Dotfiles for my arch based hyprland rice.
</p>

<p align="center">
  <a href="#-overview">Overview</a> &nbsp;&bull;&nbsp;
  <a href="#-dependencies">Dependencies</a> &nbsp;&bull;&nbsp;
  <a href="#-installation">Installation</a> &nbsp;&bull;&nbsp;
  <a href="#-keybinds">Keybinds</a>
</p>

---

### ~ Overview

| Component | Tool |
|---|---|
| **WM** | [Hyprland](https://hyprland.org) |
| **Bar** | [Waybar](https://github.com/Alexays/Waybar) |
| **Terminal** | [Kitty](https://sw.kovidgoyal.net/kitty/) |
| **Launcher** | [Rofi](https://github.com/davatorium/rofi) |
| **Notifications** | [SwayNC](https://github.com/ErikReider/SwayNotificationCenter) |
| **Wallpaper** | [swww](https://github.com/LGFae/swww) + [pywal](https://github.com/dylanaraps/pywal) |
| **Fetch** | [Fastfetch](https://github.com/fastfetch-cli/fastfetch) |
| **Music Module** | [waybar-module-music](https://github.com/Someon1e/waybar-module-music) |

### ~ Dependencies

**Core:**

```
hyprland hyprpaper hypridle hyprlock hyprshot
waybar kitty rofi swaync
```

**Wallpaper & Theming:**

```
swww python-pywal pywalfox wofi
```

**Utilities:**

```
fastfetch playerctl brightnessctl blueman
networkmanager dolphin grim slurp
swayosd cava wpctl (wireplumber)
```

**Waybar extras:**

```
waybar-module-music
```

**AUR / Optional:**

```
hyprshot swayosd-git waybar-module-music
```

**One-liner (yay):**

```bash
yay -S --needed hyprland hyprpaper hypridle hyprlock hyprshot \
  waybar kitty rofi swaync swww python-pywal pywalfox wofi \
  fastfetch playerctl brightnessctl blueman dolphin grim slurp \
  swayosd-git cava wireplumber waybar-module-music
```

---

### ~ Installation

**1. Clone the repo:**

```bash
git clone https://github.com/<your-username>/dotdot.git ~/dotdot
```

**2. Back up your existing configs (recommended):**

```bash
mkdir -p ~/.config/backup
for dir in hypr fastfetch kitty rofi swaync wal waybar waybar-module-music; do
  [ -d ~/.config/$dir ] && cp -r ~/.config/$dir ~/.config/backup/
done
```

**3. Symlink everything into `~/.config/`:**

```bash
cd ~/dotdot
for dir in hypr fastfetch kitty rofi swaync wal waybar waybar-module-music; do
  ln -sf "$(pwd)/$dir" ~/.config/$dir
done
```

> [!IMPORTANT]
> The `hypr/` folder contains the full Hyprland config along with sub-configs in `hypr/configs/` (keybinds, input, animations, window rules, look-and-feel) and utility scripts in `hypr/scripts/` (volume, brightness, screenshots, waybar controls, wallpaper picker, etc). All of these are linked together — make sure the entire `hypr/` directory is symlinked, not just `hyprland.conf`.

**4. Make scripts executable:**

```bash
chmod +x ~/dotdot/hypr/scripts/*.sh
chmod +x ~/dotdot/hypr/wallpaper.sh
chmod +x ~/dotdot/rofi/launchers/*/launcher.sh
chmod +x ~/dotdot/rofi/powermenu/*/powermenu.sh
chmod +x ~/dotdot/rofi/applets/bin/*.sh
chmod +x ~/dotdot/waybar/scripts/*.sh
chmod +x ~/dotdot/swaync/refresh.sh
```

**5. Set up wallpapers directory:**

```bash
mkdir -p ~/wallpapers/walls
# drop your wallpapers in ~/wallpapers/walls/
```

**6. Log out and back in to Hyprland**, or reload:

```bash
hyprctl reload
```

---

### ~ Keybinds

| Keys | Action |
|---|---|
| `SUPER + T` | Open terminal (kitty) |
| `SUPER + R` | App launcher (rofi) |
| `SUPER + Q` | Power menu |
| `SUPER + E` | File manager (dolphin) |
| `SUPER + C` | Close active window |
| `SUPER + V` | Toggle floating |
| `SUPER + P` | Screenshot (active output) |
| `SUPER + J` | Toggle split (dwindle) |
| `SUPER + S` | Scratchpad |
| `SUPER + 1-0` | Switch workspace |
| `SUPER + SHIFT + 1-0` | Move window to workspace |

---

<p align="center">
  <sub>built on arch btw</sub>
</p>
