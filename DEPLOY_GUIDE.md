# KTX Bags – Deployment Guide
**GitHub Pages + GoDaddy Custom Domain**

---

## Step 1 — Create a GitHub Account (if you don't have one)
Go to https://github.com and sign up. It's free.

---

## Step 2 — Create a New GitHub Repository

1. Click the **+** icon (top-right) → **New repository**
2. Repository name: `ktxbags.com` (or any name you like)
3. Set it to **Public**
4. Click **Create repository**

---

## Step 3 — Upload Your Website Files

You have two files to upload:
- `index.html`
- `CNAME`

**Option A — via GitHub website (easiest):**
1. Inside your new repo, click **Add file → Upload files**
2. Drag and drop both `index.html` and `CNAME`
3. Click **Commit changes**

**Option B — via Git (if you know the terminal):**
```bash
git init
git add index.html CNAME
git commit -m "Initial website"
git remote add origin https://github.com/YOUR_USERNAME/ktxbags.com.git
git push -u origin main
```

---

## Step 4 — Enable GitHub Pages

1. In your repo, go to **Settings** (top tab)
2. Scroll down to **Pages** in the left sidebar
3. Under **Source**, select **Deploy from a branch**
4. Branch: **main**, folder: **/ (root)**
5. Click **Save**

GitHub will give you a URL like `https://yourusername.github.io/ktxbags.com`

---

## Step 5 — Set Custom Domain in GitHub Pages

1. Still in **Settings → Pages**
2. Under **Custom domain**, type: `ktxbags.com`
3. Click **Save**
4. Check **Enforce HTTPS** (after DNS propagates — may take up to 24 hrs)

---

## Step 6 — Point GoDaddy DNS to GitHub Pages

1. Log in to **GoDaddy** → go to your domain **ktxbags.com**
2. Click **DNS** or **Manage DNS**
3. **Delete** any existing A records pointing to GoDaddy parking pages
4. **Add these 4 A records** (GitHub's IPs):

| Type | Name | Value | TTL |
|------|------|-------|-----|
| A | @ | 185.199.108.153 | 600 |
| A | @ | 185.199.109.153 | 600 |
| A | @ | 185.199.110.153 | 600 |
| A | @ | 185.199.111.153 | 600 |

5. **Add a CNAME record** for www:

| Type | Name | Value | TTL |
|------|------|-------|-----|
| CNAME | www | YOUR_GITHUB_USERNAME.github.io | 600 |

6. Click **Save**

DNS propagation takes **1–24 hours**. After that, `ktxbags.com` will load your website.

---

## Step 7 — Set Up the Contact Form (Formspree)

The quote form on the website uses Formspree (free tier: 50 submissions/month).

1. Go to https://formspree.io and sign up with **bagktx@gmail.com**
2. Click **New Form** → name it "KTX Bags Quote Form"
3. Copy your **Form ID** (looks like `xpzgkwnd`)
4. Open `index.html`, find this line:
   ```
   action="https://formspree.io/f/YOUR_FORM_ID"
   ```
5. Replace `YOUR_FORM_ID` with your actual ID
6. Re-upload the updated `index.html` to GitHub

---

## Step 8 — Done! 🎉

Your website is live at **ktxbags.com**

---

## To Update the Website Later

1. Edit `index.html` locally
2. Go to your GitHub repo → click `index.html` → click the **pencil (edit) icon**
3. Paste your updated code → **Commit changes**
4. Changes go live in ~30 seconds

---

## Support
For any questions, raise a GitHub issue or contact the developer.
