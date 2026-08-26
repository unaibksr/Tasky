# Chore Quest

A retro-arcade style daily chores tracker. Add chores (name, category, points),
tap a chore to score points, and browse your completed-chore history in the
Archive. Installable as a Progressive Web App (PWA) with offline support and
arcade sound effects.

## Features

- Add chores with a custom category and point value (points stepper +10 / −10).
- Tap a chore to earn its points; tap again to undo.
- Categories: General, Abu, Home, Myself, Uncle (plus any custom category).
- Archive view grouped by date showing each completed chore and daily totals.
- Neon / pixel "retro arcade" UI with glowing SCORE, confetti on score, and
  Web-Audio click & coin sounds (with a mute toggle).
- Installable PWA: manifest + service worker, works offline, saves to
  `localStorage`.

## Run it

The app is just static files (`index.html`, `sw.js`, `icon/`). Open `index.html`
directly, or serve the folder over HTTP (required for the PWA / install prompt):

```bash
# Option A — Node (included helper)
node server.js
# then open http://localhost:8000/

# Option B — any static server, e.g.
python3 -m http.server 8000
```

To install as an app: open the URL in Chrome/Edge and use the address-bar
**Install** button (or menu → Install Chore Quest).

## Project structure

```
.
├── index.html          # App (markup, styles, logic)
├── sw.js               # Service worker (offline cache)
├── server.js           # Optional tiny static dev server (Node)
├── icon/
│   ├── site.webmanifest
│   ├── android-chrome-192x192.png
│   ├── android-chrome-512x512.png
│   ├── apple-touch-icon.png
│   ├── favicon-32x32.png
│   ├── favicon-16x16.png
│   └── favicon.ico
├── README.md
├── LICENSE
└── .gitignore
```

## Notes

- Data is stored in the browser's `localStorage` (per origin), so it is tied to
  the device/browser you use.
- Google Fonts ("Press Start 2P", "VT323") load from a CDN; offline, the app
  falls back to a monospace font.
