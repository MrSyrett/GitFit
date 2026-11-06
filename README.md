# GitFit

Your daily fitness coach as an installable offline web app:

- **Today** — a habit hub with a daily completion meter: workout, cardio, mobility, steps, bodyweight, and nutrition habits in one place.
- **Workout** — the Starting Strength session (A/B), auto warm-up ramps, inline plate math, rest timer, auto-progression and deload.
- **Cardio** — a *coached* walk-to-run session: pick your level (20-min walk up to a 20-min run), hit start, and it counts you through each walk/run interval hands-free with beeps and vibration.
- **Mobility** — a *coached* stretch routine that shows each pose's name, an illustration, the side/hold and a timer, with a get-ready transition between poses; builds a daily streak.
- **History** — bodyweight (with goal line + trend), steps, and working-weight charts.

Everything is saved on your device.

## Custom pose images (optional)

The mobility screens use simple built-in figure drawings by default. To use your
own images instead, create a **`poses/`** folder in the repo and add an image
named after the pose (`.png`, `.jpg`, `.jpeg`, or `.webp`). The app uses your
image when it finds one and falls back to the drawing when it doesn't:

```
poses/seated-neck-rolls.png
poses/bound-angle-pose.png
poses/easy-pose-arm-stretch.png
poses/child-s-pose.png
poses/cat-cow-pose.png
poses/cobra-pose.png
poses/downward-dog.png
poses/front-thigh-stretch.png
poses/standing-forward-bend.png
```

Use images you have the rights to (your own photos, or ones you've licensed).
Square-ish images look best. After adding them, bump the `CACHE` in `sw.js`.

## Put it on GitHub Pages

1. Create a repo (e.g. `gitfit`) and upload every file here to the repo root:
   `index.html`, `manifest.webmanifest`, `sw.js`, and the `icon-*.png` files.
2. Repo **Settings → Pages**: Source = *Deploy from a branch*, branch `main`,
   folder `/ (root)`, **Save**.
3. Open the URL it gives you, e.g. `https://YOUR-USERNAME.github.io/gitfit/`.

All paths are relative, so it works at the domain root or in a `/gitfit/` subfolder.

## Add it to your home screen

- **iPhone (Safari):** open the URL → Share → **Add to Home Screen**.
- **Android (Chrome):** open the URL → menu → **Install app**.

Launches full-screen with its own icon and works offline after the first visit.
The coached sessions keep the screen awake while they run.

## Does my data save?

Yes — stored in the browser's `localStorage` for this site's address. On GitHub
Pages that address is stable and HTTPS, so it persists between visits and after you
add the app to your home screen. The app also asks to mark the storage persistent.

- Storage is **per address** — the Pages app, preview link, and downloaded file keep
  separate data. Use **Settings → Copy backup / Restore** to move between them.
- Treat **Copy backup** as your safety net before clearing site data or deleting the app.

## Updating later

Push the changed files and bump the `CACHE` name in `sw.js` (e.g. `gitfit-v6` →
`gitfit-v7`) so installed apps pick up the new version. Saved data is untouched.
