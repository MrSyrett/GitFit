# GitFit

A Starting Strength trainer: A/B workouts, auto warm-up ramps, a visual plate
calculator, a rest timer, a bodyweight log, and progress saved on your device.
Runs as an installable offline web app.

## Put it on GitHub Pages

1. Create a new repository (e.g. `gitfit`) and upload every file in this folder
   to the repo root: `index.html`, `manifest.webmanifest`, `sw.js`, and the
   `icon-*.png` files.
2. In the repo: **Settings → Pages → Build and deployment**. Set **Source** to
   *Deploy from a branch*, pick your branch (`main`) and the `/ (root)` folder,
   then **Save**.
3. Wait a minute, then open the URL it shows, e.g.
   `https://YOUR-USERNAME.github.io/gitfit/`.

All paths are relative, so it works whether the app is at the domain root or in a
`/gitfit/` subfolder.

## Add it to your home screen

- **iPhone (Safari):** open the Pages URL → Share → **Add to Home Screen**.
- **Android (Chrome):** open the URL → menu → **Install app** / **Add to Home screen**.

It launches full-screen with its own icon, and the service worker lets it open
even with no connection after the first visit.

## Does my data save?

Yes. Your log is stored in the browser's `localStorage` for this site's address.
On GitHub Pages that address is stable (and served over HTTPS), so it persists
between visits and after you add the app to your home screen. The app also asks
the browser to mark the storage **persistent** so it isn't cleared under storage
pressure.

Two things to know:
- Storage is **per address**. The data on your GitHub Pages app is separate from
  the preview link and from the downloadable file. Use **Settings → Copy backup**
  to export, and **Restore** to import, when moving between them.
- Treat **Copy backup** as your real safety net. If you ever clear the browser's
  site data or delete the home-screen app, restore from a backup.

## Updating later

Push a changed `index.html` and bump the `CACHE` name in `sw.js` (e.g.
`gitfit-v3` → `gitfit-v4`) so the new version replaces the cached one. Your saved
data is untouched by updates.
