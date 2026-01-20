---
label: AlgorithmAce
icon: rocket
description: "AI-powered LeetCode companion Chrome extension with AI explanations, friend comparisons, notifications, and GitHub star gating."
order: 86
tags: [Chrome Extension, React, TypeScript, Tailwind, Chart.js, GitHub OAuth, Cloudflare Workers]
---

# AlgorithmAce: AI-Powered LeetCode Companion :icon-rocket:

![Chrome Extension](https://img.shields.io/badge/Chrome_Extension-4285F4?style=flat-square&logo=google-chrome&logoColor=white) ![React](https://img.shields.io/badge/React-20232a?style=flat-square&logo=react&logoColor=61DAFB) ![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=flat-square&logo=typescript&logoColor=white) ![License](https://img.shields.io/github/license/0xarchit/AlgorithmAce?style=flat-square)  
![Stars](https://img.shields.io/github/stars/0xarchit/AlgorithmAce?style=flat-square) ![Repo Size](https://img.shields.io/github/repo-size/0xarchit/AlgorithmAce?style=flat-square) ![Forks](https://img.shields.io/github/forks/0xarchit/AlgorithmAce?style=flat-square) [![Website](https://img.shields.io/website?url=https://algorithmace.0xarchit.is-a.dev&style=flat-square)](https://algorithmace.0xarchit.is-a.dev){target="_blank"}

**Enhance your LeetCode experience with AI assistance, friend comparisons, and daily problem notifications**

:icon-mark-github: **GitHub**: [0xarchit/AlgorithmAce](https://github.com/0xarchit/AlgorithmAce){target="_blank"}  
:icon-globe: **Live Demo**: [https://algorithmace.0xarchit.is-a.dev](https://algorithmace.0xarchit.is-a.dev){target="_blank"}

---


## :icon-star: Overview {#overview}

**AlgorithmAce** is a production-ready Chrome Extension (Manifest V3) that supercharges your LeetCode journey with:

- :icon-hubot: **AI-powered explanations** for problem-solving logic
- :icon-people: **Friend comparisons** to track progress with peers
- :icon-calendar: **Daily notifications** with Problem of the Day
- :icon-bell: **Smart reminders** and motivational messages
- :icon-star: **GitHub star gating** for premium features

Built with React, TypeScript, and Tailwind CSS, AlgorithmAce provides a sleek, modern interface. Core features (AI chat, problem search, stats) run locally in the extension; GitHub OAuth and star verification are handled securely by a minimal Cloudflare Worker backend.

> [!TIP]
> :icon-zap: For first‑time users, start with Releases (CRX/ZIP) to try AlgorithmAce quickly. Developers can use the source install below.

## :icon-star: Features {#features}

### 1. :icon-plug: LeetCode Integration

- :icon-calendar: **Problem of the Day (POTD)**: Automatically fetch and display the daily coding challenge
- :icon-graph: **User Stats Dashboard**: View your solving stats, ranking, streak, and active days
- :icon-search: **Problem Search**: Search by keyword, difficulty, or topic tags
- :icon-database: **Smart Caching**: Efficient data caching using `chrome.storage.local`

### 2. :icon-people: Friend Comparison

- :icon-people: **Multi-User Tracking**: Add multiple LeetCode usernames to compare
- :icon-graph: **Visual Analytics**: Beautiful radar charts showing comparative stats
- :icon-pulse: **Real-time Stats**: Easy/Medium/Hard problems solved, streaks, and more
- :icon-sync: **Persistent Storage**: Friends list synced across devices via `chrome.storage.sync`

### 3. :icon-hubot: AI Assistant Panel

- :icon-cpu: **Multi-Provider Support**: Choose from Gemini and OpenAI‑compatible providers (OpenAI, Groq, etc.), or set a custom base URL
- :icon-light-bulb: **Logic-Focused**: Get explanations without code (promotes learning)
- :icon-pencil: **Custom Prompts**: Tailor the AI behavior to your learning style
- :icon-comment-discussion: **Chat History**: Maintains conversation context per problem
- :icon-verified: **API Key Validation**: Built-in verification system

### 4. :icon-star: GitHub Star Gating

- :icon-lock: **Premium Feature Lock**: AI and friend comparison require GitHub star
- :icon-sync: **Automatic Verification**: Hourly checks using GitHub REST API
- :icon-smiley: **Smooth UX**: Non-intrusive modal with easy verification flow
- :icon-star: **Star Count Display**: Shows repo popularity

### 5. :icon-bell: Notifications & Engagement

- :icon-bell: **Daily POTD Alerts**: Get notified at 9 AM every day
- :icon-quote: **Motivational Quotes**: Random coding inspiration with each notification
- :icon-link-external: **Click-to-Solve**: Notifications link directly to LeetCode problems
- :icon-clock: **Smart Reminders**: Periodic GitHub star reminders (max 1/day)

### 6. :icon-gear: Comprehensive Settings

- :icon-person: **Profile Configuration**: Set your LeetCode username
- :icon-gear: **AI Configuration**: Manage provider, API keys, models, and prompts
- :icon-people: **Friend Management**: Add/remove friends easily
- :icon-mark-github: **GitHub Verification**: Link and verify your GitHub account

## :icon-eye: Preview {#preview}

![Screenshot 1](public/AlgorithmAce/image1.png)

![Screenshot 2](public/AlgorithmAce/image2.png)

![Screenshot 3](public/AlgorithmAce/image3.png)

![Screenshot 4](public/AlgorithmAce/image4.png)

![Screenshot 5](public/AlgorithmAce/image5.png)

![Screenshot 6](public/AlgorithmAce/image6.png)

## :icon-tools: Tech Stack {#tech-stack}

| Category | Technologies |
|----------|-------------|
| **Framework** | React 18 + TypeScript |
| **Build Tool** | Vite 5 |
| **Styling** | Tailwind CSS 3 |
| **Charts** | Chart.js + react-chartjs-2 |
| **HTTP Client** | Axios |
| **Icons** | Lucide React |
| **Browser API** | Chrome Extension Manifest V3 |
| **Storage** | chrome.storage (local & sync) |
| **Background** | Service Workers |

## :icon-package: Installation {#installation}

### Option A: Install from Releases (CRX / ZIP) {#option-a-install-from-releases-crx--zip}

The easiest way to try AlgorithmAce without building locally is via GitHub Releases:

1. Go to the latest release: https://github.com/0xarchit/AlgorithmAce/releases
2. Download one of the assets:
   - CRX: `AlgorithmAce.crx` (drag-and-drop install)
   - ZIP: `AlgorithmAce-dist.zip` (unzip and Load unpacked)

CRX install (Chrome/Edge):

1) Open `chrome://extensions/` (or `edge://extensions/` on Edge)
2) Enable “Developer mode” (top-right)
3) Drag the downloaded `AlgorithmAce.crx` onto the page to install

Notes:
- If Chrome blocks the CRX due to security policy, use the ZIP method below.
- Manually installed CRXs don’t auto-update. Check Releases for updates.

> [!NOTE]
> :icon-alert: Side‑loaded CRX installs may be blocked by enterprise policies. Use ZIP (Load unpacked) if CRX fails.

ZIP install (Load unpacked):

1) Unzip `AlgorithmAce-dist.zip`
2) Open `chrome://extensions/` and enable “Developer mode”
3) Click “Load unpacked” and select the unzipped `dist` folder

