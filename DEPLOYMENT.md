# SnapStudio Landing Page - Deployment Guide

Complete step-by-step instructions for deploying your landing page to production.

## 🎯 Deployment Options

### Quick Comparison

| Platform | Cost | Setup Time | Custom Domain | Ease | Best For |
|----------|------|-----------|---|------|----------|
| **Netlify** | Free | 2 mins | Yes | ⭐⭐⭐⭐⭐ | Easiest option |
| **Vercel** | Free | 2 mins | Yes | ⭐⭐⭐⭐⭐ | Next.js/Frontend teams |
| **GitHub Pages** | Free | 5 mins | Yes | ⭐⭐⭐⭐ | GitHub-native |
| **Surge** | Free/Paid | 3 mins | Yes | ⭐⭐⭐⭐ | Quick deploys |
| **AWS S3** | Paid | 10 mins | Yes | ⭐⭐⭐ | Enterprise scale |
| **Traditional Hosting** | Varies | 15 mins | Yes | ⭐⭐⭐ | Full control |

---

## 🚀 Option 1: Netlify (RECOMMENDED)

### Best for: Absolute simplicity, perfect for small teams

#### Step 1: Prepare Files
```bash
cd /Users/mohitpunia/Services/drip-feed-app-website-UI
# Ensure you have: index.html, config.json, README.md
```

