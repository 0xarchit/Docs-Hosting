---
label: 0xDABmusic
icon: play
description: "High-performance native music player built with Go and Wails, featuring 320kbps streaming, lyrics sync, and Spotify integration."
order: 80
tags: [Go, Wails, React, Music, Privacy]
---

# 🎵 0xDABmusic

**Download, Convert, Listen all at one place.**

![Go](https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white) ![React](https://img.shields.io/badge/React-20232a?style=flat-square&logo=react&logoColor=61DAFB) ![Wails](https://img.shields.io/badge/Wails-E32636?style=flat-square&logo=wails&logoColor=white) ![License](https://img.shields.io/github/license/0xarchit/0xDABmusic?style=flat-square)  
![Stars](https://img.shields.io/github/stars/0xarchit/0xDABmusic?style=flat-square) ![Repo Size](https://img.shields.io/github/repo-size/0xarchit/0xDABmusic?style=flat-square) ![Forks](https://img.shields.io/github/forks/0xarchit/0xDABmusic?style=flat-square) [![Website](https://img.shields.io/website?url=https://dab.0xarchit.is-a.dev/&style=flat-square)](https://dab.0xarchit.is-a.dev/){target="_blank"}

## 🚀 Why 0xDABmusic? {#why-0xdabmusic}

**0xDABmusic** isn't just another music player. It's a high-performance, native application built with **Go** and **Wails**, designed for those who demand quality and privacy.

- :icon-zap: **Native Performance**: Written in Go, ensuring lightning-fast startup and low resource usage.
- :icon-pulse: **Studio Quality**: Full support for FLAC and high-fidelity artifacts.
- :icon-shield-lock: **Privacy First**: Your library stays local. No ads, no tracking, no subscription walls.
- :icon-tools: **Power Tools**: Built-in lyrics synchronization, Spotify playlist import, and smart conversion.

## 📥 Installation {#installation}

Choose the version that fits your workflow.

### Windows
Download the **Windows Bundle (Zip)**. It contains:
- **Setup (.exe)**: Full installer (Recommended).
- **Portable (.exe)**: Standalone executable.

> [!WARNING]
> :icon-alert: If Microsoft Defender warns you, strict "More Info" -> "Run Anyway".

### macOS
Download the **macOS Bundle (Zip)**. It contains:
- **Installer (.dmg)**: Drag and drop to Applications.
- **Portable (.app)**: Run directly.

> [!NOTE]
> :icon-info: Since we don't have an Apple Developer ID yet, you may need to **Right Click > Open** the app for the first time if you see "App is damaged" or "Unidentified Developer".

### Linux
We support major distributions natively.

**Debian / Ubuntu:**
```bash
sudo dpkg -i 0xDABmusic_<version>_amd64.deb
```

**Arch Linux:**
```bash
sudo pacman -U 0xDABmusic-<version>-x86_64.pkg.tar.zst
```

## 🚀 Getting Started {#getting-started}

### 1️⃣ Create a DAB Account
0xDABmusic requires a DAB account to access cloud features.
- Register at **[dab.yeet.su](https://dab.yeet.su/)**
- Use these credentials to log in to the app.

### 2️⃣ Spotify Integration (Recommended)
To enable playlist imports and enhanced metadata:
1. Go to the [Spotify Developer Dashboard](https://developer.spotify.com/dashboard) and log in.
2. Click **"Create App"**.
3. Fill in the details:
   - **App Name:** `0xDABmusic`
   - **App Description:** `music`
   - **Redirect URI:** `http://127.0.0.1:8888/callback`
   - **Which API/SDKs are you planning to use?**: Select **"Web API"**.
4. Once created, go to **Settings** in your dashboard.
5. Copy the **Client ID** and **Client Secret**.
6. Open **0xDABmusic > Settings** and paste them into the Spotify configuration section.

## ✨ Features {#features}

### 🎵 Library Management {#library-management}
- :icon-file-directory: **Organize**: tracks, artists, and albums efficiently.
- :icon-list-unordered: **Playlists**: Create Public/Private playlists.
- :icon-arrow-switch: **Batch Actions**: Import and export your library seamlessly.

### 🔍 Smart Search {#smart-search}
- :icon-globe: **Global Search**: Search across your library and online simultaneously.
- :icon-filter: **Filters**: Filter by bitrate, format, or duration.
- :icon-zap: **Speed**: Instant results.

### 🎤 Synced Lyrics {#synced-lyrics}
- :icon-comment: **Real-time**: Lyrics display in sync with the music.
- :icon-download: **Auto-fetch**: Automatically fetches lyrics for supported tracks.
- :icon-broadcast: **Karaoke**: Karaoke-style highlighting.

### 📡 Spotify Integration {#spotify-integration}
- :icon-plug: **Import**: Import playlists directly from Spotify.
- :icon-download: **Convert**: Convert streaming tracks to local files.
- :icon-sync: **Sync**: Keep your collection in sync.

<br>

<p align="center">
  Built with ❤️ by <a href="https://github.com/0xarchit">0xArchit</a> using 
  <a href="https://wails.io">Wails</a> & <a href="https://react.dev">React</a>.
</p>
