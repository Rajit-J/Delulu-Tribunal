# Delulu Tribunal

A local-first, playful reality-check web app. Users choose a case category, describe a situation, and receive a deterministic assessment. Case history is stored in the browser rather than synchronized to a server.

## Features

- Landing page, application form, and browser-local history.
- Category-aware assessment and safety handling.
- Optional AI verdict integration; the local deterministic experience does not require an API key.
- Optional payment-link interface. The static app does not verify payment or securely unlock paid content.

## Technology

- TypeScript and Vite
- Netlify Functions for optional server-side AI calls
- Browser storage for local history

## Run locally on Windows

Prerequisites: Node.js and npm. In PowerShell:

```powershell
cd D:\MyProjects\Delulu-Tribunal
npm ci
npm run dev -- --host 127.0.0.1 --port 5173
```

Open [http://127.0.0.1:5173](http://127.0.0.1:5173). Stop the server with **Ctrl+C**.

Create a production build with:

```powershell
npm run build
```

## Optional AI configuration

AI verdicts are optional and disabled by default. To enable them, configure `ENABLE_AI_VERDICTS` and `GEMINI_API_KEY` in the server-side environment used by Netlify Dev or a deployment. Never put a provider key in frontend code or a `VITE_` variable. Do not commit `.env` files. Provider pricing, quotas, and data terms can change; avoid sending sensitive personal information.

## Limitations

Browser history can be lost if site data is cleared and is not synced across devices. A static frontend cannot securely verify payments. The safety checks are not a complete safety classifier.

## Before publishing

Review environment files and deployment settings. No license is included; add one only after confirming ownership and terms for all bundled assets.

##Current Live Demo Link

https://delulu-tribunal.netlify.app/
