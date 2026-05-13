# Deployment Guide

This guide covers how to deploy your "I'm Sorry!" website to various platforms.

## Prerequisites

- Git installed
- Node.js and npm installed (for local development)
- A repository on GitHub, GitLab, or Bitbucket

## File Structure

```
ansh/
├── index.html              # Main page
├── photo.svg              # Profile image (replace with your photo)
├── audio.mp3.mpeg         # Background music
├── package.json           # Node.js configuration
├── vercel.json            # Vercel configuration
├── netlify.toml           # Netlify configuration
├── Procfile               # Heroku configuration
├── web.config             # Azure/IIS configuration
├── .htaccess              # Apache configuration
├── 404.html               # Error page
├── robots.txt             # SEO robots file
├── sitemap.xml            # XML sitemap
├── .gitignore             # Git ignore rules
├── .github/workflows/      # GitHub Actions
└── README.md              # Project documentation
```

## Quick Setup

1. **Initialize Git:**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   ```

2. **Install Dependencies:**
   ```bash
   npm install
   ```

3. **Test Locally:**
   ```bash
   npm start
   ```
   Visit `http://localhost:8000`

## Deployment Options

### Option 1: Vercel (Recommended - Free & Easy)

1. Create account at https://vercel.com
2. Connect your GitHub repository
3. Vercel auto-detects your project
4. Click "Deploy" - Done!

**Or via CLI:**
```bash
npm i -g vercel
vercel
```

### Option 2: Netlify (Free & Easy)

1. Create account at https://netlify.com
2. Connect your GitHub repository
3. Netlify reads `netlify.toml` and deploys automatically

**Or via CLI:**
```bash
npm i -g netlify-cli
netlify deploy
```

### Option 3: Heroku (Free tier available)

1. Create account at https://heroku.com
2. Install Heroku CLI
3. Run:
   ```bash
   heroku create
   git push heroku main
   ```

### Option 4: GitHub Pages (Free)

1. Push to GitHub
2. Go to Settings → Pages
3. Set source to `main` branch
4. Done!

### Option 5: Azure Static Web Apps

1. Create account at https://azure.microsoft.com
2. Create Static Web App resource
3. Connect your repository
4. Uses `web.config` automatically

### Option 6: Apache/Shared Hosting

1. Upload all files to your hosting
2. The `.htaccess` file handles routing
3. Ensure `audio.mp3.mpeg` and `photo.svg` upload correctly

## Before Deploying

### ✅ Checklist:

- [ ] Replace `photo.svg` with your actual photo (keep filename or update HTML)
- [ ] Verify `audio.mp3.mpeg` file exists and is accessible
- [ ] Test locally with `npm start`
- [ ] Update `sitemap.xml` with your domain
- [ ] Update `README.md` with your info
- [ ] Test on mobile devices
- [ ] Test audio playback in different browsers

### File Changes Needed:

1. **Add your photo:**
   - Replace `photo.svg` with your image
   - Or update HTML line 153: `<img src="YOUR_IMAGE_PATH"...`

2. **Update domain in `sitemap.xml`:**
   ```xml
   <loc>https://yoursite.com/</loc>
   ```

## Post-Deployment

### Setup Custom Domain:

- **Vercel:** Project Settings → Domains
- **Netlify:** Domain Settings → Custom Domains
- **Heroku:** Heroku CLI: `heroku domains:add yourdomain.com`
- **GitHub Pages:** Settings → Pages → Custom domain

### Enable HTTPS:

All platforms provide free HTTPS by default! ✅

### Monitor Performance:

- **Vercel:** Analytics dashboard
- **Netlify:** Analytics in dashboard
- **Google Search Console:** Add your domain for SEO tracking

## Troubleshooting

### Audio not playing?
- Ensure `audio.mp3.mpeg` is in the root folder
- Check browser console for errors
- Some browsers need user interaction before playing audio
- Verify MIME type is set correctly

### Image not showing?
- Verify `photo.svg` exists
- Check image file size (not too large)
- Ensure correct file path in HTML
- Try different image format if needed

### 404 errors on refresh?
- Vercel & Netlify automatically use `404.html` ✅
- Apache uses `.htaccess` ✅
- Azure uses `web.config` ✅
- If using custom hosting, ensure redirects are configured

### CORS issues with audio?
- This is rare for static files
- Ensure server sets proper CORS headers
- Try moving audio file to CDN if needed

## File References

| File | Used By | Required |
|------|---------|----------|
| index.html | All | ✅ Yes |
| photo.svg | Displayed in card | ⚠️ Yes (replace) |
| audio.mp3.mpeg | Background music | ✅ Yes |
| package.json | Node servers | Optional |
| vercel.json | Vercel | Auto-detected |
| netlify.toml | Netlify | Auto-detected |
| Procfile | Heroku | Auto-detected |
| web.config | Azure/IIS | Auto-detected |
| .htaccess | Apache | Auto-detected |
| 404.html | Error handling | Optional |
| robots.txt | SEO | Optional |
| sitemap.xml | SEO | Optional |

## Cost

- **Vercel:** Free tier (up to 100GB bandwidth)
- **Netlify:** Free tier (100GB bandwidth)
- **Heroku:** Free tier ended (paid plans from $7/month)
- **GitHub Pages:** Free forever
- **Azure:** Free tier available
- **Traditional hosting:** Varies ($2-50/month)

## Support

For platform-specific help:
- Vercel: https://vercel.com/docs
- Netlify: https://docs.netlify.com
- Heroku: https://devcenter.heroku.com
- GitHub Pages: https://docs.github.com/en/pages

---

**Last Updated:** May 13, 2026
