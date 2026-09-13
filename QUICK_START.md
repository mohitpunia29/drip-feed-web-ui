# SnapStudio Landing Page - Quick Start Guide

Get your landing page live in 5 minutes! 🚀

---

## 1️⃣ Test Locally (1 minute)

### Option A: Browser (Simplest)
```bash
# Open file directly
open /Users/mohitpunia/Services/drip-feed-app-website-UI/index.html

# Or on Windows
start /Users/mohitpunia/Services/drip-feed-app-website-UI/index.html
```

### Option B: Local Server
```bash
# Python 3
cd /Users/mohitpunia/Services/drip-feed-app-website-UI
python -m http.server 8000
# Visit: http://localhost:8000

# Or Node.js
npx http-server
# Visit: http://localhost:8080
```

---

## 2️⃣ Deploy to Web (2 minutes) - Choose One

### 🏆 Easiest: Netlify Drag & Drop

1. Go to [app.netlify.com](https://app.netlify.com)
2. Sign up (free)
3. Drag and drop the `drip-feed-app-website-UI` folder
4. ✅ **Live instantly!** You get a URL like `https://xxxxx.netlify.app`

Then add custom domain:
1. In Netlify dashboard: "Domain management"
2. Add your custom domain (e.g., snapstudio.app)
3. Follow DNS instructions

---

### Quick: GitHub Pages

```bash
# Create repo on github.com first, then:
cd /Users/mohitpunia/Services/drip-feed-app-website-UI
git init
git add .
git commit -m "SnapStudio landing page"
git branch -M main
git remote add origin https://github.com/YOU/snapstudio-landing.git
git push -u origin main

# Go to Repo → Settings → Pages → Select main branch
# ✅ Live at: https://you.github.io/snapstudio-landing
```

---

### Quick: Vercel

1. Push to GitHub (see GitHub Pages steps above)
2. Go to [vercel.com](https://vercel.com)
3. Click "Add New" → "Project"
4. Import your GitHub repo
5. ✅ **Live instantly!**

---

## 3️⃣ Add App Store Links (1 minute)

When your app is published:

1. Open `index.html` in any text editor
2. Find `const config = {` (around line 390)
3. Update these fields:

```javascript
appStore: {
    url: "https://apps.apple.com/app/snapstudio/id1234567890", // ← Your URL
    enabled: true, // ← Change from false
    comingSoon: false // ← Change from true
},
googlePlay: {
    url: "https://play.google.com/store/apps/details?id=com.anonymous.snapstudio", // ← Your URL
    enabled: true, // ← Change from false
    comingSoon: false // ← Change from true
}
```

4. Save
5. If using Git: `git add . && git commit -m "Add store links" && git push`
6. ✅ **Done!** Auto-deployed in 30 seconds

---

## 📁 File Guide

```
📦 drip-feed-app-website-UI
├── 📄 index.html              ← Main landing page (edit links here!)
├── 📄 config.json             ← Configuration reference
├── 📚 README.md              ← Full documentation
├── 📚 QUICK_START.md         ← You are here!
├── 📚 DEPLOYMENT.md          ← Detailed deployment guide
├── 📚 UPDATE_LINKS.md        ← How to update store links
├── 📄 .gitignore             ← Git ignore file
└── 📁 assets/                ← Images & favicon
```

---

## 🎨 Customization (Optional)

### Change Colors
Edit the `:root` section in `index.html` (around line 27):
```css
--accent-hover: #BEE622;  /* Change neon yellow to your color */
--bg: #0A0A0C;           /* Change dark background */
```

### Change Text/Content
Edit directly in the HTML:
- `<h1>` tags for headlines
- `<p>` tags for descriptions
- `.feature-title` for feature names

### Add Screenshots
Replace the placeholder divs in the "Experience SnapStudio" section:
```html
<div class="screenshot">
    <img src="./assets/screenshots/screen1.png" style="width: 100%; height: 100%; object-fit: cover;">
</div>
```

---

## ✅ Launch Checklist

- [ ] Site loads and looks good locally
- [ ] Deployed to web (Netlify/Vercel/GitHub Pages)
- [ ] Custom domain configured
- [ ] Store links added (when app launches)
- [ ] All buttons tested
- [ ] Mobile responsive verified
- [ ] Shared on social media
- [ ] Added to app's website link

---

## 🔗 Important URLs

Keep these bookmarked:

- **Netlify**: https://app.netlify.com
- **Vercel**: https://vercel.com
- **GitHub Pages**: https://pages.github.com
- **Domain Registrar**: (GoDaddy, Namecheap, etc.)
- **App Store Connect**: https://appstoreconnect.apple.com
- **Google Play Console**: https://play.google.com/console

---

## 📊 What You Get

✅ Beautiful, modern landing page
✅ Dark theme matching your app
✅ Fully responsive (mobile/tablet/desktop)
✅ Fast load times (~1 second)
✅ SEO optimized
✅ No build process needed
✅ Configurable store links
✅ Ready for custom domain

---

## 🚀 Next Steps

1. **Test** → Open `index.html` in browser
2. **Deploy** → Push to Netlify/Vercel/GitHub
3. **Configure** → Add domain name
4. **Update Links** → When app launches
5. **Share** → Post on social media
6. **Monitor** → Add Google Analytics (optional)

---

## ❓ Help

- **Deployment issues?** See `DEPLOYMENT.md`
- **Updating links?** See `UPDATE_LINKS.md`
- **Customization help?** See `README.md`
- **Local testing issues?** Try different browser or clear cache

---

## 🎯 Common Tasks

### "How do I change the title?"
Edit `<title>` and `<h1>` in `index.html`

### "How do I use my own logo?"
Replace emoji (✨) with image: `<img src="logo.png" alt="Logo">`

### "How do I add more features?"
Duplicate a `.feature-card` div and edit content

### "How do I update the site after launch?"
Edit `index.html`, save, push to Git (auto-deploys)

### "How long until my domain works?"
DNS: 5 minutes to 24 hours (usually 5-30 minutes)

---

## 📈 Performance Tips

- ✅ Already optimized for speed
- ✅ Already mobile responsive
- ✅ Already has dark theme
- ✅ Consider adding Google Analytics later
- ✅ Monitor with PageSpeed Insights

---

**Ready to launch?** Go to Step 1 above! 🚀

Last Updated: 2024
