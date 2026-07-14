# Indikator pH Antosianin

A single-page camera app that estimates pH from the color of an anthocyanin
indicator (e.g. red-cabbage extract) and reports whether a food/drink is
safe to consume. Pure static HTML/CSS/JS — no build step needed.

## Deploy to Vercel

**Option A — Vercel CLI (fastest)**
```bash
npm i -g vercel
cd ph-scanner
vercel --prod
```
Follow the prompts (link/create a project). Vercel auto-detects this as a
static site — no framework config needed.

**Option B — GitHub + Vercel dashboard**
1. Push this folder to a new GitHub repo.
2. Go to https://vercel.com/new and import the repo.
3. Leave all build settings as default (no build command, output = root).
4. Deploy.

## Notes
- Camera access requires HTTPS (Vercel provides this automatically) or
  `localhost` — it will not work over plain HTTP.
- On first load, the browser will prompt for camera permission.
- If camera access is denied or unavailable, use the "unggah foto dari
  galeri" link to upload a photo instead — analysis works the same way.
- The pH estimate is derived from the average hue/saturation of the center
  ~30% of the captured frame, mapped against a red-cabbage-style anthocyanin
  color reference chart. It's an approximation, not a lab measurement — for
  best results, photograph the indicator solution against a plain background
  in good, even lighting.

# bioplastic
