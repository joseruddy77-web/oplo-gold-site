# OPLO.GOLD

The Gold Standard of Texas Security Training — official website for OPLO Training Group.

**Live site:** [https://oplo.gold](https://oplo.gold)

---

## Deployment to GitHub Pages

This site is a static HTML build — no build step, no dependencies. Just push and serve.

### First-time setup

1. **Create a new repository** on GitHub
   - Suggested name: `oplo-gold` (any name works)
   - Set it **Public** (required for GitHub Pages on the free tier)
   - Do NOT initialize with a README (we already have one)

2. **Push these files** to the repo. From this folder, in a terminal:

   ```bash
   git init
   git add .
   git commit -m "Initial commit — OPLO.GOLD launch"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/oplo-gold.git
   git push -u origin main
   ```

   Replace `YOUR-USERNAME` with your GitHub username.

3. **Enable GitHub Pages**
   - Go to your repo on GitHub
   - Click **Settings** → **Pages** (left sidebar)
   - Under **Build and deployment**:
     - **Source**: Deploy from a branch
     - **Branch**: `main` / root (`/`)
     - Click **Save**
   - Wait 1–2 minutes. You'll see a banner: "Your site is live at `https://YOUR-USERNAME.github.io/oplo-gold/`"

### Connect the oplo.gold domain

The `CNAME` file in this folder already tells GitHub to serve the site at **oplo.gold**.

You just need to point your domain at GitHub:

1. **At your domain registrar** (wherever you bought oplo.gold — GoDaddy, Namecheap, Google Domains, Cloudflare, etc.), open DNS settings.

2. **Add these records:**

   | Type  | Host | Value                  |
   |-------|------|------------------------|
   | A     | @    | 185.199.108.153        |
   | A     | @    | 185.199.109.153        |
   | A     | @    | 185.199.110.153        |
   | A     | @    | 185.199.111.153        |
   | CNAME | www  | YOUR-USERNAME.github.io |

   (Replace `YOUR-USERNAME` with your GitHub username — note the trailing `.github.io`, no repo name.)

3. **Back on GitHub** → Settings → Pages
   - Under **Custom domain**, you should see `oplo.gold` already populated (from the CNAME file)
   - Wait for the green check mark next to "DNS check successful" (5–30 minutes)
   - Once verified, **check the box** for **Enforce HTTPS**

4. **Done.** https://oplo.gold is live.

---

## Updating the site later

Edit any file locally, then:

```bash
git add .
git commit -m "Update content"
git push
```

GitHub auto-redeploys in about 60 seconds. No build step, no config — it just works.

---

## File structure

```
oplo-gold/
├── index.html         The entire website (logo embedded as base64)
├── CNAME              Points GitHub Pages to oplo.gold
├── .nojekyll          Disables Jekyll (we're pure HTML)
├── .gitignore         Standard ignore rules
├── README.md          This file
└── assets/
    ├── *.jpg          Gallery photos & video poster frames
    ├── *.mp4          Two looping training videos
    └── oplo-logo.png  Source logo (also embedded in index.html)
```

---

## Optional — Real-time form submissions

The contact form currently opens the visitor's email client pre-filled with their message. This works without any backend.

To get form submissions delivered straight to `oplotraininggroup@gmail.com` automatically:

1. Sign up at [Formspree](https://formspree.io) (free, 50 submissions/month)
2. Create a new form, copy your endpoint (e.g., `https://formspree.io/f/abc123`)
3. In `index.html`, find this line:
   ```html
   <form class="form-card" id="contactForm" novalidate>
   ```
   Change to:
   ```html
   <form class="form-card" id="contactForm" action="https://formspree.io/f/abc123" method="POST">
   ```
4. Find the JavaScript form handler (`form.addEventListener('submit', ...)`) and remove or comment out that whole block.
5. Commit and push.

---

## Contact

- **Phone:** 832-330-1321
- **Email:** oplotraininggroup@gmail.com
- **Instagram:** [@oplo.traininggroup](https://www.instagram.com/oplo.traininggroup)

---

© OPLO.GOLD · OPLO Training Group · Texas Private Security Training · The Gold Standard
