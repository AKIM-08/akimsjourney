---
layout: post
title: "Dotfiles Arch Linux"
date: 2026-08-15 12:20:00 +0000
categories: [Projects]
tags: [Arch Linux, Linux, Dotfiles, CLI]
---

# My Customized Arch Linux Setup (Hyprland & Waybar)

Here is a showcase of my personal Arch Linux desktop setup built on Hyprland, tailored for a laptop with an AZERTY keyboard layout. 

In this setup, I focus on smooth workspace navigation, dynamic color schemes, notification management, and custom power options.

---

### Video Showcase

{% include embed/youtube.html id='FTkhdweLU7s' %}

---

### Repositories and Credits

* **My Dotfiles Repository:** [AKIM-08/akim-dotfiles](https://github.com/AKIM-08/akim-dotfiles)
* **Inspiration & Base Setup:** Thanks to [@partyh4t](https://github.com/partyh4t) for sharing their configuration. You can check out their original dotfiles at [partyh4t/arch-dotfiles](https://github.com/partyh4t/arch-dotfiles).

---

### Key Features

1. **Dynamic Color Palette (`pywal16`):**
   * Extract colors automatically from the active wallpaper (`~/Pictures/wallpapers/current.jpg`).
   * Dynamically update Hyprland window borders, Kitty terminal, Rofi launcher, Hyprlock, Waybar, SwayNC, wlogout, Cava, and GTK 3/4 themes.
   * Includes a Python fallback (`pywal-fallback.py` with Pillow) if `pywal16` fails.

2. **Automated Low-Battery Hibernation:**
   * **Automatic Hibernation at 1%:** The background script `battery-hibernate-watch.sh` monitors battery status. If the charge drops to 1% while unplugged, the system automatically hibernates.
   * **Session Preservation:** Saves active applications, terminal sessions, and workspace state to disk so you can resume once plugged back in.
   * **Requirement:** Requires an active swap partition or swap file (`swapon --show`). Without swap, the system cancels hibernation and sends a notification.

3. **Dynamic Waybar Theme Switcher:**
   * Switch between four custom Waybar themes (`default`, `line`, `zen`, `experimental`) using `Super + Shift + T` or a Rofi menu.
   * Real-time clock update with second-level precision (`interval: 1`).

4. **Custom SDDM Login Screen (`akim` theme):**
   * Split-screen layout featuring a left navigation panel ("Welcome", clock, login) with full wallpaper visibility on the right.
   * Syncs wallpaper and user avatar (`~/.face`) with the desktop session.

5. **Automated One-Command Installer (`install.sh`):**
   * Installs necessary packages, AUR helpers (`yay`), GTK/icon themes (Catppuccin Mocha, Nordzy, Papirus), setup configs, and Oh My Zsh (`fishy` theme).

6. **Power and Idle Management:**
   * **wlogout / snmenu:** Radial power menu (`Super + Escape`) supporting Lock, Suspend, Hibernate, Reboot, and Shutdown with automated swap partition checks.
   * **hypridle + hyprlock:** Auto-dimming (10 min), lock screen with avatar (15 min), and auto-suspend (20 min).

---

### Tech Stack and Components

| Component | Tool / Package |
| :--- | :--- |
| **OS** | Arch Linux |
| **Display Manager** | SDDM (Custom `akim` split-screen theme) |
| **Compositor** | Hyprland (Wayland) |
| **Terminal** | Kitty |
| **Status Bar** | Waybar (4 dynamic styles) |
| **Application Launcher** | Rofi (+ Wofi theme selector) |
| **Notification Center** | SwayNC |
| **Power Menu** | wlogout / snmenu |
| **Wallpaper Manager** | hyprpaper + Waypaper (GUI) |
| **Lock Screen** | hyprlock + hypridle |
| **Dynamic Colors** | pywal16 |
| **Shell** | Zsh + Oh My Zsh (`fishy` theme) |
| **CLI Tools** | `cava`, `btop`, `tty-clock`, `fastfetch` |

---

### Keybindings (AZERTY Layout)

* `Super + Enter` : Open Terminal (Kitty)
* `Super + Q` : Toggle App Launcher (Rofi)
* `Super + A` : Close Active Window
* `Super + F` : Open File Manager (Nautilus)
* `Super + B` : Web Browser (Firefox / Brave)
* `Super + N` : SwayNC Notification Center
* `Super + Escape` : Open Power Menu (wlogout)
* `Super + Shift + T` : Waybar Theme Selector
* `Super + Alt + → / ←` : Next / Previous Wallpaper + Regenerate Pywal Theme