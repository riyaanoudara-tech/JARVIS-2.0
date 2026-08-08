# AEGIS (Gemini version) — Deploy & Test

Files in this project:
- `index.html` — the app itself.
- `api/chat.js` — server function that calls Google's Gemini API, keeping your key private.
- `package.json` — lets Vercel recognize this as a Node project.

## 1. Get a Gemini API key

1. Go to https://aistudio.google.com and sign in with a **personal** Google account (school/work accounts often block this).
2. Click **Get API key** → **Create API key** → **Create API key in new project**.
3. Copy the key (starts with `AIza...`). You can view it again later on the same page if needed.

No billing or credit card needed for the free tier.

## 2. Create a new GitHub repo

1. Go to https://github.com → **New repository** → give it any name → Create.
2. On the repo page, click **Add file → Upload files**.
3. On your computer, unzip this project if it's zipped, then select and drag in **all of it** — `index.html`, `package.json`, and the whole `api` folder together — so the folder structure is preserved.
4. Scroll down, click **Commit changes**.
5. Refresh the page and confirm you see `index.html`, `package.json`, and an `api` folder containing `chat.js`.

## 3. Deploy on Vercel

1. Go to https://vercel.com → log in with **Continue with GitHub** (authorize when asked).
2. Click **Add New → Project**.
3. Find your new repo → **Import**.
4. Leave all settings on default → **Deploy**. Wait ~30–60 seconds.

## 4. Add your API key

1. Open the deployed project → **Settings**.
2. Find **Environment Variables** (use the "Find" search box at the top of Settings if the sidebar doesn't show it directly).
3. Add:
   - **Key**: `GEMINI_API_KEY`
   - **Value**: the `AIza...` key you copied earlier
4. Leave Production/Preview/Development all checked → **Save**.

## 5. Redeploy

Environment variables only apply after a redeploy:
1. Go to the **Deployments** tab.
2. Click the **⋯** menu on the latest (top) deployment → **Redeploy**.

## 6. Test it

Open the live URL shown at the top of the project (something like `https://your-project.vercel.app`) on any device — try the chat, add a task by typing or by voice, check the Overview tab.

## Reusing this same Gemini key elsewhere

Yes — the same `AIza...` key works in any other project too. Just add it as an environment variable named `GEMINI_API_KEY` (or whatever name that project's code expects) in that project's Vercel settings. No need to create a new key each time unless you want separate usage tracking per project.

## Iterating further

Bring changes back to this chat any time — new features, a shared database across devices, styling tweaks — and I'll update these same files for your next redeploy.
