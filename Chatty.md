---
label: Chatty (AnyWhere Chatbot)
icon: comment-discussion
description: "Drop-in JS widget that adds a floating, context-aware chatbot to any website. Customizable theme, branding, system prompt, and page context capture."
order: 87
tags: [JavaScript, Widget, CDN, Shadow DOM, Chatbot]
---

# AnyWhere Chatbot — Chatty

AnyWhere Chatbot ("Chatty") is a lightweight, drop-in JavaScript widget that adds a floating, context-aware chatbot to any website. The widget is delivered as a single script via Jsdelivr cdn. Chatty supports customizable branding, theme mode, system prompt, and optional page context capture.

:::buttons
[Repository :icon-mark-github:](https://github.com/0xarchit/AnyWhere-ChatBot-Chatty){target="_blank"}  
[Live Demo :icon-globe:](https://chatty.0xarchit.is-a.dev){target="_blank"}  
[CDN :icon-link:](https://cdn.jsdelivr.net/gh/0xarchit/AnyWhere-ChatBot-Chatty@1.0.0/chatty.min.js){target="_blank"}
:::

**Quick Start**
- **Install:** Add the script tag to any page near the end of the `body`.

    ```html
    <script src="https://cdn.jsdelivr.net/gh/0xarchit/AnyWhere-ChatBot-Chatty@1.0.0/chatty.min.js"
      mode="dark"
      brandName="AnyWhere ChatBot"
      systemPrompt="You are testing chatbot for AnyWhere Chatbot created and owned by 0xArchit."
      context="toggle"></script>
    ```


## Screenshots {#screenshots}

- Demo 1 — Chatty on GitHub Profile Analyzer tool

  ![Demo 1 — GitHub Profile Analyzer](public/Chatty/demo1.png)

- Demo 2 — Chatty integrated on my portfolio website

  ![Demo 2 — Portfolio Website](public/Chatty/demo2.png)

- Testing — Local testing page for Chatty

  ![Testing — Local Test Page](public/Chatty/testing.png)


> [!TIP]
> :icon-rocket: Quick start: copy the minimal script tag example below and paste it before </body> on your page.

**Quick Start**

**How it Works** {#how-it-works}

**Script Attributes (options)** {#script-attributes-options}
  `

- **`context`**: Controls page context capture. Accepts values such as `true`, `false`, `toggle`. For convenience, the following are also understood: `yes/no`, `on/off`, `1/0`, `always/never`, `auto/default/toggle`. Internally these map to one of three modes:
  - `never` → never include page context (e.g., `context="false"`, `context="no"`, `context="never"`).
  - `toggle` → show a small context toggle in the chat UI so visitors can enable/disable context per session (e.g., `context="toggle"`, `context="auto"`, omitted attribute).

Example attribute usage: `context="toggle"`, `context="true"`, `context="false"`, `context="always"`, `context="never"`.

**Examples** {#examples}
- Minimal (defaults):

  ```html
  <script src="https://cdn.jsdelivr.net/gh/0xarchit/AnyWhere-ChatBot-Chatty@1.0.0/chatty.min.js"></script>
  ```

- Custom brand and light mode:

    ```html
    <script src="https://cdn.jsdelivr.net/gh/0xarchit/AnyWhere-ChatBot-Chatty@1.0.0/chatty.min.js"
      mode="light"
      brandName="SupportBot"></script>
    ```

- Context always enabled with a custom system prompt:

    ```html
    <script src="https://cdn.jsdelivr.net/gh/0xarchit/AnyWhere-ChatBot-Chatty@1.0.0/chatty.min.js"
      context="true"
      systemPrompt="You are a friendly support assistant for ExampleCorp."></script>
    ```

- Programmatic insertion (useful when loading scripts conditionally):

  ```html
  <script>
    const s = document.createElement('script');
    s.src = 'https://cdn.jsdelivr.net/gh/0xarchit/AnyWhere-ChatBot-Chatty@1.0.0/chatty.min.js';
    s.setAttribute('mode', 'dark');
    s.setAttribute('brandName', 'AnyWhere ChatBot');
    document.body.appendChild(s);
  </script>
  ```

- Force context off (no page text captured):

  ```html
  <script src="https://cdn.jsdelivr.net/gh/0xarchit/AnyWhere-ChatBot-Chatty@1.0.0/chatty.min.js" context="false"></script>
  ```

- Toggleable context with a different brand and light mode:

    ```html
    <script src="https://cdn.jsdelivr.net/gh/0xarchit/AnyWhere-ChatBot-Chatty@1.0.0/chatty.min.js"
      mode="light"
      brandName="AnyWhere ChatBot"
      context="toggle"></script>
    ```

- Self-hosted CDN path example:

  ```html
  <script src="https://cdn.example.com/widgets/chatty.js"
  mode="dark"
  brandName="AnyWhere ChatBot"
  systemPrompt="You are a helpful assistant for AnyWhere ChatBot."></script>
  ```

- Defer loading via `defer` attribute so it doesn't block rendering:

  ```html
  <script defer src="https://cdn.jsdelivr.net/gh/0xarchit/AnyWhere-ChatBot-Chatty@1.0.0/chatty.min.js" mode="dark"></script>
  ```

- Programmatically set attributes including context mode:

  ```html
  <script>
    const s = document.createElement('script');
    s.src = 'https://cdn.jsdelivr.net/gh/0xarchit/AnyWhere-ChatBot-Chatty@1.0.0/chatty.min.js';
    s.setAttribute('mode', 'dark');
    s.setAttribute('brandName', 'AnyWhere ChatBot');
    s.setAttribute('context', 'always'); // also accepts: toggle/never/true/false/default
    s.setAttribute('systemPrompt', 'You are a friendly support assistant.');
    document.body.appendChild(s);
  </script>
  ```

**Customization & Theming** {#customization--theming}
- `mode` controls the built-in dark/light palette. Because Chatty uses Shadow DOM, your site CSS won't affect the widget. If you want to change the widget visuals you'll need to modify the script.
- `brandName` and `systemPrompt` are the easiest ways to adapt the assistant to your site and tone of voice.
- The input placeholder and button icons come from the script; editing them requires changing the `chatty.js` source.

Tip: If you plan to support multiple themes later, consider wrapping your overrides in CSS custom properties and reading them inside the widget (requires editing `chatty.js`).

**Privacy & Data Handling** {#privacy--data-handling}
> [!NOTE]
> :icon-shield: Self-host the script and set your own API endpoint if you have strict privacy requirements.

**Privacy & Data Handling**


Configuration notes:

**Accessibility** {#accessibility}
- If your page has strict accessibility requirements, verify contrast and focus order with your auditing tools and adjust the hosted script as needed.

- Chat button does not appear:
  - Confirm the script `src` URL is correct and the CDN is serving the file.
- Chat opens but messages don't send:
  - Confirm the remote API accepts the payload and CORS is configured.
- Context toggle not visible or not working:
  - If `context` is set to `true`/`always` or `false`/`never` the toggle will be forced on/off. Use `context="toggle"` (or `auto`/omit) for a visible toggle.
- Clearing chat history:
  - Open developer console and run: `sessionStorage.removeItem('chatbotHistory')`.

**Developer Notes** {#developer-notes}
- The widget creates a container with id `0xarchit-chatbot-container` and uses Shadow DOM for isolation.
- Chat messages are rendered inside an element with id `0xarchit-chatbot-messages` and history is read from / written to `sessionStorage`.
 - When context is enabled, the page text is appended to the last user message in the payload sent to the API, keeping the on-screen chat history clean.

**Contributing & Support** {#contributing--support}
- To contribute or customize, edit `chatty.js` and test locally by loading `main.html` in your browser.
- For help integrating on specific platforms (WordPress, Shopify, etc.), open an issue or create a fork with platform-specific examples.


## Future Goals {#future-goals}

- Multi-theme support: built-in themes (e.g., primary colors, compact/comfortable density) and a `theme` attribute.
- Custom theming API: CSS custom properties and/or a lightweight config object to override palette, shapes, and spacing without editing the script.
- Markdown rendering for assistant messages (links, code blocks, lists) with safe sanitization.
- Streaming responses for faster perceived latency and typing effect.
- Internationalization (i18n): UI strings and placeholder configurable via attributes; RTL layout support.
- Persistence options: opt-in localStorage persistence and export/import chat transcripts.