#### Step 2: Create Netlify Account
1. Go to [netlify.com](https://www.netlify.com)
2. Click "Sign up"
3. Choose "GitHub", "GitLab", or "Email"
4. Complete signup

#### Step 3: Deploy Site
**Method A: Drag & Drop (Fastest)**
1. Go to [app.netlify.com](https://app.netlify.com)
2. Drag and drop the `drip-feed-app-website-UI` folder
3. Done! Site is live instantly

**Method B: Git Integration (Recommended)**
1. Push your folder to GitHub
2. In Netlify: "Add new site" → "Import an existing project"
3. Connect your GitHub account
4. Select repository and main branch
5. Click "Deploy site"

#### Step 4: Configure Custom Domain
1. In Netlify dashboard: "Domain management"
2. Click "Add custom domain"
3. Enter your domain (e.g., `snapstudio.app`)
4. Follow DNS setup instructions from your domain registrar

#### Step 5: Enable HTTPS
- Netlify auto-enables HTTPS with free SSL certificate
- Takes ~1 minute to activate

#### URLs After Deployment
- Default: `https://xxxx.netlify.app`
- Custom: `https://snapstudio.app` (if configured)

---

## 🚀 Option 2: Vercel

### Best for: Teams using modern frameworks, Next.js

#### Step 1: Push to GitHub
```bash
cd /Users/mohitpunia/Services/drip-feed-app-website-UI
git init
git add .
git commit -m "Add SnapStudio landing page"
git remote add origin https://github.com/YOUR-USERNAME/snapstudio-landing
git push -u origin main
```

#### Step 2: Deploy on Vercel
1. Go to [vercel.com](https://vercel.com)
2. Click "New Project"
3. Connect GitHub account
4. Select your repository
5. Click "Import"
6. Settings are pre-configured
7. Click "Deploy"

#### Step 3: Add Custom Domain
1. In Vercel dashboard: "Domains"
2. Add your domain
3. Update DNS records at your registrar

#### URLs After Deployment
- Default: `https://snapstudio-landing.vercel.app`
- Custom: `https://snapstudio.app`

---

## 🚀 Option 3: GitHub Pages

### Best for: Developers who want version control + hosting

#### Step 1: Create GitHub Repository
```bash
# Go to github.com and create new repo: "snapstudio-landing"
# Clone it locally
git clone https://github.com/YOUR-USERNAME/snapstudio-landing.git
cd snapstudio-landing

# Copy your files
cp -r /Users/mohitpunia/Services/drip-feed-app-website-UI/* .

# Commit and push
git add .
git commit -m "Initial commit: SnapStudio landing page"
git push origin main
```

#### Step 2: Enable GitHub Pages
1. Go to repository Settings
2. Scroll to "Pages" section
3. Select "Deploy from a branch"
4. Choose "main" branch
5. Click "Save"

#### Step 3: Wait for Deployment
- Takes 1-2 minutes
- Site appears at: `https://YOUR-USERNAME.github.io/snapstudio-landing`

#### Step 4: Add Custom Domain
1. In Settings → Pages
2. Enter your domain in "Custom domain"
3. Add DNS records at your registrar:
   ```
   A Record: 185.199.108.153
   A Record: 185.199.109.153
   A Record: 185.199.110.153
   A Record: 185.199.111.153
   
   CNAME: YOUR-USERNAME.github.io
   ```

---

## 🚀 Option 4: AWS S3 + CloudFront

### Best for: Enterprise, high-traffic sites, full control

#### Step 1: Create S3 Bucket
1. Go to [AWS Console](https://console.aws.amazon.com)
2. Navigate to S3
3. "Create bucket"
4. Name: `snapstudio-landing`
5. Uncheck "Block Public Access"
6. Create bucket

#### Step 2: Upload Files
1. Open your bucket
2. Click "Upload"
3. Drag and drop all files from `drip-feed-app-website-UI`
4. Click "Upload"

#### Step 3: Enable Static Website Hosting
1. Go to bucket "Properties"
2. Scroll to "Static website hosting"
3. Click "Edit"
4. Enable it
5. Index: `index.html`
6. Error page: `index.html`
7. Save

#### Step 4: Set Bucket Policy
1. Go to "Permissions" tab
2. "Bucket policy"
3. Add policy:
```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::snapstudio-landing/*"
        }
    ]
}
```

#### Step 5: Set Up CloudFront (CDN)
1. Go to CloudFront
2. "Create distribution"
3. Origin domain: your S3 endpoint
4. Enable HTTPS
5. Add your domain
6. Create distribution

#### Step 6: Add Custom Domain
1. Update DNS records to CloudFront distribution URL
2. Configure SSL certificate in AWS Certificate Manager

#### URLs After Deployment
- S3 direct: `http://snapstudio-landing.s3.amazonaws.com`
- CloudFront: `https://d111111abcdef8.cloudfront.net`
- Custom domain: `https://snapstudio.app`

---

## 🚀 Option 5: Traditional Web Hosting (GoDaddy, Bluehost, etc.)

### Best for: Budget-conscious, non-technical users

#### Step 1: Upload Files
1. Log into your hosting control panel (cPanel, Plesk, etc.)
2. Use File Manager or FTP
3. Navigate to `public_html` folder
4. Upload all files from `drip-feed-app-website-UI`

#### Step 2: Set Index File
1. In control panel: "Index Manager"
2. Ensure `index.html` is listed as index file
3. Save

#### Step 3: Configure Custom Domain
1. Point your domain to your hosting provider's nameservers
2. Or update A record to your hosting IP
3. Wait for DNS propagation (5-24 hours)

#### Step 4: Enable HTTPS
1. Most providers offer free SSL (Let's Encrypt)
2. In control panel: "SSL/TLS"
3. Install certificate
4. Enable auto-redirect to HTTPS

#### URLs After Deployment
- Your domain: `https://snapstudio.app`

---

## 📋 Pre-Deployment Checklist

Before deploying, ensure:

- [ ] **Links configured**: App Store and Google Play URLs added to `index.html`
- [ ] **Images optimized**: All images are compressed
- [ ] **Tested locally**: Verified all links work
- [ ] **Mobile tested**: Checked on phone/tablet
- [ ] **Meta tags**: Title and description are correct
- [ ] **Favicon**: favicon.png exists
- [ ] **SEO ready**: Keywords in title and description
- [ ] **Social sharing**: Open Graph tags configured
- [ ] **Analytics**: Add Google Analytics (optional)

---

## 🔗 Setting Up Google Analytics (Optional)

### Add Tracking Code

1. Go to [google.com/analytics](https://analytics.google.com)
2. Create new property
3. Copy tracking ID
4. Add to `index.html` before `</head>`:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

Replace `GA_MEASUREMENT_ID` with your tracking ID.

---

## 🌐 Domain Registration

### Where to Buy Domain

- **Affordable**: Namecheap, GoDaddy, HostGator ($5-15/year)
- **Premium**: Google Domains, Bluehost
- **ICANN**: Any accredited registrar

### Popular Domain Options
- snapstudio.app
- snapstudio.co
- getsnap.studio
- snapstudio.io
- mysnapstudio.com

---

## 🔄 DNS Configuration

### After Purchasing Domain

You'll typically update these:

**For Netlify/Vercel:**
```
CNAME: your-netlify-domain.netlify.app
```

**For GitHub Pages:**
```
CNAME: username.github.io
A Records: 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
```

**For Traditional Hosting:**
```
A Record: Your hosting IP address
Or use Nameservers provided by host
```

---

## ✅ Post-Deployment Steps

### Verify Deployment
1. Visit your domain in browser
2. Check page loads correctly
3. Test all buttons and links
4. Verify responsive on mobile
5. Test App Store button redirects

### Test Links
```bash
# Test if domain resolves
ping snapstudio.app

# Check SSL certificate
curl -I https://snapstudio.app
```

### Monitor Performance
- Set up Google Analytics
- Monitor in Chrome DevTools
- Check Google PageSpeed Insights
- Test on mobile devices

---

## 🐛 Troubleshooting

### Site Not Loading
- Check DNS propagation: [whatsmydns.net](https://whatsmydns.net)
- Verify files uploaded correctly
- Check index.html exists
- View browser console for errors

### Slow Performance
- Optimize images
- Enable gzip compression
- Use CDN (CloudFront, Cloudflare)
- Minimize JavaScript

### SSL Certificate Issues
- Wait 24-48 hours for propagation
- Use [ssl-checker.com](https://www.ssl-checker.com) to verify
- Contact hosting provider

### 404 Errors
- Ensure all file names match exactly
- Check file paths in HTML (case-sensitive on Linux)
- Verify index.html is in root directory

---

## 📚 Additional Resources

- **Netlify Docs**: https://docs.netlify.com
- **Vercel Docs**: https://vercel.com/docs
- **GitHub Pages Guide**: https://pages.github.com
- **AWS S3 Guide**: https://docs.aws.amazon.com/s3
- **DNS Checker**: https://whatsmydns.net
- **SSL Checker**: https://www.ssl-checker.com
- **PageSpeed Insights**: https://pagespeed.web.dev

---

**Need help?** Refer to the platform-specific documentation or reach out to their support team.

Last Updated: 2024
