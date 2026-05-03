# 3DUpito — GitHub Pages Setup Guide

## What You're Building

A free hosted web app at `https://yourusername.github.io/3dupito`  
Installs as a home screen app on iPhone via Safari.  
Works fully offline once installed.

---

## File Structure

Your repo should look like this:

```
3dupito/
├── index.html          ← Main app
├── manifest.json       ← PWA manifest
├── sw.js               ← Service worker (offline support)
└── icons/
    ├── icon-32.png
    ├── icon-192.png
    ├── icon-512.png
    └── apple-touch-icon.png
```

---

## Step 1 — Create a GitHub Account

If you don't have one already:
1. Go to **github.com**
2. Click **Sign up**
3. Choose a username (this becomes part of your URL)
4. Verify email

---

## Step 2 — Create the Repository

1. Click the **+** icon top right → **New repository**
2. Repository name: `3dupito` (lowercase, no spaces)
3. Set to **Public** ← Required for free GitHub Pages
4. Check **"Add a README file"**
5. Click **Create repository**

---

## Step 3 — Upload Your Files

### Option A — GitHub Website (Easiest, no coding required)

1. Open your new repo on github.com
2. Click **Add file → Upload files**
3. Drag and drop: `index.html`, `manifest.json`, `sw.js`
4. Click **Commit changes**
5. Now create the icons folder:
   - Click **Add file → Upload files** again
   - Before dropping files, type `icons/` in the file path box at the top
   - Drop all 4 icon PNG files
   - Click **Commit changes**

### Option B — Git Command Line (If you have Git installed)

```bash
# Clone your repo
git clone https://github.com/YOURUSERNAME/3dupito.git
cd 3dupito

# Copy your files in (adjust path to where you saved them)
cp /path/to/index.html .
cp /path/to/manifest.json .
cp /path/to/sw.js .
mkdir icons
cp /path/to/icons/*.png icons/

# Push to GitHub
git add .
git commit -m "Initial 3DUpito build manual"
git push
```

---

## Step 4 — Enable GitHub Pages

1. In your repo, click **Settings** (top tab)
2. Scroll down to **Pages** in the left sidebar
3. Under **Source**, select **Deploy from a branch**
4. Branch: **main** · Folder: **/ (root)**
5. Click **Save**
6. Wait 1–2 minutes
7. A banner will appear: *"Your site is live at https://YOURUSERNAME.github.io/3dupito"*

---

## Step 5 — Install on iPhone

1. Open **Safari** on your iPhone (must be Safari, not Chrome)
2. Navigate to `https://YOURUSERNAME.github.io/3dupito`
3. Wait for the page to fully load
4. Tap the **Share button** (box with arrow pointing up, bottom center)
5. Scroll down and tap **"Add to Home Screen"**
6. Name it `3DUpito` → tap **Add**
7. The app icon appears on your home screen

> **First time only:** Open the app from home screen while on WiFi.  
> This caches everything for offline use. After that it works anywhere.

---

## Step 6 — Updating the App

Whenever you want to update the manual:

**Via website:**
1. Go to your repo on github.com
2. Click the file you want to edit → pencil icon
3. Make changes → **Commit changes**
4. Changes go live in ~30 seconds

**Via Git:**
```bash
git add .
git commit -m "Update tuning notes"
git push
```

The app auto-updates next time it's opened with an internet connection.

---

## Troubleshooting

**"Page not found" after enabling Pages:**  
Wait 2–3 minutes and hard refresh. GitHub Pages takes a moment to deploy.

**iOS hint not showing:**  
Must open in Safari specifically. Chrome on iOS does not support PWA install.

**App not updating after changes:**  
Open app, pull down to refresh. If still old, delete app from home screen and reinstall.

**Service worker not registering:**  
Must be served over HTTPS. GitHub Pages does this automatically — no action needed.

**Icons not showing on home screen:**  
Confirm `icons/` folder is in the root of the repo and all 4 PNG files are uploaded. Path in manifest.json must match exactly.

---

## Your URLs

| Resource | URL |
|---|---|
| App | `https://YOURUSERNAME.github.io/3dupito` |
| Repo | `https://github.com/YOURUSERNAME/3dupito` |
| Settings | `https://github.com/YOURUSERNAME/3dupito/settings/pages` |

---

## Optional — Custom Domain

If you ever want `3dupito.com` instead of the github.io URL:

1. Buy domain from Namecheap, Cloudflare, etc.
2. In repo Settings → Pages → Custom domain → enter your domain
3. Add a CNAME record in your domain DNS pointing to `YOURUSERNAME.github.io`
4. GitHub handles SSL automatically

---

*Built for the 3DUpito — MantaDynamics Manta V1 in Bambu Labs PLA-CF Red*  
*AOS Supernova 2807 1400KV · Spektrum Avian 45A · AR631T+ · 6S*
