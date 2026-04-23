# 🏏 IPL Dashboard — Personal Dugout

A single-file, dark-themed personal dashboard for following the **IPL 2026** season. Built with vanilla HTML/CSS/JS — no build tools, no dependencies, just open `index.html` in a browser.

---

## Features

- **Live score banner** — appears automatically when CSK is playing, showing live innings scores and match status
- **Countdown timer** — counts down to the next CSK match (days · hours · mins · secs)
- **Next match card** — displays fixture details, venue, and key pre-match stats
- **CSK schedule strip** — scrollable timeline of all 14 CSK fixtures with results and upcoming games
- **Points table** — full IPL 2026 standings with animated progress bars, pulled live from the API
- **Scrolling ticker** — top-bar marquee with table leaders, Orange Cap, Purple Cap, and CSK highlights
- **API key setup** — first-run modal to connect your CricAPI key; stored in `localStorage`, never shared

---

## Getting Started

### 1. Get a free CricAPI key

1. Go to [cricapi.com](https://cricapi.com) and sign up (free tier)
2. Copy your API key from the dashboard
3. The free tier allows **100 requests/day** — enough for a personal dashboard

### 2. Open the dashboard

```bash
# No server needed — just open the file directly
open index.html        # macOS
start index.html       # Windows
xdg-open index.html    # Linux
```

### 3. Connect your API key

On first load a setup screen appears. Paste your CricAPI key and click **Connect**. The key is saved in your browser's `localStorage` and is never transmitted anywhere except directly to `cricapi.com`.

---

## Customisation

The file contains `✏️` markers for the spots you'll want to personalise:

| What | Where in `index.html` |
|---|---|
| Your name (title & greeting) | Search `Esther` — replace all occurrences |
| Next match details | `<!-- ══ NEXT MATCH ══` section |
| Ticker content | `<!-- ══ TICKER ══` section |
| CSK schedule fixtures | `<!-- ══ CSK SCHEDULE STRIP ══` section |
| Points table rows | `<!-- ══ POINTS TABLE ══` section |

The CSK colour palette and all 10 team colours are defined as CSS custom properties at the top of the `<style>` block — easy to retheme.

---

## How Live Data Works

```
cricapi.com  ──fetch──▶  browser
```

- On load (or **Refresh**), the app calls `cricapi.com/v1/currentMatches` and `cricapi.com/v1/series_points_table`
- If CSK is in a live match the banner appears and data auto-refreshes every **30 seconds**
- Otherwise data refreshes every **5 minutes**
- API key is read from `localStorage`; you can change it anytime via the ⚙ API Key button

---

## Tech Stack

| Layer | Choice |
|---|---|
| Markup | HTML5 |
| Styling | CSS (custom properties, animations, grid/flex) |
| Logic | Vanilla JavaScript (ES2020, no framework) |
| Fonts | Chakra Petch · Inter · JetBrains Mono (Google Fonts) |
| Data | [CricAPI v1](https://cricapi.com) |

---

## Project Structure

```
ipl_dashboard/
└── index.html   ← entire app (HTML + CSS + JS, self-contained)
```

---

## License

Personal use. Not affiliated with the BCCI or IPL.
