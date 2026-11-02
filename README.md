# JV Video Lab — Cloudflare Pages

Deploy the **contents** of this folder to Cloudflare Pages (not the folder itself).

Required files:
- `index.html`
- `ffmpeg/worker.js`
- `ffmpeg/const.js`
- `ffmpeg/errors.js`

The FFmpeg 0.12.15 ESM class worker is served from the same origin at `/ffmpeg/worker.js`; its relative ESM imports resolve to `/ffmpeg/const.js` and `/ffmpeg/errors.js`. The FFmpeg core JS/WASM are still fetched from jsDelivr at runtime.

After deployment, verify these URLs load in a browser:
- `https://YOUR-PAGES-DOMAIN/ffmpeg/worker.js`
- `https://YOUR-PAGES-DOMAIN/ffmpeg/const.js`
- `https://YOUR-PAGES-DOMAIN/ffmpeg/errors.js`

If you previously deployed the earlier ZIP, replace the entire deployment with this ZIP. Clear the site's cache or hard-refresh after deployment.
