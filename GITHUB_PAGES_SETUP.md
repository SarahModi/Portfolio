# GitHub Pages Deployment Setup

## Quick Setup (5 minutes)

### Step 1: Create Repository
```bash
# Create new repo on GitHub named: cybersecurity-portfolio
# OR use your custom name

git clone https://github.com/YOUR_USERNAME/cybersecurity-portfolio.git
cd cybersecurity-portfolio
```

### Step 2: Add Your Files
```bash
# Copy the HTML file as index.html (required for GitHub Pages)
cp cybersecurity-portfolio.html index.html

# Optional: Add React version for advanced users
cp cybersecurity-portfolio.jsx src/

# Copy README
cp README.md .

# Create .gitignore
echo "node_modules/" > .gitignore
echo "dist/" >> .gitignore
echo ".env" >> .gitignore
```

### Step 3: Customize Your Portfolio

Edit `index.html` and update:
- Your name and bio
- GitHub and LinkedIn URLs
- Skills and percentages
- Projects and descriptions
- Certifications
- Contact email

### Step 4: Deploy

```bash
git add .
git commit -m "Initial portfolio commit"
git push origin main
```

### Step 5: Enable GitHub Pages

1. Go to Repository Settings
2. Scroll to "GitHub Pages" section
3. Select "Deploy from a branch"
4. Choose `main` branch
5. Select `/ (root)` folder
6. Click "Save"

Your portfolio will be live at:
```
https://YOUR_USERNAME.github.io/cybersecurity-portfolio
```

---

## Custom Domain Setup

### Step 1: Buy Domain
- GoDaddy, Namecheap, Google Domains, etc.

### Step 2: Configure DNS

For registrars using A records, point to GitHub's IP:
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

For CNAME records:
```
YOUR_USERNAME.github.io
```

### Step 3: Update GitHub Pages

1. Repository Settings → Pages
2. Under "Custom domain", enter your domain
3. GitHub will create a CNAME file
4. Wait 24 hours for DNS propagation

### Step 4: Enable HTTPS
- Check "Enforce HTTPS" once domain is verified (automatic)

---

## Automatic Deployment with GitHub Actions

Create `.github/workflows/deploy.yml`:

```yaml
name: Deploy Portfolio

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  deploy:
    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v3
    
    - name: Check HTML validity
      run: |
        # Optional: Add HTML validation here
        ls -la index.html

    - name: Deploy to GitHub Pages
      uses: peaceiris/actions-gh-pages@v3
      with:
        github_token: ${{ secrets.GITHUB_TOKEN }}
        publish_dir: ./

    - name: Notify deployment
      run: echo "✅ Portfolio deployed successfully!"
```

---

## File Structure for GitHub Pages

```
cybersecurity-portfolio/
├── index.html                 # REQUIRED: Main portfolio file
├── README.md                  # Repository documentation
├── CNAME                      # OPTIONAL: Custom domain (auto-created)
└── .github/
    └── workflows/
        └── deploy.yml         # OPTIONAL: Auto-deploy workflow
```

---

## Environment Variables (Optional)

If using analytics or other services, create `.env`:

```env
REACT_APP_GITHUB_URL=https://github.com/yourprofile
REACT_APP_LINKEDIN_URL=https://linkedin.com/in/yourprofile
REACT_APP_EMAIL=your.email@example.com
```

---

## SEO & Meta Tags

Already included in portfolio:
- ✅ Meta description
- ✅ Keywords for searchability
- ✅ Open Graph tags (social sharing)
- ✅ Viewport optimization
- ✅ Canonical URLs

---

## Analytics Setup (Optional)

### Google Analytics

Add to `<head>` section of index.html:

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

Replace `GA_MEASUREMENT_ID` with your Google Analytics property ID.

### Plausible Analytics (Privacy-friendly)

Add to `<head>` section:

```html
<script defer data-domain="yourdomain.com" src="https://plausible.io/js/script.js"></script>
```

---

## Troubleshooting

