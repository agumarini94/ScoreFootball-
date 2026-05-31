# ScoreFootball

A mobile-first football tournament manager for organizing multi-team futsal and small-sided games. Track goals, manage team rotations, and view live standings — all offline, with no backend required.

**Live app:** https://agumarini94.github.io/ScoreFootball-/

## What It Does

ScoreFootball handles the full lifecycle of an informal football tournament:

1. **Setup** — Configure match duration, number of teams (2–20), game format (Futsal-5, Futsal-7, or 11-a-side), and goal limit to win
2. **Team Registration** — Name each team, add players, and pick a team color
3. **Live Scoring** — Tap players to add goals and track kicks in real time during matches
4. **Automatic Rotation** — In 3-team tournaments, the winner stays on, the loser sits out, and the resting team enters
5. **Statistics** — Full league table, top scorers, top kick leaders, and match history

## Features

- **Match timer** with pause, reset, and auto-finish when time expires
- **Goal limit detection** — match ends automatically when a team reaches the configured goal limit
- **Draw resolution modal** — when 3 teams tie, prompts which team sits out next
- **Soccer field visualizer** — optional drag-and-drop player positions per game format
- **Long-press to edit** player names during a match
- **Confetti animation** on every goal
- **Haptic feedback** (vibration) on mobile when goals are scored
- **League table** with PJ, W, D, L, GF, GA, GD, and Points
- **Match history** with delete-last-match support
- **Bilingual UI** — Spanish and English
- **Fully offline** — all data saved to localStorage, no network calls

## Tech Stack

| | |
|---|---|
| Framework | React 19 |
| Build tool | Vite |
| Styling | Tailwind CSS 4 |
| Deployment | GitHub Pages (`gh-pages`) |

No backend. No API keys. No dependencies beyond the frontend.

## Getting Started

```bash
cd mi-app-futbol
npm install
npm run dev       # http://localhost:5173
```

### Build & Deploy

```bash
npm run build     # production build → dist/
npm run preview   # preview the build locally
npm run deploy    # push to GitHub Pages
```

## Project Structure

```
mi-app-futbol/
├── src/
│   ├── App.jsx           # Main app & tournament state machine
│   ├── Scoreboard.jsx    # Live match scoring screen
│   ├── useLanguage.js    # Language toggle hook (ES/EN)
│   ├── helpers.js        # Translations & localStorage utilities
│   └── main.jsx          # React entry point
└── public/
    └── pelota.png        # App icon
```

## Data Persistence

All state is stored in `localStorage`:

- Tournament configuration (duration, teams, format, goal limit)
- Team names, player names, and colors
- Match results and history
- Player statistics (goals, kicks, playing time)
- Field player positions
- Language preference

Closing or refreshing the browser preserves all progress.
