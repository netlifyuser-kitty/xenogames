# Xeno Games

A free, static game library for the browser. Pick a game, hit play, no downloads or installs.

**Live site:** https://<your-username>.github.io/xeno-games/

## Features

- Alien-themed UI with animated background and 3D tilt cards
- Search, category tabs, and a "Surprise me" random game button
- Favorites, saved in your browser
- Fullscreen player with an "open in new tab" fallback
- 4-digit PIN gate (browser-side only, so treat it as a casual lock, not real security)
- Single-file site: just `index.html`, no build step or dependencies

## Games

All games are free, open-source, or freeware, and are loaded from their creators' own pages:

| Game | Category |
| --- | --- |
| 2048 | Puzzle |
| Hextris | Puzzle |
| React Tetris | Classic |
| Pac-Man | Classic |
| Clumsy Bird | Arcade |
| Astray | Arcade |

## Add a game

Open `index.html`, find the `GAMES` list near the bottom, and add a line:

```js
{name:"My Game", cat:"Arcade", glyph:"🎮", h:200, desc:"Short description.", url:"https://example.com/game/"},
```

- `cat` sets the category tab (new categories appear automatically)
- `h` is a hue from 0 to 360 for the card art color
- Only add games you have the right to host or link to. Some sites block embedding, so if a game won't load in the player, use the "New tab" button or remove it.

## Change the PIN

The PIN is stored as a SHA-256 hash in the `HASH` constant in `index.html`. To change it, run this with your new code and paste the result over the old hash:

```
printf '1234' | sha256sum
```

## Deploy

1. Push `index.html` to a public GitHub repo.
2. Go to **Settings → Pages**, choose **Deploy from a branch**, then `main` and `/ (root)`.
3. Your site goes live at `https://<your-username>.github.io/<repo-name>/`.

## Notes

- Fonts load from Google Fonts, so the page needs an internet connection to look its best.
- Not affiliated with any of the game creators. All games belong to their respective authors.
