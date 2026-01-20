---
label: Focusd
icon: tracked-by-closed-completed
description: "Privacy-first digital wellbeing and screen time tracker for Windows. No cloud, no telemetry."
order: 79
tags: [Go, Privacy, Windows, Productivity]
---

# :icon-tracked-by-closed-completed: Focusd

<center>
  <pre>
   __                           _ 
  / _|                         | |
 | |_ ___   ___ _   _ ___  ____| |
 |  _/ _ \ / __| | | / __|/ _  | |
 | || (_) | (__| |_| \__ \ (_| |_|
 |_| \___/ \___|\__,_|___/\____(_)
  </pre>
</center>

**Privacy-First Digital Wellbeing for Windows**

**Track your screen time. Own your data. No cloud required.**

![License](https://img.shields.io/github/license/0xarchit/focusd?style=flat-square) ![Release](https://img.shields.io/github/v/release/0xarchit/focusd?style=flat-square&color=22d3ee) ![Build Status](https://img.shields.io/github/actions/workflow/status/0xarchit/focusd/release.yml?style=flat-square&label=Build%20Status) [![Website](https://img.shields.io/website?url=https%3A%2F%2Ffocusd.0xarchit.is-a.dev&style=flat-square)](https://focusd.0xarchit.is-a.dev/){target="_blank"}  
![Stars](https://img.shields.io/github/stars/0xarchit/focusd?style=flat-square&color=yellow) ![Downloads](https://img.shields.io/github/downloads/0xarchit/focusd/total?style=flat-square&color=orange) ![Repo Size](https://img.shields.io/github/repo-size/0xarchit/focusd?style=flat-square&color=blue)

**:icon-mark-github: GitHub:** [https://github.com/0xarchit/Focusd](https://github.com/0xarchit/Focusd){target="_blank"}  
**:icon-globe: Live Project:** [https://focusd.0xarchit.is-a.dev](https://focusd.0xarchit.is-a.dev){target="_blank"}

## :icon-rocket: Why Focusd? {#why-focusd}

Every productivity tracker on the market uploads your data to their servers. **Focusd doesn't.** Your usage data stays on your machine, stored in a local SQLite database that you fully control.

| App | Installer / Disk Size | RAM Usage (Idle) | Tech Stack |
|-----|----------------------|------------------|------------|
| StayFree (Windows) | ~164 MB | 150MB - 400MB | likely Electron / UWP |
| Toggl Track | ~100 MB | 200MB - 500MB | Electron (Chromium bundled) |
| RescueTime (Classic) | ~25 MB | 20 - 50 MB | Native C++ / Qt |
| **Focusd** | **<11 MB** | **~4 - 10 MB** | **Go (Native Syscalls)** |

## :icon-download: Quick Start {#quick-start}

**PowerShell** (Recommended):
```powershell
iwr "https://github.com/0xarchit/focusd/releases/latest/download/focusd.exe" -OutFile focusd.exe; ./focusd.exe init
```

**Command Prompt**:
```cmd
curl -L -o focusd.exe "https://github.com/0xarchit/focusd/releases/latest/download/focusd.exe" && focusd.exe init
```

> [!NOTE]
> :icon-info: After running `init`, the `focusd` command is available globally from any terminal.

## :icon-star: Features {#features}

### :icon-graph: Usage Dashboard {#usage-dashboard}
View daily and historical screen time with a beautiful terminal UI.
```bash
focusd stats
```

### :icon-stopwatch: Focus Sessions {#focus-sessions}
Built-in Pomodoro timer with completion notifications.
```bash
focusd focus 25
```

### :icon-globe: Browser Tracking {#browser-tracking}
Tracks time spent per browser tab (by page title, not URL for privacy).
- :icon-eye: View in `focusd stats` → Browser Usage
- :icon-plus: Add custom browsers: `focusd browser add <exe_name>`

### :icon-beaker: Smart App Grouping (Experimental) {#smart-app-grouping}
Automatically groups related browser tabs (e.g., all YouTube videos under "YouTube").
- :icon-globe: 80+ supported sites (YouTube, GitHub, Reddit, Discord, LeetCode, etc.)
- :icon-file-directory: Shows parent category with sub-entries
- *Note: This feature is under active development. Some titles may not group correctly.*

### :icon-hourglass: App Limits {#app-limits}
Set daily time limits for distracting applications.
```bash
focusd limit
```

### :icon-bell-slash: Background Daemon {#background-daemon}
Silent background process with minimal resource usage (~5MB RAM, ~0% CPU).

## :icon-tools: Commands {#commands}

| Command | Description |
|---------|-------------|
| `focusd` | Interactive menu |
| `focusd stats` | Open usage dashboard |
| `focusd focus <mins>` | Start focus timer |
| `focusd limit` | Configure app limits |
| `focusd browser` | Add/remove custom browsers |
| `focusd start/stop` | Control background service |
| `focusd update` | Check for updates |
| `focusd uninstall` | Remove all data |

## :icon-lock: Privacy {#privacy}

- :icon-shield-check: **No telemetry.** Zero network requests except for update checks.
- :icon-server: **No cloud.** All data stored locally in `%APPDATA%\focusd\focusd.db`.
- :icon-database: **Open database.** Standard SQLite—query it yourself with any SQL tool.
- :icon-code: **Open source.** Audit the code anytime.

## :icon-package: Building from Source {#building-from-source}

```powershell
git clone https://github.com/0xarchit/Focusd.git
cd Focusd
go build -ldflags="-s -w" -trimpath -o focusd.exe ./cmd/focusd
```

**Requirements:** Go 1.21+