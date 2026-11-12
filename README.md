<p align="center"><img src="mascot.png" width="140" alt="A yellow speech bubble giving you side-eye"></p>

<h1 align="center">Sidechat</h1>
<p align="center"><i>a small, fast Matrix chat app for friends who'd rather not be on Discord</i></p>

---

This repo holds **Sidechat's installers and updates**. The source lives elsewhere; nothing here but builds.

## Get it

1. Open the [latest release](../../releases/latest) and download **`Sidechat-win-Setup.exe`**.
2. Run it. It installs just for you (no admin, no wizard, no 14 checkboxes) and opens Sidechat.
3. Windows may say *"Windows protected your PC"* the first time, because these test builds aren't signed yet.
   Click **More info → Run anyway**. You'll only see that once: updates install themselves.

Sign in with your Matrix account (matrix.org works), and press **F1** for the guide.

## Check your download (optional, takes 10 seconds)

Each release lists the installer's SHA-256, and the person who sent you here will share it too. In PowerShell:

```
Get-FileHash .\Sidechat-win-Setup.exe
```

If the long hex string matches, the file is the real one. If it doesn't, don't run it, and tell them.

## Updates

Sidechat checks here every few hours. When a fresher build hatches, it downloads quietly, double-checks the
signature (it refuses anything that isn't signed by the release key), and offers a restart when it suits you.

## Removing it

Sign out first (Ctrl+K → *sign out*), then uninstall from **Settings → Apps → Installed apps → Sidechat**.

## Found a bug?

Tell whoever sent you here. Screenshots help; so does `%LOCALAPPDATA%\Sidechat\sidechat.log`.
