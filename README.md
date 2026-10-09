# DevOps Interview Quiz - deploy guide

Single file app: `index.html` (no build step, no dependencies to install).

## Free hosting options (pick one)

1. **Netlify Drop (fastest, 1 minute)**
   Go to https://app.netlify.com/drop, drag this whole `deploy` folder onto the page. You get a live https link.
2. **GitHub Pages**
   - Create a new public repo, upload `index.html`.
   - Settings -> Pages -> Source: "Deploy from a branch" -> `main` / root -> Save.
   - Site goes live at `https://<your-username>.github.io/<repo>/`.
3. **Cloudflare Pages**
   Dashboard -> Workers & Pages -> Create -> Pages -> Upload assets -> upload the folder.
4. **Vercel**
   `npm i -g vercel`, then run `vercel` inside this folder (or import the GitHub repo).

## What works after deploying

- Quiz (4 categories + Mixed), timer, streaks, confetti: yes
- Login (bottle) and signup (lamp) pages: yes, but accounts are stored in each visitor's own browser
- Leaderboard: top 10 for that browser/device only
- Owner-only Excel of all signups: NOT available (needs a backend, see below)

## To get a shared leaderboard + owner-only Excel

Add a free backend (Supabase or Firebase): real user accounts, a `signups` table only you can read, a shared `scores` table, and an export-to-Excel button visible only to your admin login.
