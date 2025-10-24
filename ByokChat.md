---
label: BYOK Chat
icon: comment-discussion
description: "Versatile Next.js chat platform with multi-provider AI support, context management, and beautiful animated UI powered by ReactBits."
order: 85
tags: [Next.js, TypeScript, AI, Chat, Zustand, IndexedDB, Shadcn UI]
---

# BYOK Chat Platform (Next.js)

BYOK Chat is a versatile Next.js platform designed to integrate with various AI providers, enabling seamless communication and customization. This platform supports both standard OpenAI-compatible APIs and Cloudflare Workers AI.

**:icon-mark-github: GitHub:** [https://github.com/0xarchit/ByokChat](https://github.com/0xarchit/ByokChat){target="_blank"}  
**:icon-globe: Live Demo:** [https://byok.0xarchit.is-a.dev](https://byok.0xarchit.is-a.dev){target="_blank"}


> [!TIP]
> :icon-rocket: Quick start: Clone the repo, run `npm install`, then `npm run dev` to launch the development server at `http://localhost:3000`.

## Features {#features}

- :icon-paintbrush: **Beautiful Landing Page**: Modern, animated landing page with Aurora background effects and smooth scroll animations using ReactBits components
- :icon-rocket: **Next.js 16 App Router**: Built with the latest Next.js for optimal performance and SEO
- :icon-gear: **Provider Management**: Add, edit, and manage multiple AI providers
- :icon-checklist: **Model Selection**: Fetch available models or manually add custom models
- :icon-key: **API Key Validation**: Test API keys with selected models
- :icon-cloud: **Cloudflare Workers Support**: Rotate between multiple accounts using worker URLs
- :icon-paintbrush: **Customizable UI**: Tailor the interface to your needs with Shadcn UI components
- :icon-database: **Client-Side Storage**: Uses IndexedDB for local data persistence
- :icon-moon: **Theme Support**: Built-in light, dark, and cyber-aurora themes
- :icon-code: **TypeScript**: Fully typed for better development experience
- :icon-play: **Animated Components**: Leverages framer-motion and GSAP for smooth animations

## Routes {#routes}

- `/` - Landing page showcasing features, advantages, and use cases
- `/chat` - Main chat interface for AI conversations

## Supported AI Providers {#supported-ai-providers}

> [!NOTE]
> :icon-globe: BYOK Chat supports all OpenAI-compatible endpoints with several fallbacks for maximum reliability.

### Popular Free AI Providers {#popular-free-ai-providers}

1. :icon-zap: **Groq**
- Base URL: [https://api.groq.com/openai/](https://api.groq.com/openai/)


2. :icon-cpu: **Mistral**
- Base URL: [https://api.mistral.ai/v1](https://api.mistral.ai/v1)


3. :icon-workflow: **OpenRouter**
- Base URL: [https://openrouter.ai/api/v1](https://openrouter.ai/api/v1)
   

4. :icon-pulse: **Cerebras**
- Base URL: [https://api.cerebras.ai/v1](https://api.cerebras.ai/v1)


5. :icon-search: **Google Generative Language**
- Base URL: [https://generativelanguage.googleapis.com/v1beta/openai/](https://generativelanguage.googleapis.com/v1beta/openai/)


6. :icon-cloud: **Cloudflare Worker AI**
- Deploy your own worker version to integrate seamlessly with the platform.
- Refer to the [Cloudflare Workers documentation](https://developers.cloudflare.com/workers/) for setup instructions.

## Tech Stack {#tech-stack}

| Category | Technologies |
|----------|-------------|
| **Framework** | Next.js 16 (App Router) |
| **Language** | TypeScript |
| **Styling** | Tailwind CSS v3 |
| **UI Components** | Shadcn UI |
| **State Management** | Zustand |
| **Database** | IndexedDB (via localforage) |
| **Markdown** | React-Markdown with Mermaid support |
| **Icons** | Lucide React |

## Getting Started {#getting-started}

### Prerequisites {#prerequisites}

- Node.js (v20 or higher)
- npm, pnpm, or yarn

### Installation {#installation}

1. Clone the repository:
   ```bash
   git clone https://github.com/0xarchit/ByokChat.git
   cd ByokChat/byok-chat
   ```

2. Install dependencies:
   ```bash
   npm install
   # or
   pnpm install
   # or
   yarn install
   ```

3. Start the development server:
   ```bash
   npm run dev
   # or
   pnpm dev
   # or
   yarn dev
   ```

4. Open your browser and navigate to `http://localhost:3000`.

### Building for Production {#building-for-production}

```bash
npm run build
npm run start
```

This will create an optimized production build and start the production server.

## Usage {#usage}

### Adding a Provider {#adding-a-provider}

1. Click on "Add Provider".
2. Select the provider type (Standard or Cloudflare).
3. Fill in the required fields:
   - **Standard**: API URL, API keys, and models.
   - **Cloudflare**: Worker URL, max index, and models.
4. Test the API key and save the provider.

### Editing a Provider {#editing-a-provider}

1. Navigate to the "Providers" section.
2. Click on the edit icon next to the provider.
3. Update the fields and save changes.

### Fetching Models {#fetching-models}

- For standard providers, click "Fetch Available Models" to retrieve models from the API.
- For Cloudflare providers, manually add models using the input field.

## Project Structure {#project-structure}

```
byok-chat/
├── app/                    # Next.js App Router
│   ├── layout.tsx         # Root layout with metadata
│   ├── page.tsx           # Home page
│   ├── not-found.tsx      # 404 page
│   └── globals.css        # Global styles and theme variables
├── components/            # React components
│   ├── ui/               # Shadcn UI components
│   ├── settings/         # Settings-related components
│   └── *.tsx             # Feature components
├── lib/                  # Utility functions
│   ├── db.ts            # IndexedDB configuration
│   ├── api.ts           # API utilities
│   └── utils.ts         # Helper functions
├── store/               # Zustand state management
│   ├── chatStore.ts     # Chat state
│   ├── providerStore.ts # Provider state
│   └── settingsStore.ts # Settings state
├── types/               # TypeScript type definitions
├── hooks/               # Custom React hooks
└── public/              # Static assets
```

## Context Management & Summarization {#context-management--summarization}

This project includes built-in context management features designed to keep conversations coherent while staying within model context windows and token limits. The system balances retaining recent, relevant messages with periodic summarization of older content so the model keeps essential context without sending the entire chat history.

> [!IMPORTANT]
> :icon-checklist: Context management ensures your conversations remain coherent even with long chat histories while respecting token limits.

### Key Behaviors {#key-behaviors}

- :icon-sync: **Automatic summarization**: After a configurable number of recent messages (default: 20) the app will create a concise summary of the previous segment of the conversation and store it with the chat. Future requests include that summary as system context so the assistant retains the important facts and decisions from earlier messages.
- :icon-clock: **Context windowing**: The app keeps the most recent N messages (configurable per chat and globally; default: 10) and forwards them along with the latest user prompt and the latest summary. This keeps the input size smaller while preserving immediate conversational context.
- :icon-pulse: **Background summarization**: Summaries are generated asynchronously in the background so they don't block the active chat. If summarization fails, the system logs the error and continues; it will retry during subsequent summarization cycles.
- :icon-workflow: **Provider rotation & resiliency**: When using Cloudflare worker providers or multiple API keys, the system rotates indices and keys to avoid throttling. Summaries and requests are sent through the same provider route and will respect provider-specific requirements (for example, sending an `index` field when using Cloudflare Workers).

### Configurable Settings {#configurable-settings}

- **summarizeAfter**: Number of messages per summarization batch (default 20). When this many non-system messages accumulate, the app will produce a summary for that segment.
- **retainMessages**: Number of recent messages to keep after summarization (default 10). These messages are sent directly with the prompt to preserve local conversational continuity.
- **temperature**: Optional override for the model temperature used in chat requests or summarization (leave empty to use provider/API defaults).
- **maxTokens**: Optional override for max tokens for completions and summarization (leave empty to use provider/API defaults).

### Best Practices {#best-practices}

- :icon-beaker: Tune `summarizeAfter` and `retainMessages` based on the model you use (larger models can handle larger contexts). Lower `retainMessages` when you need to conserve tokens.
- :icon-note: Keep summaries concise but informative — the summarization prompt in the app aims for clear, structured summaries focusing on topics, decisions, and facts necessary to continue the conversation.
- :icon-shield: Monitor token usage and set `maxTokens` conservatively if you are on a rate limit or cost-sensitive provider.

### Implementation Notes {#implementation-notes}

- The app builds a `messages` array that includes:
   - the system prompt (including the stored summary when present),
   - the most recent retained user/assistant messages,
   - the latest user message triggering the request.
- When the configured `summarizeAfter` threshold is reached, older segments are summarized using the same chat completion endpoint in the background. The produced summary is stored in the chat object and used as system context for later requests.
- Summarization requests use a low temperature (for determinism) and a higher `max_tokens` to allow longer, structured summaries.

If you want to change defaults or experiment with different summarization prompts, check the implementation in `lib/api.ts`, `store/chatStore.ts`, and the settings UI in `components/settings/ContextControls.tsx`.

## Deployment {#deployment}

### Vercel (Recommended)

The easiest way to deploy your Next.js app is to use [Vercel](https://vercel.com):

1. Push your code to GitHub
2. Import your repository to Vercel
3. Vercel will automatically detect Next.js and configure the build settings
4. Deploy!

### Other Platforms {#other-platforms}

You can also deploy to:
- **Netlify**: Supports Next.js with automatic configuration
- **AWS Amplify**: Full support for Next.js
- **Docker**: Use the provided Dockerfile for containerized deployments
- **Self-hosted**: Build the app and run with `npm start`

## Contributing {#contributing}

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License {#license}

This project is licensed under the MIT License. See the LICENSE file for details.

## Support {#support}

For issues, questions, or contributions, please visit the [GitHub repository](https://github.com/0xarchit/ByokChat).

---

**Happy chatting!** 🚀