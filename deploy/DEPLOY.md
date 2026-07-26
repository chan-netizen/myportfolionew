# Deploy — Chanakya B H Portfolio

This folder is deploy-ready. `index.html` is a single static file (fonts + photo inlined).
Do the three steps below in order.

---

## 1. Fix the Web3Forms access key (do this FIRST)

The contact form currently has a placeholder key, so submissions won't send until you replace it.

1. Go to **https://web3forms.com** → enter your email → you'll get an **Access Key** (a UUID like `a1b2c3d4-...`). It's free, no account/password needed — the key arrives by email.
2. Open `index.html` in any text editor (or in Claude Code).
3. Find **`YOUR_WEB3FORMS_KEY`** (appears once) and replace it with your real key. Example:
   ```js
   access_key: '0f8e1c9a-1234-4c56-9abc-de1234567890',
   ```
4. Save. That's it — the "Connect with me" form now emails you every submission (name, email, phone, relocate choices).

> Tip: also replace the two **"Download CV"** links (`href="#"`) with a link to your CV PDF, and confirm the contact email `chanakyahemanth08@gmail.com` in the Offer section.

---

## 2. Push to GitHub

Using Claude Code (or a terminal) in this `deploy/` folder:

```bash
git init
git add index.html Professional_looking_headshot.jpeg
git commit -m "Chanakya B H portfolio"
git branch -M main
# create an empty repo on github.com first (e.g. chanakya-portfolio), then:
git remote add origin https://github.com/<your-username>/chanakya-portfolio.git
git push -u origin main
```

If you don't want the terminal: on **github.com** click **New repository** → drag `index.html` and `Professional_looking_headshot.jpeg` into the upload box → **Commit**.

---

## 3. Deploy to Vercel

**Option A — from GitHub (recommended):**
1. Go to **https://vercel.com** → **Add New… → Project**.
2. **Import** your `chanakya-portfolio` repo.
3. Framework preset: **Other** (it's static — no build step). Leave build/output settings empty.
4. **Deploy**. Your site is live at `https://chanakya-portfolio.vercel.app` (rename in project settings).

**Option B — drag & drop (no GitHub):**
1. Go to **https://vercel.com** → **Add New… → Project → Deploy** (or vercel.com/new).
2. Drag this whole `deploy/` folder in. Deploy.

> Every future `git push` to `main` auto-redeploys (Option A). For drag-and-drop, just re-upload.

---

## Files in this folder
- `index.html` — the complete site (open it locally to preview).
- `Professional_looking_headshot.jpeg` — hero photo (must sit next to index.html).

## Notes
- Company/school logos load live from Google's favicon API — they need internet (fine on Vercel).
- No build tools, npm, or backend required anywhere.
