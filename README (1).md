# Elite Security Portfolio 🔐

A highly elegant, professional cybersecurity portfolio website for aspiring bug bounty hunters and security researchers. Built with a minimalist "girl hacker" aesthetic featuring iOS-inspired design, dark theme, and smooth micro-animations.

## ✨ Features

### Design & Aesthetics
- **Minimalist Dark Theme**: Matte black background (iOS-style) with elegant typography
- **Smooth Micro-Animations**: Fade-ins, glows, and subtle hover effects
- **Elegant Typography**: Clean, modern fonts optimized for readability
- **Gradient Accents**: Cyan, blue, and purple gradients for visual depth
- **Responsive Design**: Perfect on mobile, tablet, and desktop
- **Parallax Effects**: Subtle scroll-based movement for depth

### Interactive Elements
- **Smooth Navigation**: Fixed navbar with smooth scrolling to sections
- **Skill Progress Bars**: Animated bars with hover effects and gradient colors
- **Project Cards**: Hover glows and smooth transitions
- **Timeline Section**: Completed/upcoming milestones with visual indicators
- **Mobile Menu**: Responsive hamburger menu for smaller screens

### Sections Included
1. **Hero Section** - Animated title with blinking cursor, badge, and CTA buttons
2. **About Me** - Professional bio with highlights
3. **Skills** - Categorized skills (Web Security, Tools, Programming, Learning)
4. **Projects** - Showcase of security tools and projects
5. **Journey** - Timeline of learning and achievements
6. **Writeups** - Placeholder for vulnerability writeups
7. **Certifications** - 10 certification slots (customizable)
8. **Contact** - Social links and contact information
9. **Footer** - Minimal command-line inspired footer

## 📁 File Structure

```
cybersecurity-portfolio/
├── cybersecurity-portfolio.html          # Static HTML version (GitHub Pages friendly)
├── cybersecurity-portfolio.jsx           # React component version
├── README.md                             # This file
├── index.html                            # Symlink to main portfolio
└── .github/
    └── workflows/
        └── deploy.yml                    # GitHub Pages deployment workflow
```

## 🚀 Quick Start

### Option 1: GitHub Pages (Recommended for beginners)

1. **Fork or Clone this repository**
   ```bash
   git clone https://github.com/yourusername/cybersecurity-portfolio.git
   cd cybersecurity-portfolio
   ```

2. **Replace placeholders with your information**
   - Update name, email, and social links in HTML
   - Update skill percentages as needed
   - Add your actual project repositories

3. **Deploy to GitHub Pages**
   - Push to your repository
   - Go to Settings → Pages
   - Select `main` branch as source
   - Your site will be live at `https://yourusername.github.io/cybersecurity-portfolio`

### Option 2: Local Development (React)

1. **Create a React app**
   ```bash
   npx create-react-app my-portfolio
   cd my-portfolio
   ```

2. **Replace App.jsx with the React component**
   ```bash
   # Copy cybersecurity-portfolio.jsx to src/App.jsx
   cp cybersecurity-portfolio.jsx src/App.jsx
   ```

3. **Run locally**
   ```bash
   npm start
   ```

4. **Build for production**
   ```bash
   npm run build
   ```

### Option 3: Self-hosted Static Site

Simply deploy the `cybersecurity-portfolio.html` file to any web server:
- **Netlify**: Drag & drop the HTML file
- **Vercel**: Push to GitHub and connect
- **Traditional Hosting**: Upload via FTP

## 🎨 Customization Guide

### Update Personal Information

**In the HTML file, find and replace:**

```html
<!-- Hero Section -->
<h1 class="hero-title">
    breaking the
    <span class="hero-title-highlight">
        insecure
    </span>
    to build the secure
    <span class="hero-cursor"></span>
</h1>

<!-- About Section -->
<p>I'm a BCA student passionate about...</p>

<!-- Contact Links -->
<a href="https://github.com">  <!-- Update this -->
<a href="https://linkedin.com">  <!-- Update this -->
```

### Customize Skills & Percentages

Update the skill bars in the skills section:

```html
<div class="skill-item skill-web">
    <div class="skill-header">
        <span class="skill-name">XSS (Cross-Site Scripting)</span>
        <span class="skill-percentage">75%</span>  <!-- Change this -->
    </div>
    <div class="skill-bar">
        <div class="skill-progress" style="width: 75%;" data-width="75%"></div>
        <!-- Change both percentages -->
    </div>
</div>
```

### Add Your Projects

Update the projects grid section with your repositories:

```html
<div class="project-card">
    <div class="project-card-inner">
        <h3 class="project-title">Your Project Name</h3>
        <p class="project-description">
            Your project description...
        </p>
        <div class="project-tags">
            <span class="project-tag">Tech1</span>
            <span class="project-tag">Tech2</span>
        </div>
        <a href="https://github.com/yourrepo" class="project-link">
            View Repository →
        </a>
    </div>
</div>
```

### Customize Color Scheme

The portfolio uses CSS variables for easy color customization:

```css
:root {
    --color-cyan-500: #06b6d4;     /* Primary accent */
    --color-cyan-400: #22d3ee;     /* Lighter accent */
    --color-blue-500: #3b82f6;     /* Secondary accent */
    --color-purple-500: #a855f7;   /* Tertiary accent */
    --color-black: #000000;        /* Background */
}
```

### Update Timeline

Add your milestones in the journey section:

