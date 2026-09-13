# How to Update App Store Links - Quick Guide

When your app is published on the App Store and Google Play, follow this guide to activate the download buttons.

## 📱 Step 1: Get Your App Links

### From Apple App Store
1. Go to [App Store Connect](https://appstoreconnect.apple.com)
2. Select your app (SnapStudio)
3. Click "App Information"
4. Find your app's App Store URL
5. It will look like: `https://apps.apple.com/app/snapstudio/id{NUMBERS}`

**Example:**
```
https://apps.apple.com/app/snapstudio/id1234567890
```

### From Google Play Store
1. Go to [Google Play Console](https://play.google.com/console)
2. Select your app (com.anonymous.snapstudio)
3. Click "Product details"
4. Find your public store link
5. It will look like: `https://play.google.com/store/apps/details?id=com.anonymous.snapstudio`

**Example:**
```
https://play.google.com/store/apps/details?id=com.anonymous.snapstudio
```

---

## ✏️ Step 2: Update the Website

### Option A: Edit index.html (Recommended)

1. Open `index.html` in your text editor
2. Find this section (search for "const config ="):

```javascript
const config = {
    appStore: {
        url: "", // ← Update this
        enabled: false, // ← Change to true
        comingSoon: true // ← Change to false
    },
    googlePlay: {
        url: "", // ← Update this
        enabled: false, // ← Change to true
        comingSoon: true // ← Change to false
    }
};
```

3. Replace with your actual URLs:

```javascript
const config = {
    appStore: {
        url: "https://apps.apple.com/app/snapstudio/id1234567890",
        enabled: true,
        comingSoon: false
    },
    googlePlay: {
        url: "https://play.google.com/store/apps/details?id=com.anonymous.snapstudio",
        enabled: true,
        comingSoon: false
    }
};
```

4. Save the file

### Option B: Update config.json (For Reference)

Open `config.json` and update:

```json
{
  "links": {
    "appStore": {
      "url": "https://apps.apple.com/app/snapstudio/id1234567890",
      "enabled": true,
      "comingSoon": false
    },
    "googlePlay": {
      "url": "https://play.google.com/store/apps/details?id=com.anonymous.snapstudio",
      "enabled": true,
      "comingSoon": false
    }
  }
}
```

---

## 🧪 Step 3: Test Locally

1. Open `index.html` in your browser (or run local server)
2. Scroll to the bottom "Download" section
3. Click the "App Store" button
4. It should open your App Store link
5. Click the "Google Play" button
6. It should open your Google Play link
7. Notice the "Coming Soon" badges are gone

---

## 🚀 Step 4: Deploy Changes

### If using Netlify/Vercel
```bash
git add index.html
git commit -m "Enable App Store and Google Play links"
git push origin main
```

**Your site will auto-deploy!** Changes live in 30 seconds.

### If using traditional hosting
1. Upload updated `index.html` via FTP
2. Clear browser cache (Ctrl+Shift+Delete)
3. Visit your domain to see changes

---

## ✅ Checklist

When updating, verify:

- [ ] App is published on App Store
- [ ] App is published on Google Play
- [ ] Both links work when clicked manually
- [ ] Buttons now show "App Store" and "Google Play" (no "Coming Soon")
- [ ] Local testing passes
- [ ] Changes deployed to production
- [ ] Visit live site and test buttons
- [ ] Clear browser cache if needed

---

## 🔗 How to Find Your Links

### Test Your URLs Before Updating

**For App Store:**
```
https://apps.apple.com/app/snapstudio/id{YOUR-ID}
```

**For Google Play:**
```
https://play.google.com/store/apps/details?id=com.anonymous.snapstudio
```

---

## 📞 Troubleshooting

### Links Don't Work
- **Verify URL is correct**: Copy-paste directly from App Store/Play Console
- **Check for typos**: URLs are case-sensitive
- **Ensure app is published**: Link only works if app is live

### Buttons Still Say "Coming Soon"
- **Check `enabled: true`** - Ensure you changed this
- **Check `comingSoon: false`** - Ensure you changed this
- **Clear browser cache** - Old version may be cached (Cmd+Shift+Delete)
- **Hard refresh** - Press Cmd+Shift+R (Mac) or Ctrl+Shift+F5 (Windows)

### Changes Not Live
- **Check if deployed**: Verify files uploaded to server
- **Wait for deployment**: Netlify/Vercel takes 30 seconds
- **Check file permissions**: File should be readable by web server
- **View page source**: Right-click → "View Page Source" to verify updates

---

## 🎯 Expected Behavior After Update

### Before (Coming Soon)
- Buttons disabled (grayed out)
- Badge shows "Coming Soon"
- Buttons don't redirect anywhere

### After (Live)
- Buttons fully enabled (bright colors)
- No "Coming Soon" badge
- Clicking redirects to App Store/Play Store
- Mobile users can install app immediately

---

## 📚 App Store ID Reference

### Find Your App Store ID
1. Visit your app on App Store
2. Look at the URL: `https://apps.apple.com/app/snapstudio/id**1234567890**`
3. The number after `id` is your App Store ID

### Find Your Package Name
1. Visit your app on Google Play
2. Look at the URL: `https://play.google.com/store/apps/details?id=**com.anonymous.snapstudio**`
3. The `id=` value is your package name

---

## 🔄 Regular Updates

As your app gets updated and re-published:

1. Links remain the same
2. No need to update website links again
3. Users will always get the latest version

Only update website if:
- App ID changes
- Package name changes
- Hosting platform changes

---

**Questions?** Refer to the main `README.md` or `DEPLOYMENT.md`

Last Updated: 2024
