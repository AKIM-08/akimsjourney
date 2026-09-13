---
layout: post
title: "Dotfiles Arch Linux"
date: 2026-09-13 21:20:00 +0000
categories: [Projects]
tags: [Arch Linux, Linux, Dotfiles, CLI]
---

# 🚀 My Customized Arch Linux Setup | Hyprland, Waybar & Dynamic Pywal Setup

A showcase of my personal Arch Linux desktop configuration (rice) built on Hyprland (Wayland), tailored for laptop setups with an AZERTY keyboard layout. 

In this video, I demonstrate workspace management, floating terminal windows with Cava audio visualization, a radial power menu, notification center integration, dynamic GTK/Waybar theming, and wallpaper switching on the fly.

---

### 🎥 Watch the Video Showcase

{% include embed/youtube.html id='FTkhdweLU7s' %}

---

### 🔗 Repositories & Credits

* 📁 **My Dotfiles Repository:** [AKIM-08/akim-dotfiles](https://github.com/AKIM-08/akim-dotfiles)
* 💡 **Inspiration & Base Setup:** Special thanks to **[@partyh4t](https://github.com/partyh4t)** for sharing their configuration! Check out their original dotfiles repository here: [partyh4t/arch-dotfiles](https://github.com/partyh4t/arch-dotfiles).

---

### ✨ Key Features Added in `akim-dotfiles`

1. **🎨 Dynamic Color Palette (`pywal16`):**
   * UI colors are extracted automatically from the active wallpaper (`~/Pictures/wallpapers/current.jpg`).
   * Theme generation dynamically updates Hyprland window borders, Kitty terminal colors, Rofi launcher, Hyprlock, Waybar, SwayNC, wlogout, Cava, and GTK 3/4 themes on the fly.
   * Includes a Python fallback (`pywal-fallback.py` with Pillow) if `pywal16` fails.

2. **🔋 Automated Low-Battery Hibernation Safeguard:**
   * **Automatic Hibernation at 1%:** The background script `battery-hibernate-watch.sh` continuously monitors system power. If the battery level drops to **1% while unplugged (discharging)**, the system automatically triggers a full hibernation.
   * **Session Preservation:** Saves active applications, terminal sessions, and workspace state directly to disk so you can resume seamlessly once reconnected to power.
   * **Requirement:** Requires an active **swap partition** or **swap file** (`swapon --show`). If no active swap is detected, hibernation safely aborts and displays a warning notification.

3. **📊 Dynamic Waybar Theme Switcher:**
   * Instant switching between 4 custom Waybar themes (`default`, `line`, `zen`, `experimental`) using `Super + Shift + T` or a Rofi menu.
   * Real-time clock update with second precision (`interval: 1`).

4. **🖥️ Custom SDDM Login Screen (`akim` theme):**
   * Custom split-screen SDDM theme featuring a left navigation panel ("Welcome", clock, login) with full wallpaper visibility on the right.
   * Automatic wallpaper and avatar sync with your user session (`~/.face`).

5. **⚡ Automated One-Command Installer (`install.sh`):**
   * Complete setup script for Arch Linux that installs essential packages, AUR helpers (`yay`), GTK/icon themes (Catppuccin Mocha, Nordzy, Papirus), setup configs, Oh My Zsh (`fishy` theme), and autogenerates dynamic themes.

6. **🌙 Custom Power & Idle Management:**
   * **wlogout / snmenu:** Radial power menu (`Super + Escape`) supporting Lock, Suspend, Hibernate, Reboot, and Shutdown with automated swap partition checks.
   * **hypridle + hyprlock:** Auto-dimming (10 min), custom lockscreen with user avatar (15 min), and auto-suspend (20 min).

---

### 🛠️ Tech Stack & Components

| Component | Tool / Package |
| :--- | :--- |
| **OS** | Arch Linux |
| **Display Manager** | SDDM (Custom `akim` split-screen theme) |
| **Compositor** | Hyprland (Wayland) |
| **Terminal** | Kitty |
| **Status Bar** | Waybar (4 dynamic styles) |
| **Application Launcher** | Rofi (+ Wofi theme selector) |
| **Notification Center**| SwayNC |
| **Power Menu** | wlogout / snmenu |
| **Wallpaper Manager** | hyprpaper + Waypaper (GUI) |
| **Lock Screen** | hyprlock + hypridle |
| **Dynamic Colors** | pywal16 |
| **Shell** | Zsh + Oh My Zsh (`fishy` theme) |
| **CLI Tools** | `cava`, `btop`, `tty-clock`, `fastfetch` |

---

### ⌨️ Main Keybindings (AZERTY Layout)

* `Super + Enter` : Open Terminal (Kitty)
* `Super + Q` : Toggle App Launcher (Rofi)
* `Super + A` : Close Active Window
* `Super + F` : Open File Manager (Nautilus)
* `Super + B` : Web Browser (Firefox / Brave)
* `Super + N` : SwayNC Notification Center
* `Super + Escape` : Open Radial Power Menu (wlogout)
* `Super + Shift + T` : Waybar Theme Selector
* `Super + Alt + → / ←` : Next / Previous Wallpaper + Regenerate Pywal Theme