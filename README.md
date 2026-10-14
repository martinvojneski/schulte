# Schulte Table

Tap the numbers 1 → N² in order on a shuffled 4×4, 5×5 or 6×6 grid as fast as you can.
The numbers are only generated when you press **Start** (the timer starts at the same moment), so the grid can't be memorized.

- Wrong taps flash red and count as mistakes; re-tapping an already found number is ignored.
- Best time and recent runs are kept per grid size on the device.
- Found numbers stay on the board looking exactly like the others (classic Schulte), so they keep getting in the way of the search.
- Works offline after the first visit and installs to the iPhone home screen as a full-screen app.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole game (HTML, CSS and JS in one file) |
| `manifest.webmanifest` | App name, colors and icons for "Add to Home Screen" |
| `sw.js` | Service worker that caches the app for offline play |
| `icons/` | Home-screen icons (180 px is the one iOS uses) |

## Run locally

```bash
python -m http.server 8080
```

Then open http://localhost:8080.

## Host it for free on GitHub Pages

```bash
git init
git add .
git commit -m "Schulte Table"
gh repo create schulte --public --source . --push
gh api -X POST repos/{owner}/schulte/pages -f "source[branch]=main" -f "source[path]=/"
```

After a minute the game is live at `https://<your-github-username>.github.io/schulte/`.
To update it later, commit and `git push`; the app picks up the new version on its next launch.

## Install on iPhone

1. Open the GitHub Pages link in **Safari**.
2. Tap **Share** → **Add to Home Screen** → **Add**.
3. Launch it from the home screen icon: it opens full screen, without Safari's bars, and works offline.