```html
<div class="timeline-item completed">
    <div class="timeline-dot"></div>
    <div class="timeline-year">2024</div>
    <div class="timeline-title">Your Milestone</div>
    <div class="timeline-description">
        Description of your achievement...
    </div>
</div>
```

### Add Certifications

Fill in your certification slots:

```html
<div class="cert-card">
    <div class="cert-card-inner">
        <div class="cert-icon">🏆</div>
        <div class="cert-name">Your Certification</div>
        <div class="cert-issuer">Issuing Organization</div>
    </div>
</div>
```

### Add Writeups

Create your vulnerability writeup cards:

```html
<div class="writeup-card">
    <div class="writeup-header">
        <span class="writeup-date">2025-02-10</span>
        <span class="writeup-category">Web Security</span>
    </div>
    <h3 class="writeup-title">Your Vulnerability Title</h3>
    <p class="writeup-status">📝 Detailed writeup...</p>
</div>
```

## 🔧 Customization Examples

### Change Primary Color from Cyan to Neon Green

```css
:root {
    --color-cyan-500: #39ff14;     /* Neon green */
    --color-cyan-400: #3aff0d;     /* Lighter neon */
}
```

### Disable Animations

Add to CSS:
```css
* {
    animation: none !important;
    transition: none !important;
}
```

### Change Font

Update the body font-family:
```css
body {
    font-family: 'Fira Code', 'Source Code Pro', monospace;
}
```

## 📱 Responsive Breakpoints

The portfolio is optimized for:
- **Mobile**: 0px - 640px
- **Tablet**: 641px - 1024px
- **Desktop**: 1025px+

All sections adapt gracefully to different screen sizes.

## ⚡ Performance Optimization

- **Zero External Dependencies**: Pure HTML/CSS/JS
- **Lightweight**: ~45KB uncompressed, ~12KB gzipped
- **Fast Load Time**: Optimized for Lighthouse scores
- **SEO Ready**: Semantic HTML, proper meta tags
- **Accessibility**: WCAG compliant, keyboard navigable

## 🔍 SEO Features

- Meta descriptions and keywords
- Semantic HTML structure
- Open Graph tags for social sharing
- Mobile-friendly viewport
- Fast page load optimization

## 🎯 Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## 📝 Content Tips

### Writing Your Bio
- Keep it concise (2-3 sentences)
- Highlight your unique focus areas
- Show your passion and ambition
- Make it authentic and grounded

### Project Descriptions
- 1-2 sentences max
- Lead with the problem solved
- Include relevant technologies
- Add a GitHub link

### Skill Percentages
- Be realistic and honest
- Rate based on practical experience
- Update as you learn
- 0-30%: Learning, 30-70%: Competent, 70-100%: Expert

### Timeline Milestones
- Include key learning moments
- Add tool/project launches
- Mark certifications achieved
- Plan future goals

## 🐛 Troubleshooting

### Navigation not working
- Check all `id` attributes match `data-section` values
- Ensure JavaScript is enabled
- Clear browser cache

### Animations not playing
- Check CSS animations are enabled
- Verify browser support (all modern browsers supported)
- Check animation-duration values

### Skills bars not animating
- Ensure IntersectionObserver is supported
- Check that `data-width` attributes match `width` styles
- Verify CSS transition properties

### Mobile menu not opening
- Check display: flex/grid on navMenu
- Ensure JavaScript event listeners are attached
- Verify button click handlers

## 📚 Additional Resources

- **Cybersecurity Learning**:
  - HackTheBox: https://www.hackthebox.com
  - TryHackMe: https://tryhackme.com
  - OWASP Top 10: https://owasp.org/www-project-top-ten/

- **Bug Bounty Platforms**:
  - HackerOne: https://hackerone.com
  - Bugcrowd: https://bugcrowd.com
  - Intigriti: https://intigriti.com

- **Security Tools**:
  - Burp Suite: https://portswigger.net/burp
  - OWASP ZAP: https://owasp.org/www-project-zap/
  - Metasploit: https://www.metasploit.com

## 📄 License

This portfolio template is provided as-is for personal use. Feel free to customize and deploy to your own domain.

## 🤝 Support

Need help customizing your portfolio?
- Check the customization guide above
- Review inline code comments
- Test changes in browser DevTools first
- Share your portfolio and tag the creator!

## ✅ Pre-Launch Checklist

- [ ] Updated name and bio
- [ ] Added GitHub profile link
- [ ] Added LinkedIn profile link
- [ ] Updated email address
- [ ] Added your projects
- [ ] Verified skill percentages
- [ ] Updated certifications
- [ ] Tested on mobile
- [ ] Fixed all broken links
- [ ] Added custom domain (optional)
- [ ] Set up analytics (optional)

## 🌟 Going Live

### GitHub Pages Deployment
1. Create a GitHub repo named `cybersecurity-portfolio`
2. Push HTML file to main branch
3. Enable GitHub Pages in settings
4. Share your portfolio URL!

### Custom Domain
1. Buy domain from registrar
2. Point DNS to GitHub Pages
3. Update domain in GitHub Pages settings
4. Verify SSL certificate is working

### SEO & Marketing
- Submit to search engines
- Add to your resume/CV
- Share on LinkedIn, Twitter
- Include in job applications
- Add to email signature

---

**Built with precision and purpose. Happy hunting! 🎯**

Last updated: February 2025
