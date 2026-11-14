# VYRA Studio V4 — Visual Prototype

This is a **static, multi-page design prototype** built with HTML/CSS/JS. It contains:

- `index.html` — cinematic landing page
- `login.html` — Sign Up / Log In **browser-only demo**
- `studio.html` — prompt page, reference picker, optional settings, animated loading
- `result.html` — single concept preview, revision history, downloadable text brief
- `style.css`, `app.js` — design and interactions

## Try it
Open `index.html` in your browser, select Get Started, choose Sign Up, and create a **throwaway demo username/password**. Enter a prompt and generate. After the simulated loading screen, you will see a concept summary (not a video).

## IMPORTANT — Security and AI

This version has **no secure authentication**. Demo passwords are stored in browser localStorage as plain text, so **do not use real passwords**. Username uniqueness applies only to the same browser's local demo data, not globally. The demo session lasts until the tab/browser session ends or the user logs out. There is no real user database, admin dashboard, Claude API, AI generation, voiceover, media rendering, or MP4 download. The reference file picker only displays a filename; no upload happens. The loading is simulated and clearly labeled. Do not advertise this as a live AI service or enable public signups until a secure backend and abuse protection are implemented.

## Cloudflare Pages
Upload the *contents* of this folder to the root of the existing GitHub repository, preserving filenames. Use Cloudflare Pages Git integration with no framework preset, no build command, and output directory `/`. A commit to `main` triggers deployment. For a safe preview, use a separate branch/preview deployment before replacing production. **Do not delete your previous `functions/` folder unless you deliberately migrate the backend.** The V4 demo doesn't call that backend.

## Next production work
Build real authentication using a trusted auth provider or a secure backend with hashed passwords, email verification and password reset; a database enforcing unique usernames; private object storage and media processing; Claude API server-side for planning; a separate video/image generation provider and rendering pipeline; async job status; revision history; an admin panel with role-based access and privacy safeguards. Store all API keys only in Cloudflare secrets.


V4.1 FIX: Route detection supports Cloudflare Pages clean URLs (`/login`, `/studio`, `/result`) as well as `.html` file paths. Previously the login JavaScript was not initialized on clean URLs, so form fields were submitted in the URL. Login form now also defaults to POST as a safety fallback. Demo only, not real authentication.
