# OPLO.GOLD — Updates Summary

All changes since the initial GitHub deploy, condensed.

---

## What's NEW since last push

### 1. New hero video
- Replaced static visual with the action footage you sent (drawing, on-the-gun, security drill)
- Optimized to 5.2 MB, 38 seconds, loops seamlessly muted

### 2. NEW: Operator Capabilities section (Section 05)
- Five custom-drawn SVG weapon illustrations: **Handgun · AR/Carbine · Shotgun · NODs · Hands & Blade**
- Each card has hover effects (red glow, gold scanning line)
- Closing mantra strip: "The standard is fluency, not familiarity."

### 3. NEW: Houston Texas announcement bar
- Slim bar above the topbar showing: **📍 Houston · Texas | ★ TX DPS Licensed | ● USMC Veteran Owned | 📞 832-330-1321**
- Smart scroll: hides when you scroll down, returns at top

### 4. Mobile optimization
- Added breakpoints for 640px and 380px (proper phone sizes)
- Fixed contact form overflow issue (was extending past screen edge)
- Constrained all four full-bleed sections on mobile
- Gallery captions always visible on touch devices

### 5. Hero stats refreshed
- Now reads: II–IV DPS Levels · 9 Certifications · USMC Veteran Led · 100% Live Fire

---

## Files to push to GitHub

```
index.html                          ← UPDATED (1.5 MB)
assets/hero-clip.mp4                ← NEW (5.2 MB)
assets/hero-clip-poster.jpg         ← NEW (35 KB)
```

Everything else stays the same — no changes to:
- CNAME, .nojekyll, .gitignore, 404.html, README.md
- All other photos and videos in `assets/`

---

## Easiest way to push

### Option A — GitHub web upload (recommended)
1. Go to https://github.com/joseruddy77-web/oplo-gold-site
2. Click **Add file → Upload files**
3. From the unzipped folder I gave you, drag these THREE files onto the page:
   - `index.html`
   - `assets/hero-clip.mp4`
   - `assets/hero-clip-poster.jpg`
4. GitHub will detect the path; the assets go in the right folder automatically
5. Commit message: `Hero video + Capabilities + Houston announcement bar`
6. Click **Commit changes**
7. Wait ~60 seconds, refresh oplo.gold

### Option B — Replace the whole folder
Drag the **entire `oplo-gold-github` folder contents** onto the GitHub upload page. It will replace files and add new ones. Same commit message.

### Option C — Command line (if you used git)
```bash
cd path/to/oplo-gold-github
git add .
git commit -m "Hero video + Capabilities + Houston announcement bar"
git push
```

---

## After it's live

Test on phone AND desktop:
- [ ] New action video plays in hero
- [ ] Houston Texas bar shows at top, slides away on scroll
- [ ] Capabilities section has 5 cards with weapon icons
- [ ] Phone tap on announcement bar dials 832-330-1321
- [ ] Contact form fits inside the screen (no horizontal scroll)
- [ ] Gallery videos play when tapped on mobile

---

That's the whole package. Updated zip is at: `oplo-gold-website.zip`
