<p align="center"><img src="mascot.png" width="140" alt="A pixel-art gecko face"></p>

<h1 align="center">Nyx</h1>
<p align="center"><i>a Matrix chat app for our group</i></p>

---

Nyx (formerly Sidechat) is an app for Windows and Linux for chatting, hanging out in voice, and streaming games to each other. It uses Matrix, so it works alongside Element: same rooms, same people.

This repo only has the installers and updates.

## What it does

- Text chat, DMs, replies, reactions, files. All the normal stuff, end-to-end encrypted.
- Voice chat in any room. You can see who's in voice before you join.
- Screen and window sharing with sound. Nobody gets your stream until they click watch.
- A volume mixer, so you can turn one person (or one stream) up or down.
- A layout you set up yourself: split the window into panes, tab them, resize them, and they stay where you put them. Save a few layouts and switch between them.
- Themes, and Ctrl+K to jump to anything.

## What you need

- A Matrix account. A free one from [matrix.org](https://matrix.org) works; if you already use Element, use that account.
- **Windows:** Windows 10 or 11, 64-bit. Stream sound needs Windows 10 version 2004 (May 2020) or newer.
- **Linux (beta):** a 64-bit (x86-64) distro from 2022 or newer. See [which ones](#which-linux-versions).

## Install on Windows

1. Download **`Sidechat-win-Setup.exe`** from the [latest release](../../releases/latest). (The installer still has the old name; it installs Nyx.)
2. Run it. Windows may warn you the first time ("Windows protected your PC"). Click **More info → Run anyway**.
3. Nyx opens. Sign in with your Matrix account: it opens your browser to log in, then comes back.

After that it updates itself: when there's a new version, the status line says so, and it installs the next time you restart Nyx.

To check the download, compare this in PowerShell with the installer's SHA-256 listed on the release:

```
Get-FileHash .\Sidechat-win-Setup.exe
```

To uninstall: Settings → Apps → Installed apps → Nyx → Uninstall.

## Install on Linux (beta)

1. Download **`Sidechat.AppImage`** from the [latest release](../../releases/latest).
2. Put it somewhere it can stay, for example `~/Applications/`. Updates replace this file, so don't run it from a folder you clean out.
3. Make it runnable: right-click → Properties → "Allow executing as program" (or "Is executable"), or in a terminal:
   ```
   chmod +x Sidechat.AppImage
   ```
4. Double-click it (or run `./Sidechat.AppImage`) and sign in. It updates itself like the Windows version.

Nothing else to install: the AppImage brings what it needs (no FUSE or libfuse2 package required). To get a menu entry, a tool like [Gear Lever](https://flathub.org/apps/it.mijorus.gearlever) or AppImageLauncher can add one.

To check the download: `sha256sum Sidechat.AppImage` should match the AppImage's SHA-256 on the release.

To uninstall: delete the AppImage, and `~/.local/share/Sidechat-data` if you want your local data gone too (your account and messages stay on your Matrix server).

### Which Linux versions

Nyx needs glibc 2.35 or newer, which means:

| Works | Version |
|---|---|
| Ubuntu (and Kubuntu, Xubuntu…) | 22.04 or newer |
| Linux Mint | 21 or newer |
| Pop!_OS | 22.04 or newer |
| Zorin OS | 17 or newer |
| elementary OS | 7 or newer |
| Debian | 12 (Bookworm) or newer |
| Fedora | 36 or newer |
| Arch, Manjaro, EndeavourOS | current |
| openSUSE | Tumbleweed |
| Steam Deck | desktop mode |

Not yet: Ubuntu 20.04, Debian 11, openSUSE Leap, RHEL/Rocky/Alma 8 or 9, and ARM computers (Raspberry Pi, ARM laptops).

### What works on Linux

- **Chat, voice, watching streams:** everything, as on Windows.
- **Sharing your screen:** on Wayland, Nyx asks your desktop for the screen or window (your desktop's own picker opens). GNOME and KDE have this built in; on Sway or Hyprland install `xdg-desktop-portal-wlr` or `xdg-desktop-portal-hyprland`. On X11, Nyx lists your screens and windows itself.
- **Stream sound:** "everything I hear except Nyx" works everywhere; "only that app's sound" on X11. Needs PipeWire (with `pipewire-pulse`) or PulseAudio, which every common desktop has.
- **Push-to-talk:** on X11 it works while another app is focused. On Wayland only while Nyx is in front (Wayland doesn't let apps watch keys in other windows); voice activity works everywhere.
- **Your sign-in** is kept in your desktop's keyring (GNOME Keyring, KWallet). Without one, Nyx keeps it in a private file and tells you so once.

It's a beta: if something doesn't work, please tell us (below), with your distro, desktop (GNOME, KDE…) and whether it's Wayland or X11.

## Problems

Click **[feedback]** in Nyx's status line (it works from the sign-in screen too): describe what happened, add a screenshot with Ctrl+V, and tick "include my log". Or tell whoever sent you here, and attach `sidechat.log` and `debug.log` from Nyx's data folder: `%LOCALAPPDATA%\Sidechat-data` on Windows, `~/.local/share/Sidechat-data` on Linux.
