# Afya Desk — Clinic & Pharmacy System

A standalone build of your clinic/pharmacy app. Data is saved in the browser's
`localStorage` on whichever device/browser you use it on — it does not sync
between devices, and clearing browser data will erase it.

## Run it locally first (optional but recommended)

You'll need [Node.js](https://nodejs.org) installed (18+).

```
npm install
npm run dev
```

Open the URL it prints (usually http://localhost:5173) and confirm everything
works, then log in with the default passwords (`staff123` / `admin123`) and
change them immediately under Settings.

## Deploy to Vercel

**Option A — Vercel CLI (fastest, from your computer)**

1. Install the CLI once: `npm install -g vercel`
2. From this project folder, run: `vercel`
3. Follow the prompts (log in / create a Vercel account if you don't have one,
   accept the defaults — it auto-detects Vite).
4. When it finishes, it gives you a live URL. Run `vercel --prod` to promote
   it to your production URL.

**Option B — GitHub + Vercel dashboard (no CLI)**

1. Create a new GitHub repository and push this folder to it:
   ```
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin <your-repo-url>
   git push -u origin main
   ```
2. Go to https://vercel.com/new, sign in, and "Import" that GitHub repo.
3. Vercel auto-detects the Vite framework — leave the defaults and click Deploy.
4. You'll get a `.vercel.app` URL. You can attach a custom domain later from
   the project's Settings → Domains tab.

Either way, every time you push a change (or run `vercel --prod` again),
Vercel rebuilds and redeploys automatically.

## Important limitations of this local-storage version

- **Per-browser, per-device.** Data typed in on one computer/phone won't show
  up on another. If your two branches need to share one live view of stock,
  patients, sales, etc., you'd need a real backend database instead (I can
  help set that up — e.g. with Supabase or Postgres — when you're ready).
- **Clearing site data wipes it.** Browser privacy cleanups, "Clear browsing
  data", or a fresh browser profile will delete everything. Consider adding a
  manual export/backup routine, or moving to a database-backed version.
- **Passwords are a basic gate, not real security.** They're stored in the
  same local data, unencrypted. Fine for keeping casual access out at the
  counter; not a substitute for real auth if that ever matters more.
