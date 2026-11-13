<p align="center"><img src="mascot.png" width="140" alt="A pixel-art gecko face"></p>

<h1 align="center">Nyx</h1>
<p align="center"><i>a Matrix chat app for our group</i></p>

---

Nyx (formerly Sidechat) is a Windows app for chatting, hanging out in voice, and streaming games to each other. It uses Matrix, so it works alongside Element: same rooms, same people.

This repo only has the installers and updates.

## What it does

- Text chat, DMs, replies, reactions, files. All the normal stuff, end-to-end encrypted.
- Voice chat in any room. You can see who's in voice before you join.
- Screen and window sharing with sound. Nobody gets your stream until they click watch.
- A volume mixer, so you can turn one person (or one stream) up or down.
- A layout you set up yourself: split the window into panes, tab them, resize them, and they stay where you put them. Save a few layouts and switch between them.
- Themes, and Ctrl+K to jump to anything.

## Install

1. Download **`Sidechat-win-Setup.exe`** from the [latest release](../../releases/latest). (The installer still has the old name; it installs Nyx.)
2. Run it. Windows may warn you the first time ("Windows protected your PC"). Click **More info → Run anyway**.
3. Sign in with your Matrix account ([matrix.org](https://matrix.org) works).

After that it updates itself.

If you want to check the download, compare this in PowerShell with the SHA-256 listed on the release:

```
Get-FileHash .\Sidechat-win-Setup.exe
```

## Problems

Click **[feedback]** in Nyx's status line (it works from the sign-in screen too): describe what happened, add a screenshot with Ctrl+V, and include your log. Or tell whoever sent you here, and attach `%LOCALAPPDATA%\Sidechat-data\sidechat.log` and `debug.log` from the same folder.
