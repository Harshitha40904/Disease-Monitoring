# Deployment Guide: Infectious Disease Monitor

This guide will walk you through deploying your infectious disease monitoring website to GitHub Pages.

## 🚀 Quick Start

### 1. Create GitHub Repository

1. Go to [GitHub](https://github.com) and sign in
2. Click the "+" icon in the top right corner
3. Select "New repository"
4. Name it: `infectious-disease-monitor`
5. Make it **Public** (required for free GitHub Pages)
6. Don't initialize with README (we already have one)
7. Click "Create repository"

### 2. Upload Your Code

```bash
# Navigate to your project directory
cd infectious-disease-monitor

# Initialize git repository
git init

# Add all files
git add .

# Make initial commit
git commit -m "Initial commit: Infectious Disease Monitor website"

# Add remote origin (replace YOUR_USERNAME with your GitHub username)
git remote add origin https://github.com/YOUR_USERNAME/infectious-disease-monitor.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### 3. Enable GitHub Pages

1. Go to your repository on GitHub
2. Click "Settings" tab
3. Scroll down to "Pages" section (left sidebar)
4. Under "Source", select "Deploy from a branch"
5. Choose "main" branch and "/ (root)" folder
6. Click "Save"
7. Wait a few minutes for deployment

Your site will be available at: `https://YOUR_USERNAME.github.io/infectious-disease-monitor/`

## 🔧 Advanced Configuration

### Custom Domain (Optional)

1. In GitHub Pages settings, enter your custom domain
2. Add a CNAME record in your DNS provider pointing to `YOUR_USERNAME.github.io`
3. Create a `CNAME` file in your repository root with your domain name

### Branch-based Deployment

For more control, you can use a separate branch:

```bash
# Create and switch to gh-pages branch
git checkout -b gh-pages

# Push gh-pages branch
git push origin gh-pages

# In GitHub Pages settings, select gh-pages branch
```

## 📁 File Structure for GitHub Pages

```
infectious-disease-monitor/
├── index.html              # Main page (required)
├── css/                    # Stylesheets
├── js/                     # JavaScript files
├── data/                   # Sample datasets
├── assets/                 # Images and other assets
├── README.md               # Project documentation
└── .gitignore             # Git ignore file
```

## 🛡️ Security Considerations

### For Production Use

1. **Data Privacy**: All processing happens client-side
2. **No Server Storage**: Medical data never leaves user's device
3. **HTTPS**: GitHub Pages provides automatic HTTPS
4. **Content Security Policy**: Consider adding CSP headers

### Add Security Headers

Create a `_headers` file in your repository root:

```
/*
  X-Frame-Options: DENY
  X-Content-Type-Options: nosniff
  Referrer-Policy: strict-origin-when-cross-origin
  Permissions-Policy: camera=(), microphone=(), geolocation=()
```

## 🔄 Continuous Deployment

### Automatic Updates

1. **Local Development**: Make changes to your files
2. **Commit Changes**: `git add . && git commit -m "Update description"`
3. **Push to GitHub**: `git push origin main`
4. **Automatic Deployment**: GitHub Pages automatically rebuilds and deploys

### Development Workflow

```bash
# Make changes to your files
# Test locally by opening index.html in browser

# Commit and push changes
git add .
git commit -m "Description of changes"
git push origin main

# Wait 2-5 minutes for deployment
# Check your live site
```

## 🧪 Testing Your Deployment

### Local Testing

```bash
# Test locally before deploying
python -m http.server 8000
# Open http://localhost:8000 in browser
```

### Post-Deployment Testing

1. **Functionality**: Test all features work on live site
2. **Responsiveness**: Test on different devices/screen sizes
3. **Performance**: Use Google PageSpeed Insights
4. **Cross-browser**: Test in Chrome, Firefox, Safari, Edge

## 🚨 Troubleshooting

### Common Issues

1. **Site Not Loading**
   - Check GitHub Pages settings
   - Verify repository is public
   - Wait 5-10 minutes for initial deployment

2. **404 Errors**
   - Ensure `index.html` is in root directory
   - Check file paths in your code
   - Verify case sensitivity

3. **Styling Issues**
   - Check CSS file paths
   - Verify external CDN links work
   - Clear browser cache

4. **JavaScript Errors**
   - Check browser console for errors
   - Verify JS file paths
   - Test locally first

### Debug Mode

Add this to your HTML for debugging:

```html
<script>
  // Enable debug mode
  window.DEBUG = true;
  
  // Log deployment info
  console.log('Deployment:', {
    timestamp: new Date().toISOString(),
    userAgent: navigator.userAgent,
    url: window.location.href
  });
</script>
```

## 📊 Monitoring & Analytics

### GitHub Insights

- **Traffic**: View page views and unique visitors
- **Popular Content**: See which pages are most visited
- **Referrers**: Track where traffic comes from

### External Analytics (Optional)

Add Google Analytics:

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

## 🔒 Privacy & Compliance

### HIPAA Considerations

- **Client-side Processing**: All data stays on user's device
- **No Data Collection**: No personal information is stored
- **Educational Purpose**: Clearly marked as research/educational tool
- **Disclaimer**: Prominent medical disclaimer

### Privacy Policy

Consider adding a privacy policy page:

```html
<!-- Add to navigation -->
<li><a href="#privacy" class="nav-link">Privacy</a></li>

<!-- Add privacy section -->
<section id="privacy" class="privacy-section">
  <div class="container">
    <h2>Privacy Policy</h2>
    <p>This application processes all data locally in your browser...</p>
  </div>
</section>
```

## 🚀 Performance Optimization

### Best Practices

1. **Minimize HTTP Requests**: Combine CSS/JS files
2. **Optimize Images**: Use WebP format, compress images
3. **Lazy Loading**: Load non-critical resources on demand
4. **Caching**: Set appropriate cache headers

### Performance Monitoring

```bash
# Test performance
npm install -g lighthouse
lighthouse https://YOUR_USERNAME.github.io/infectious-disease-monitor
```

## 📈 Scaling Considerations

### Future Enhancements

1. **CDN**: Use Cloudflare or similar for global distribution
2. **Progressive Web App**: Add PWA capabilities
3. **Offline Support**: Implement service workers
4. **Database**: Consider client-side databases (IndexedDB)

## 🎯 Success Metrics

### Track These Metrics

- **Page Load Time**: Target < 3 seconds
- **User Engagement**: Time on site, pages per session
- **Error Rate**: JavaScript errors, 404s
- **Mobile Performance**: Mobile-first design validation

## 📞 Support & Maintenance

### Regular Maintenance

1. **Monthly**: Update dependencies, check for broken links
2. **Quarterly**: Review security, performance optimization
3. **Annually**: Major feature updates, design refresh

### Getting Help

- **GitHub Issues**: Report bugs and request features
- **GitHub Discussions**: Community support
- **Documentation**: Keep README and deployment guide updated

---

## 🎉 Congratulations!

Your infectious disease monitoring website is now live on GitHub Pages! 

**Next Steps:**
1. Test all functionality on the live site
2. Share your project with the community
3. Gather feedback and iterate
4. Consider adding more features and datasets

**Remember**: This is an educational tool. Always include appropriate medical disclaimers and encourage users to consult healthcare professionals for actual medical concerns.