### Option B: Install from Source {#option-b-install-from-source}

Prerequisites

- Node.js 18+ and npm/yarn/pnpm
- Google Chrome browser
- A GitHub account (for premium features)

### Install from Source

1. **Clone the repository**
   ```powershell
   git clone https://github.com/0xarchit/AlgorithmAce.git
   cd AlgorithmAce
   ```

2. **Install dependencies**
   ```powershell
   npm install
   ```

3. **Build the extension**
   ```powershell
   npm run build
   ```

4. **Load in Chrome**
   - Open Chrome and go to `chrome://extensions/`
   - Enable "Developer mode" (toggle in top-right)
   - Click "Load unpacked"
   - Select the `dist` folder from the project

5. **Pin the extension**
   - Click the puzzle icon in Chrome toolbar
   - Find "AlgorithmAce" and pin it

## :icon-tools: Development {#development}

### Development Mode {#development-mode}

Run the extension in development mode with hot reload:

```powershell
npm run dev
```

Then load the extension from the `dist` folder as described above (Load unpacked).

### Project Structure {#project-structure}

```
AlgorithmAce/
├── public/
│   ├── manifest.json          # Chrome extension manifest
│   └── icons/                 # Extension icons (16, 48, 128)
├── src/
│   ├── background/
│   │   └── background.ts      # Service worker for alarms & notifications
│   ├── services/
│   │   ├── leetcode.service.ts   # LeetCode GraphQL API
│   │   ├── github.service.ts     # GitHub REST API
│   │   └── ai.service.ts         # Multi-provider AI service
│   └── popup/
│       ├── components/
│       │   ├── Dashboard.tsx
│       │   ├── FriendComparison.tsx
│       │   ├── AIAssistant.tsx
│       │   ├── Settings.tsx
│       │   └── GitHubStarModal.tsx
│       ├── App.tsx
│       ├── main.tsx
│       └── index.css
├── popup.html
├── vite.config.ts
├── tailwind.config.js
├── tsconfig.json
└── package.json
```