### Portfolio not showing up after push
- Verify `index.html` is in root directory
- Check GitHub Pages is enabled in Settings
- Wait 1-2 minutes for initial deployment
- Clear browser cache (Ctrl+Shift+Delete)

### Custom domain not working
- Verify DNS settings propagated (use DNS checker tool)
- Check CNAME file in root directory
- Wait 24-48 hours for full DNS propagation
- Enable HTTPS once verified

### Content not updating
- GitHub Pages caches aggressively
- Hard refresh: Ctrl+Shift+R (Cmd+Shift+R on Mac)
- Clear cache: Settings → Clear browsing data

### GitHub Pages showing 404
- Ensure file is named `index.html`
- Check file is in root directory
- Verify repository is public
- Confirm Settings > Pages is configured

---

## Performance Tips

1. **Minify CSS/HTML**
   - Use online tools or build scripts
   - Reduces file size by 30-40%

2. **Optimize Images**
   - Use WebP format
   - Compress PNG/JPG
   - Lazy load non-critical images

3. **Enable Caching**
   - GitHub Pages handles this automatically
   - Browser caches static assets

4. **Monitor Performance**
   - Use Google PageSpeed Insights
   - Aim for 90+ scores
   - Check mobile performance

---

## Security Best Practices

- ✅ No sensitive data in HTML/JS
- ✅ HTTPS enforced (auto with GitHub Pages)
- ✅ No local storage or cookies
- ✅ External links use `rel="noopener noreferrer"`
- ✅ No embedded API keys

---

## Social Media Integration

### LinkedIn
```html
<meta property="og:title" content="Your Portfolio">
<meta property="og:description" content="Bug Bounty Hunter & Security Researcher">
<meta property="og:image" content="portfolio-preview.png">
<meta property="og:url" content="https://yourdomain.com">
```

### Twitter
```html
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="Your Portfolio">
<meta name="twitter:description" content="Bug Bounty Hunter & Security Researcher">
<meta name="twitter:image" content="portfolio-preview.png">
```

---

## Advanced Customization

### Custom CSS Variables
Edit `<style>` section in HTML:
```css
:root {
    --color-cyan-500: #YOUR_COLOR;
    --color-cyan-400: #YOUR_COLOR;
    --color-blue-500: #YOUR_COLOR;
}
```

### Custom Fonts
Add to `<head>`:
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono&display=swap" rel="stylesheet">
```

Update CSS:
```css
body {
    font-family: 'JetBrains Mono', monospace;
}
```

---

## Deployment Checklist

- [ ] Created GitHub repository
- [ ] Added all portfolio files
- [ ] Renamed main file to `index.html`
- [ ] Customized content (name, links, skills, projects)
- [ ] Tested locally in browser
- [ ] Committed and pushed to main branch
- [ ] Enabled GitHub Pages in Settings
- [ ] Verified portfolio is live
- [ ] Added custom domain (optional)
- [ ] Tested on mobile devices
- [ ] Added to resume/LinkedIn profile
- [ ] Shared with friends/network

---

## Next Steps After Deployment

1. **Share Your Portfolio**
   - Update resume with URL
   - Add to LinkedIn profile
   - Share on Twitter/LinkedIn posts
   - Include in email signature

2. **Optimize for Search**
   - Submit to Google Search Console
   - Monitor search performance
   - Update meta descriptions

3. **Keep It Fresh**
   - Add new projects monthly
   - Update skill percentages as you learn
   - Write vulnerability writeups
   - Document your bug bounty journey

4. **Gather Analytics**
   - Track visitor sources
   - Monitor bounce rates
   - Identify which projects attract interest

---

## Resources

- **GitHub Pages Docs**: https://pages.github.com
- **Custom Domain Guide**: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site
- **GitHub Actions**: https://github.com/features/actions
- **DNS Checker**: https://dnschecker.org

---

## Questions?

Check the main README.md for:
- Customization guide
- Content tips
- Design variations
- Troubleshooting

**Your portfolio is now live! 🎉**

Happy bug hunting! 🔍
