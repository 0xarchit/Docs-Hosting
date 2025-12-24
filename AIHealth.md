---
label: AI Health
icon: heart
description: "Secure nutrition analysis application leveraging Google Gemini API for calorie tracking and 3D body visualization."
order: 82
tags: [Next.js, Tailwind CSS, Gemini API, 3D, Health]
---

# 🥗 AI Health - Smart Nutrition Analysis

![Next.js](https://img.shields.io/badge/Next.js-black?style=flat-square&logo=next.js&logoColor=white) ![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white) ![Gemini](https://img.shields.io/badge/Gemini_API-8E75B2?style=flat-square&logo=google&logoColor=white) ![License](https://img.shields.io/github/license/0xarchit/AI-Health?style=flat-square)    
![Stars](https://img.shields.io/github/stars/0xarchit/AI-Health?style=flat-square) ![Repo Size](https://img.shields.io/github/repo-size/0xarchit/AI-Health?style=flat-square) ![Forks](https://img.shields.io/github/forks/0xarchit/AI-Health?style=flat-square) [![Website](https://img.shields.io/website?url=https://aihealth.0xarchit.is-a.dev/&style=flat-square)](https://aihealth.0xarchit.is-a.dev/){target="_blank"}

**AI Health** is a secure web application that empowers users to analyze food images using their own personal AI quota. By leveraging Google's Gemini API via OAuth, users can get detailed nutrition breakdowns without relying on a shared developer key or paid subscription.

**:icon-mark-github: GitHub:** [https://github.com/0xarchit/AI-Health](https://github.com/0xarchit/AI-Health){target="_blank"}  
**:icon-globe: Live Project:** [https://aihealth.0xarchit.is-a.dev](https://aihealth.0xarchit.is-a.dev){target="_blank"}

## 🚀 How It Works {#how-it-works}

**AI Health** operates on a **"Bring Your Own Key" (BYOK)** model via seamless OAuth integration.

1.  **:icon-lock: Secure Login**: You sign in with your Google Account.
2.  **:icon-key: Permission Grant**: A specific scope request is made to access the Gemini API on your behalf.
3.  **:icon-database: Encrypted Storage**: Your session tokens are encrypted (AES-256-GCM) and stored in our secure **Postgres Database**.
4.  **:icon-zap: AI Analysis**: When you analyze an image:
    *   The app retrieves your secure token.
    *   The image is processed by **Google Gemini** using your free tier quota.
    *   Results are instantly cached to prevent faster loading next time.

## ✨ Key Features {#features}

### 🥗 Smart Nutrition Analysis {#nutrition-analysis}
- :icon-graph: **Instant Breakdown**: Get calories, macronutrients (Protein, Carbs, Fats), and micronutrients via intuitive gauges.
- :icon-search: **Ingredient Detection**: Identifies primary ingredients visible in the image.
- :icon-pulse: **Health Assessment**: AI provides a healthiness score and highlights potential allergens or concerns.

### 🧬 Interactive 3D Analysis {#3d-analysis}
- :icon-person: **Whole-Body Visualization**: A high-fidelity 3D human model (Male/Female) visualizes the impact of food on your body.
- :icon-alert: **Organ Risk Mapping**: Specific organs (e.g., Heart, Liver, Kidneys) light up in **Red** (High Risk), **Yellow** (Moderate), or **Green** (Low) based on ingredients.
- :icon-info: **Interactive Tooltips**: Hover over affected areas to read detailed medical insights (e.g., *"High sodium impacts cardiovascular health"*).

### 🤖 AI Health Assistant (Chatbot) {#chatbot}
- :icon-comment-discussion: **Context-Aware**: The integrated chatbot knows about your recently analyzed food.
- :icon-light-bulb: **Personalized Advice**: Ask questions like *"Is this good for a keto diet?"* or *"How can I make this healthier?"*
- :icon-broadcast: **Real-time Interaction**: Get instant answers to your nutrition queries.

### 📊 Comprehensive Dashboard {#dashboard}
- :icon-history: **Scan History**: All your analyses are saved to the database.
- :icon-graph: **Interactive Reports**: View detailed logs of your food intake over time.
- :icon-beaker: **Medication Tracking**: Keep track of your supplements or medications alongside your nutrition.
- :icon-file: **User Reports**: Generate insights based on your eating habits.

### 👤 User Profile & Health Context {#profile}
- :icon-id-badge: **Biological Context**: Define your gender, allergies, and existing conditions. The AI uses this to tailor its nutrition advice.

### ⚡ Advanced Performance {#performance}
- :icon-cache: **Smart Caching**: Duplicate images are detected immediately, saving your API quota and providing instant results.
- :icon-image: **Optimized Assets**: Images are delivered via **ImageKit.io** for lightning-fast loading.
- :icon-id-badge: **Medical Archive**: Upload and store your medical records or prescriptions for easy access.
- :icon-shield-lock: **Privacy Mode**: All health data is encrypted and stored securely with row-level security policies.

## 🛠️ Usage Guide {#usage-guide}

### 1️⃣ Authentication
Click the **"Get Started"** button. You will be redirected to Google to sign in. 
> [!NOTE]
> :icon-info: We only ask for the permissions strictly necessary to analyze images using the Gemini API.

### 2️⃣ Dashboard Interface
Once logged in, you will see your personal dashboard.
- **Upload Area**: Drag & drop your food image here.
- **Recent Scans**: Your history is available in the sidebar.
- **Clear History**: Use the option in settings to wipe your data from our database.

### 3️⃣ Analyzing Food
1.  Upload an image.
2.  Click **"Analyze Nutrition"**.
3.  Wait a few seconds for Gemini to process the visual data.
4.  Review the **Nutrition Card** that appears with detailed stats.
5.  **Explore the 3D Model**: Rotate and zoom the 3D human model to see which organs are affected by your food choice.

### 4️⃣ Interactive Chat
After analysis, use the **Chat Assistant** floating button.
- It automatically loads the context of your current food.
- Ask for recipes, alternatives, or explanation of specific nutrients.

### 5️⃣ Managing Your Profile
Navigate to the **Profile** page to:
- **Update Health Context**: Add allergies (e.g., "Peanuts"), conditions (e.g., "Diabetes"), or medications.
- **Upload Records**: Store images of your prescriptions or lab results securely.

## 💻 Tech Stack {#tech-stack}

| Category | Technology |
| :--- | :--- |
| **Framework** | [Next.js 16 (App Router)](https://nextjs.org/) |
| **Styling** | [Tailwind CSS](https://tailwindcss.com/) |
| **Database** | Postgres Database (via [Drizzle ORM](https://orm.drizzle.team/)) |
| **AI Model** | Google Gemini 2.0 Flash |
| **Image CDN** | ImageKit.io |
| **3D Models** | NIH 3D Print Exchange |

## 🏆 Credits & Acknowledgements {#credits}

We deeply appreciate the tools and resources that make this project possible.

| Resource | Usage |
| :--- | :--- |
| **[Google Gemini API](https://ai.google.dev/)** | The core intelligence engine for nutrition analysis. |
| **[ImageKit.io](https://imagekit.io/)** | High-performance image optimization and delivery. |
| **[NIH 3D Print Exchange](https://3d.nih.gov/)** | Source for accurate human anatomy 3D models. |
| **[Lucide Icons](https://lucide.dev/)** | Beautiful, consistent icons used throughout the app. |

## 🤝 Community {#community}

- **[Code of Conduct](https://github.com/0xarchit/AI-Health/blob/main/.github/CODE_OF_CONDUCT.md)**
- **[Contributing Guidelines](https://github.com/0xarchit/AI-Health/blob/main/.github/CONTRIBUTING.md)**
- **[Security Policy](https://github.com/0xarchit/AI-Health/blob/main/.github/SECURITY.md)**

### Contact
- **Email**: mail@0xarchit.is-a.dev
- **Website**: [0xarchit.is-a.dev](https://0xarchit.is-a.dev){target="_blank"}
- **GitHub**: [@0xarchit](https://github.com/0xarchit){target="_blank"}
