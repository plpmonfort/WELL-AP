# WELL AP Study Companion

An offline-capable study app for the WELL AP (WELL v2) exam. Three modes — **Learn**, **Flashcards**,
**Quiz** — plus an exam countdown and saved progress.

Built as a **PWA (Progressive Web App)**: it installs to your phone's home screen with its own icon,
opens full-screen without browser chrome, and works with no signal.

---

## Files

| File | Purpose |
|---|---|
| `index.html` | The entire app — content, styles and logic in one file |
| `manifest.json` | Tells the phone the app's name, icon, colours and display mode |
| `sw.js` | Service worker — caches everything so it works offline |
| `icon-192.png` / `icon-512.png` | App icons |
| `icon-maskable-512.png` | Android adaptive icon |
| `apple-touch-icon.png` | iOS home-screen icon |
| `.nojekyll` | Stops GitHub Pages from mangling the files |

All paths are **relative**, so it works from a subfolder like `username.github.io/well-ap/`.

---

## Option A — GitHub Pages (recommended)

**1. Create the repository**
- Go to <https://github.com/new>
- Repository name: `well-ap` (anything is fine)
- Set it to **Public** — Pages needs this on free accounts
- Click **Create repository**

**2. Upload the files**
- On the new repo page, click **uploading an existing file**
- Drag in *all* the files from this folder (including `.nojekyll`)
- Click **Commit changes**

**3. Turn on GitHub Pages**
- Go to **Settings** → **Pages** (left sidebar)
- Under *Source*, choose **Deploy from a branch**
- Branch: **main**, folder: **/ (root)** → **Save**
- Wait 1–2 minutes. Your URL appears at the top of that page:
  `https://YOUR-USERNAME.github.io/well-ap/`

**4. Install it on your iPhone**
- Open that URL **in Safari** (this only works in Safari on iOS — not Chrome)
- Tap the **Share** button (square with an arrow, bottom centre)
- Scroll down and tap **Add to Home Screen**
- Name it and tap **Add**

Done. It now sits on your home screen like any other app, opens full-screen, and works on the Tube.

---

## Option B — Netlify Drop (no account, ~30 seconds)

If you just want it working now and don't care about version control:

1. Go to <https://app.netlify.com/drop>
2. Drag this whole folder onto the page
3. You get a live URL instantly — open it in Safari and Add to Home Screen as above

You can connect it to GitHub later if you want.

---

## Updating the app later

1. Edit `index.html`
2. **Important:** bump the cache version in `sw.js` — change `wellap-v1` to `wellap-v2`, etc.
   Without this, phones keep serving the old cached copy.
3. Re-upload / commit. Reopen the app twice to pick up the new version.

---

## Notes

- **Progress is stored per-device** in `localStorage` — reviewed sections, quiz history and exam date
  won't sync between your phone and laptop. There's a reset link at the bottom of the app.
- **Content reflects WELL v2 (Q4 2020, exam-referenced).** IWBI updates the standard via quarterly
  addenda, so verify thresholds against the current digital standard at
  <https://v2.wellcertified.com> before exam day.
- Concept colours follow IWBI's official WELL v2 palette (blue → green gradient, Air `#91cbd3`
  through Community `#a7d6ad`).
- Not affiliated with or endorsed by IWBI. Personal study aid.
