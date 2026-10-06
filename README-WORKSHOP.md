# Build Your Own Jarvis — Vapi Workshop Kit

Hands-on materials for **Build Your Own Jarvis: Create and Integrate an AI Voice Assistant into Your Website in 45 Minutes**.

No Node.js or npm required for the labs. You only need a browser, microphone, and two values from the [Vapi Dashboard](https://dashboard.vapi.ai).

## Quick start (5 minutes)

1. **Copy configuration**

   ```text
   copy config.example.js config.js
   ```

   On macOS/Linux: `cp config.example.js config.js`

2. **Edit `config.js`** — set `publicKey` and `assistantId` from the Vapi dashboard.

3. **Create an assistant** (if you have not already):
   - Paste the system prompt from `prompts/assistant-system-prompt-short.md` into your assistant’s system prompt in the dashboard.
   - Set the first message to the introduction line in that file (optional but recommended).

4. **Open a lab page over HTTP** (required for microphone access):
   - **Recommended:** VS Code → install **Live Server** → right-click `01-jarvis-widget.html` → _Open with Live Server_.
   - Or from this folder: `npx --yes serve .` (only if you have Node; not required if you use Live Server).
   - Do **not** rely on double-clicking `file://` links — mic/WebRTC often fails.

5. **Allow microphone** when prompted and start talking.

## Lab files

| File                        | What you learn                                                               |
| --------------------------- | ---------------------------------------------------------------------------- |
| `01-jarvis-widget.html`     | Fastest integration — floating Vapi voice widget via official CDN script     |
| `02-dealer-landing.html`    | Same widget on a sample “dealer website” landing page                        |
| `03-conversation-page.html` | Custom Start/End/Mute buttons and live transcript (Vapi Web SDK via CDN ESM) |

## Folder layout

```text
VapiDemo/
├── config.example.js       # Template — copy to config.js
├── config.js               # Your keys (gitignored; create locally)
├── 01-jarvis-widget.html
├── 02-dealer-landing.html
├── 03-conversation-page.html
├── prompts/
│   └── assistant-system-prompt-short.md
├── slides/
│   └── WORKSHOP-SPEAKER-NOTES.md
└── README-WORKSHOP.md      # This file
```

## Vapi keys cheat sheet

| Key                 | Where it goes         | Workshop labs                      |
| ------------------- | --------------------- | ---------------------------------- |
| **Public API key**  | Browser (`config.js`) | Yes — all labs                     |
| **Assistant ID**    | Browser (`config.js`) | Yes — all labs                     |
| **Private API key** | Server only           | No — not used in this kit          |
| **Phone number ID** | Server only           | No — outbound calls need a backend |

## Troubleshooting

| Problem                      | Try                                                               |
| ---------------------------- | ----------------------------------------------------------------- |
| “Configure config.js” banner | Copy `config.example.js` → `config.js` and paste real keys        |
| No microphone / call fails   | Use Live Server or `http://localhost`, not `file://`              |
| Call starts then errors      | Check assistant ID; confirm public key is **Public**, not Private |
| Widget does not appear       | Disable ad blockers; check browser console (F12)                  |
| Silent assistant             | Dashboard → assistant → voice/model; check account credits        |

## Security reminders for production

- Restrict the **public** key to your website origins in the Vapi dashboard.
- Never put the **private** key in HTML or front-end JavaScript.
- Add consent copy if your organization records or processes voice data.

## Links

- [Vapi documentation](https://docs.vapi.ai)
- [Voice widget (HTML script tag)](https://docs.vapi.ai/assistants/examples/voice-widget)
- [Web quickstart](https://docs.vapi.ai/quickstart/web)
