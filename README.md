# 📡 API Status Checker

A lightweight, browser-based dashboard to monitor the real-time status of multiple API services — no backend, no API keys, no installation required.

![Static Badge](https://img.shields.io/badge/runs%20in-browser-blue) ![Static Badge](https://img.shields.io/badge/dependencies-none-brightgreen) ![Static Badge](https://img.shields.io/badge/file-single%20HTML-orange)

## ✨ Features

- **One-click presets** for popular services: OpenAI, Anthropic, GitHub, Cloudflare, Stripe, Twilio, Vercel, Supabase
- **Custom endpoints** — add any URL you want to monitor
- **Smart status detection**
  - Statuspage.io services → reads the official `indicator` field (`operational / degraded / outage`)
  - Custom URLs → normal HTTP fetch; falls back to `no-cors` mode to distinguish *CORS-restricted but reachable* from *truly unreachable*
- **Response time** displayed in ms, color-coded (green / yellow / red)
- **Check All** button + **auto-refresh every 60 seconds** with live countdown
- **Persistent** — added services are saved in `localStorage` and restored on reload
- **Zero dependencies** — single `index.html`, works offline after first load

## 🚀 Usage

```bash
# Clone
git clone https://github.com/og34/api-status-checker.git
cd api-status-checker

# Open directly in your browser — no server needed
open index.html
```

Or just download `index.html` and double-click it.

## 📊 Status Colors

| Color | Meaning |
|---|---|
| 🟢 Green | Fully operational |
| 🟡 Yellow | Degraded, slow, or CORS-restricted (reachable) |
| 🔴 Red | Outage or unreachable |
| 🔵 Blue | Currently checking… |
| ⚫ Gray | Not yet checked |

## 🛠 Adding a Custom Service

1. Click **+ Add Service**
2. Enter a name and the URL to check (e.g. `https://api.example.com/health`)
3. Choose **HTTP fetch** for regular endpoints or **Statuspage.io** if the service uses [statuspage.io](https://www.atlassian.com/software/statuspage)
4. Click **Add Service** — it will be checked immediately

## 🔒 Privacy

All requests are made directly from your browser. No data is sent to any third-party server. No API keys are stored anywhere.

## License

MIT
