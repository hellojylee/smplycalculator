
# SMPLY Pricing Calculator (Static Site)

Single-file static app (HTML/CSS/JS). You can deploy it to any static host.

## Quick Preview
Open `index.html` directly in a browser.

## Deploy Options

### 1) GitHub Pages
1. Create a new repo and add `index.html` at the root.
2. Push to `main` branch.
3. In **Settings ▸ Pages**, set **Branch: `main` / `/root`**.
4. Wait for the site to build, then open the provided URL.

### 2) Vercel (recommended)
1. `vercel` (CLI) or import the repo in vercel.com.
2. Framework Preset: **Other** (static).
3. Output directory: **/** (root).

### 3) Netlify
1. Drag-and-drop the folder in https://app.netlify.com/drop or connect a repo.
2. Build command: **None**.
3. Publish directory: **/** (root).

### 4) Cloudflare Pages
1. Create a project, connect to repository or upload the folder.
2. Build command: **None**; Output directory: **/**.

### 5) S3 + CloudFront
1. Create an **S3 static website** bucket.
2. Upload `index.html` with `Content-Type: text/html; charset=utf-8`.
3. Enable static hosting and (optionally) front with **CloudFront**.

### 6) Docker + Nginx
```
docker run -d --name smply-pricing -p 8080:80 \
  -v $(pwd):/usr/share/nginx/html:ro nginx:alpine
```
Then open http://localhost:8080

## Notes
- This app is entirely client-side and needs **no backend**.
- Local state is stored in `localStorage` under `pricingCalculatorState`.
- You can customize pricing logic inside `calculatePrices()`.
