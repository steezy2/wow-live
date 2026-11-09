# WoW Live

A Windows app for World of Warcraft Mythic+ keys. It reads the game's combat log on your PC as the game writes it, with no upload, and shows:

- an overlay over the game: the clock against the timer, enemy forces, deaths, DPS, HPS and interrupts;
- a ready check when the party zones in: who's missing a flask, food or a party buff;
- a review after each key: each player against their spec's top runs on Warcraft Logs, with a damage and healing graph.

This repo holds only the installers. The source code is public at [steezy2/wow-live-app](https://github.com/steezy2/wow-live-app) (MIT), and its releases are built there on GitHub Actions with a build attestation: `gh attestation verify WoW.Live.Setup.exe -R steezy2/wow-live-app` checks an installer downloaded from there.

## Install

1. Download `WoW.Live.Setup.exe` from the [latest release](../../releases/latest).
2. Run it. It installs for your user only and needs no admin. It's unsigned, so Windows SmartScreen asks once: **More info**, then **Run anyway**.
3. In the game, turn on **Advanced Combat Logging** (Options > System > Network) and type `/combatlog` before the key.
4. Optional, for the review and a dungeon's first estimate: make a client at [warcraftlogs.com/api/clients](https://www.warcraftlogs.com/api/clients) (any name, redirect URL `http://localhost`) and paste its ID and secret in WoW Live's **Settings** tab.

Play in Windowed or Windowed (Fullscreen) mode so the overlay shows over the game. Ctrl+Alt+O moves and resizes it.

**Check the download (optional):** in PowerShell, `Get-FileHash .\WoW.Live.Setup.exe` should match the release's `.sha256` file.

**Uninstall:** Windows Settings > Apps > Installed apps > WoW Live. Your settings and saved keys stay in `%LOCALAPPDATA%\WoW Live`; delete that folder to remove them too.