### Build for Production

```powershell
npm run build
```

The production-ready extension will be in the `dist` folder.

## :icon-gear: Configuration {#configuration}

### 1. Profile Setup {#profile-setup}

1. Click the extension icon
2. Go to **Settings** → **Profile**
3. Enter your LeetCode username
4. Click "Save Profile Settings"

### 2. AI Configuration {#ai-configuration}

1. Go to **Settings** → **AI Config**
2. Select your AI provider (Gemini, OpenAI‑compatible like OpenAI or Groq, or Other for a custom base URL)
3. Enter your API key
4. Click "Check" to verify the key
5. Customize the model and prompt (optional)
6. Click "Save AI Configuration"

#### Getting API Keys {#getting-api-keys}

- **Gemini**: [Google AI Studio](https://makersuite.google.com/app/apikey)
- **OpenAI**: [OpenAI Platform](https://platform.openai.com/api-keys)
- **Groq**: [Groq Console](https://console.groq.com/keys)

### 3. GitHub Verification {#github-verification}

1. Go to **Settings** → **GitHub**
2. Enter your GitHub username
3. Click "Star on GitHub" button
4. Star the [AlgorithmAce repository](https://github.com/0xarchit/AlgorithmAce)
5. Return to extension and click "Verify Star"

## :icon-device-mobile: Usage {#usage}

### Dashboard {#dashboard}

- View today's Problem of the Day
- Check your LeetCode stats and progress
- Quick access to solve POTD

### Friend Comparison {#friend-comparison}

- Add friends' LeetCode usernames
- View comparative stats in a radar chart
- Track who's solving more problems

### AI Assistant {#ai-assistant}

- Ask questions about problem logic
- Get reasoning without actual code
- Learn problem-solving patterns
- Maintain conversation context

### Settings {#settings}

- Configure all extension preferences
- Manage AI providers and keys
- Verify GitHub star status
- Add/remove friends

## :icon-lock: Privacy & Security {#privacy--security}

- :icon-check: **Local-first**: Chat history and configuration are stored locally in your browser
- :icon-check: **AI Keys**: Stored securely in `chrome.storage.sync` (encrypted at rest by Chrome)
- :icon-check: **Secure GitHub OAuth**: Sign-in and star verification run via our Cloudflare Worker backend (`git-auth.0xarchit.is-a.dev`). Your GitHub access token remains on the server; the extension only stores a short‑lived JWT. Tokens can be revoked server‑side.
- :icon-check: **Minimal Permissions**: Only the Chrome APIs necessary for core features
- :icon-check: **No Analytics by Default**: Completely opt‑in if added later
- :icon-check: **Open Source**: Full transparency of code and Worker implementation

## :icon-home: Contributing {#contributing}

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request
