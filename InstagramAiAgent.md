---
label: Instagram AI Agent
icon: hubot
description: "Complete AI-powered automation system that generates programming memes and posts them to Instagram automatically using n8n workflows and Carbon API."
order: 93
tags: [n8n, AI, Instagram, FastAPI, Automation, Memes]
---

# :icon-hubot: Automated Meme Generation System

![n8n](https://img.shields.io/badge/n8n-EA4B71?style=flat-square&logo=n8n&logoColor=white) ![AI](https://img.shields.io/badge/AI-Mistral-blue?style=flat-square) ![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=flat-square&logo=instagram&logoColor=white) ![License](https://img.shields.io/github/license/0xarchit/n8n-templates?style=flat-square)    
![Stars](https://img.shields.io/github/stars/0xarchit/n8n-templates?style=flat-square) ![Repo Size](https://img.shields.io/github/repo-size/0xarchit/n8n-templates?style=flat-square) ![Forks](https://img.shields.io/github/forks/0xarchit/n8n-templates?style=flat-square)

:icon-mark-github: **Github**: [0xarchit/carbon-now-sh-api](https://github.com/0xarchit/carbon-now-sh-api){target="_blank"}  
:icon-globe: **Github**: [0xarchit/n8n-templates](https://github.com/0xarchit/n8n-templates/tree/main/Instagram%20auto%20meme%20post){target="_blank"}

> [!TIP]
> A complete AI-powered automation system that generates programming memes and posts them to Instagram automatically using n8n workflows and a custom Carbon.now.sh API.

## :icon-workflow: Architecture

```mermaid
graph LR
    A[AI Agent<br/>n8n] --> B[Carbon API<br/>FastAPI]
    B --> C[Instagram<br/>Auto-post]
```

---


## :icon-tools: Components

### :icon-hubot: 1. AI Agent (n8n Workflow)
- **Purpose**: Automated meme generation and Instagram posting
- **Stack**: n8n + Mistral LLM + Memory + Scheduling
- **Features**:
  - Scheduled meme generation (customizable intervals)
  - Sarcastic programming humor using Mistral AI
  - Persistent memory to avoid repetition
  - Automated Instagram posting via FB Graph API
  - Cloudinary integration for image hosting

### :icon-image: 2. Carbon API (FastAPI Service)
- **Purpose**: Convert code snippets to beautiful images
- **Stack**: FastAPI + Playwright + Carbon.now.sh
- **Features**:\
  - Pre-configured Seti theme with Hack font
  - No watermarks or distractions
  - Docker containerized
  - CORS enabled

---

## :icon-rocket: Quick Start

### :icon-container: Carbon API
```bash
cd carbon-api
docker build -t carbon-api .
docker run -p 8000:8000 carbon-api
```

### :icon-workflow: AI Agent Setup
1. Import `ai-agent/instagram_autopost.json` into your n8n instance
2. Configure credentials:
   - Mistral Cloud API
   - Facebook Graph API (Instagram)
   - Cloudinary (optional)
3. Update URLs to point to your Carbon API deployment
4. Set schedule trigger as needed

---

## :icon-globe: Live Demo

:icon-rocket: **Carbon API**: [https://zeroxcarbon.onrender.com/docs](https://zeroxcarbon.onrender.com/docs){target="_blank"}

:icon-rocket: **Instagram**: [https://www.instagram.com/echosarcasm](https://www.instagram.com/echosarcasm){target="_blank"}

---

## :icon-checklist: Prerequisites

+++ :icon-image: For Carbon API
- Docker or Python 3.11+
- Playwright (auto-installed)
+++ :icon-hubot: For AI Agent
- n8n instance (self-hosted or cloud)
- Mistral Cloud account
- Facebook Developer account (Instagram Basic Display)
- Cloudinary account (optional)
+++

---

## :icon-gear: Configuration

### :icon-workflow: AI Agent Workflow
1. **Schedule Trigger**: Set your posting frequency
2. **Mistral LLM**: Configure API credentials
3. **Carbon API URL**: Point to your deployed Carbon service
4. **Instagram**: Configure FB Graph API credentials
5. **Memory**: Maintains context to avoid duplicate memes

### :icon-image: Carbon API
- **Theme**: Seti (dark)
- **Font**: Hack 12px
- **Output**: JPG at 90% quality
- **No line numbers or window controls**

---

## :icon-workflow: Workflow Process

```mermaid
graph TD
    A[Schedule Trigger] --> B[AI Agent]
    B --> C[Memory Check]
    C --> D[Caption Generator]
    D --> E[Carbon API]
    E --> F[Cloudinary]
    F --> G[Instagram Auto-post]
```

1. **Schedule Trigger** → Starts the automation
2. **AI Agent** → Generates witty programming meme
3. **Memory Check** → Ensures uniqueness
4. **Caption Generator** → Creates Instagram-ready text
5. **Carbon API** → Converts code to beautiful image
6. **Cloudinary** → Uploads image (optional)
7. **Instagram** → Auto-posts to your account

---

## :icon-sliders: Customization

+++ :icon-paintbrush: Content Customization
- **Meme Style**: Edit prompts in AI Agent nodes
- **Visual Theme**: Modify Carbon API parameters
+++ :icon-clock: Scheduling & Platforms
- **Posting Schedule**: Adjust Schedule Trigger intervals
- **Platforms**: Extend to Twitter, LinkedIn, etc.
+++

---