# AirzoneBar

Menu-bar app for macOS that controls an **Airzone** HVAC zoning system over its
**local API** — no Airzone Cloud subscription required.

This repository hosts the **downloadable builds only**. The source lives in a
separate private repository.

## Download & install

1. Go to the [**latest** release](../../releases/latest) and download `AirzoneBar.dmg`
   (universal — Apple Silicon + Intel, macOS 13 Ventura or newer).
2. Open the DMG and drag **AirzoneBar** to your Applications folder.
3. First launch: the app isn't notarized, so macOS blocks it once. Open it, then go to
   **System Settings → Privacy & Security → "Open Anyway"**. (Alternatively, in Terminal:
   `xattr -d com.apple.quarantine /Applications/AirzoneBar.app`.)
4. Accept the **local network** permission prompt so the app can reach the Airzone
   webserver on your LAN.

The app updates itself: it checks this repository's `latest` release periodically and
reinstalls when a newer build is available (toggle in Settings).

## What it does

- Per-zone and whole-home temperature, power, and system mode (cool / heat / fan / dry)
- Sleep timers, louver control, configurable presets, and local schedules
- Room + outdoor temperature, humidity, and a 24-hour trend per zone
- Electricity-price reference (Spain PVPC) and an estimated running-cost report
- Menu-bar popover **and** an optional resizable desktop widget
- Native notifications (setpoint reached, system error, daily-cost threshold)
- Optional built-in web UI for phone control on your own network (e.g. via a VPN
  such as Tailscale) while the Mac is awake
- Shortcuts / Siri support via an `airzonebar://` URL scheme

## Requirements

- macOS 13 or newer
- An Airzone system with a **local-API-capable webserver** reachable on your network
- The app and the webserver on the **same network** (LAN, or a private VPN for remote use)

## Notes

- Not affiliated with or endorsed by Airzone.
- Settings and history are stored locally on your Mac; the app talks only to your
  own webserver (and public price/weather APIs for reference data).
