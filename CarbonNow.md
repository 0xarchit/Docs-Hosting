---
label: Carbon Code Generator
icon: image
description: "FastAPI service that generates beautiful code images using Carbon.now.sh with customizable styling and JPG output."
order: 94
tags: [FastAPI, Python, Carbon, API, Docker]
---

# :icon-image: Carbon Code Image Generator

![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white) ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![License](https://img.shields.io/github/license/0xarchit/carbon-now-sh-api?style=flat-square)    
![Stars](https://img.shields.io/github/stars/0xarchit/carbon-now-sh-api?style=flat-square) ![Repo Size](https://img.shields.io/github/repo-size/0xarchit/carbon-now-sh-api?style=flat-square) ![Forks](https://img.shields.io/github/forks/0xarchit/carbon-now-sh-api?style=flat-square) [![Website](https://img.shields.io/website?url=https://zeroxcarbon.onrender.com/docs&style=flat-square)](https://zeroxcarbon.onrender.com/docs){target="_blank"}


:icon-mark-github: **Github**: [0xarchit/carbon-now-sh-api](https://github.com/0xarchit/carbon-now-sh-api){target="_blank"}  
:icon-globe: **Live Demo**: [https://zeroxcarbon.onrender.com/docs](https://zeroxcarbon.onrender.com/docs){target="_blank"}


> [!TIP]
> A FastAPI service that generates beautiful code images using Carbon.now.sh. Convert your code into shareable JPG images with customizable styling.

## :icon-rocket: Features

+++ :icon-check: Core Features
- :icon-image: Generate high-quality code images in JPG format
- :icon-paintbrush: Pre-configured with Seti theme and Hack font
- :icon-gear: Optimized for JPG output
- :icon-zap: Fast API with CORS support
- :icon-eye: Clean, minimal design without watermarks
+++

---

## :icon-download: Installation & Usage

### :icon-container: 1. Build the Docker image:
```bash
docker build -t carbon-api .
```

### :icon-play: 2. Run the container:
```bash
docker run -p 8000:8000 carbon-api
```

### :icon-code: 3. Generate code image:
```
GET /generate-image?code=YOUR_CODE_HERE
```

#### :icon-terminal: Example
```bash
curl "http://localhost:8000/generate-image?code=console.log('Hello World');"
```

Returns a JPG image of your formatted code.

---

## :icon-server: API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/generate-image` | GET | Generate code image from query parameter |

---

## :icon-gear: Configuration

The service uses these Carbon.now.sh settings:

+++ :icon-paintbrush: Styling Options
- **Theme**: Seti
- **Font**: Hack (12px)
- **Format**: JPG (90% quality)
+++ :icon-sliders: Size & Layout
- **Size**: 512x512 pixels
- **No line numbers, window controls, or watermarks**
+++

---

## :icon-globe: Live Demo

:icon-rocket: **Try it now**: [https://zeroxcarbon.onrender.com/docs](https://zeroxcarbon.onrender.com/docs){target="_blank"}

Interactive API documentation with live testing capabilities.

---

## :icon-rocket: Deployment

Ready for deployment on any Docker-compatible platform including:

+++ :icon-cloud: Cloud Platforms
- AWS (Elastic Container Service)
- Google Cloud (Cloud Run)
- Azure (Container Instances)
- Render (Container Service)
+++