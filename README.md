# JV Video Lab — Cloudflare Pages package

This package contains the existing JV Video Lab interface with the FPS Studio
FFmpeg WebAssembly timestamp-scaling implementation.

## Deploy with Cloudflare Pages

1. Extract this ZIP.
2. In Cloudflare, open Workers & Pages → Create → Pages → Upload assets
   (or Direct Upload, depending on the dashboard version).
3. Upload the contents of this folder. `index.html` must be at the deployment root.
4. Deploy and open the assigned `*.pages.dev` URL.

Build settings for Git-based deployment:
- Framework preset: None
- Build command: leave empty
- Build output directory: `/` (the repository root)

## Important: Telegram verification CORS

The HTML calls:
`https://google-colabe-bot.onrender.com/verify/{uid}/{browser_token}`

The current backend source was configured for the Netlify origin
`https://jv60fps.netlify.app`. A Cloudflare Pages deployment has a different
origin (for example, `https://YOUR-PROJECT.pages.dev`). The backend must allow
the exact deployed Pages origin in its CORS configuration, or browser-based
Telegram verification may fail even though the HTML is deployed correctly.

Do not use `*` as an unrestricted production CORS policy. Add your actual
Pages/custom-domain origin to the backend's allowed origins.

## Notes

- This is a static HTML deployment; no build step is required.
- FFmpeg WebAssembly assets are loaded from jsDelivr at runtime.
- The app needs an internet connection for the CDN assets and verification API.
- Test Telegram verification and a short MP4 export after deployment.
- The original interface design is preserved; this package does not include
  a visual redesign.
