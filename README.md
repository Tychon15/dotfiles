# dotfiles
Dotfiles for my arch based hyprland rice.

<a href="#-overview">Overview</a> &nbsp;&bull;&nbsp;
<a href="#-dependencies">Dependencies</a> &nbsp;&bull;&nbsp;
<a href="#-installation">Installation</a> &nbsp;&bull;&nbsp;
<a href="#-keybinds">Keybinds</a>


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
| **Audio Visualizer** | [Cava](https://github.com/karlstav/cava) |
| **System Monitor** | [Btop](https://github.com/aristocratos/btop) |
| **Shell** | [Zsh](https://www.zsh.org/) + [Oh My Zsh](https://ohmyz.sh/) + [Powerlevel10k](https://github.com/romkatv/powerlevel10k) |
| **GTK Theme** | GTK 3.0 |

### ~ Dependencies

**Core:**

```
hyprland hyprpaper hypridle hyprlock hyprshot
waybar kitty rofi swaync
zsh oh-my-zsh-git zsh-theme-powerlevel10k
```

**Wallpaper & Theming:**

```
swww python-pywal pywalfox wofi
```

**Utilities:**

```
fastfetch playerctl brightnessctl blueman
networkmanager dolphin grim slurp
swayosd cava btop wpctl (wireplumber)
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
  zsh oh-my-zsh-git zsh-theme-powerlevel10k \
  fastfetch playerctl brightnessctl blueman dolphin grim slurp \
  swayosd-git cava btop wireplumber waybar-module-music
```

---

### ~ Installation

**1. Clone the repo:**

```bash
git clone https://github.com/Tychon15/dotfiles.git ~/dotfiles
```

**2. Back up your existing configs (recommended):**

```bash
mkdir -p ~/.config/backup
for dir in hypr fastfetch kitty rofi swaync wal waybar waybar-module-music cava btop gtk-3.0; do
  [ -d ~/.config/$dir ] && cp -r ~/.config/$dir ~/.config/backup/
done
```

**3. Symlink everything into `~/.config/`:**

```bash
cd ~/dotfiles
for dir in hypr fastfetch kitty rofi swaync wal waybar waybar-module-music cava btop gtk-3.0; do
  ln -sf "$(pwd)/$dir" ~/.config/$dir
done

# Shell configs (symlink to home directory)
ln -sf "$(pwd)/.zshrc" ~/.zshrc
ln -sf "$(pwd)/.p10k.zsh" ~/.p10k.zsh
```

> [!IMPORTANT]
> The `hypr/` folder contains the full Hyprland config along with sub-configs in `hypr/configs/` (keybinds, input, animations, window rules, look-and-feel) and utility scripts in `hypr/scripts/` (volume, brightness, screenshots, waybar controls, wallpaper picker, etc). All of these are linked together — make sure the entire `hypr/` directory is symlinked, not just `hyprland.conf`.

**4. Make scripts executable:**

```bash
chmod +x ~/dotfiles/hypr/scripts/*.sh
chmod +x ~/dotfiles/hypr/wallpaper.sh
chmod +x ~/dotfiles/rofi/launchers/*/launcher.sh
chmod +x ~/dotfiles/rofi/powermenu/*/powermenu.sh
chmod +x ~/dotfiles/rofi/applets/bin/*.sh
chmod +x ~/dotfiles/waybar/scripts/*.sh
chmod +x ~/dotfiles/swaync/refresh.sh
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
