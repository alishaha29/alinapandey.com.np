# Deployment Guide for alinapandey.com.np

This guide will help you deploy your website once the domain is activated.

## Pre-Deployment Checklist

- [ ] Domain `alinapandey.com.np` is registered and active
- [ ] You have access to domain DNS settings
- [ ] All website files are ready
- [ ] You've chosen a hosting method

## Recommended: Netlify Deployment (Free & Easy)

### Step 1: Create Netlify Account
1. Go to [netlify.com](https://netlify.com)
2. Sign up with GitHub, GitLab, or email

### Step 2: Deploy Website
1. Click "Add new site" → "Deploy manually"
2. Drag the `alinapandey.com.np` folder onto the upload area
3. Wait for deployment (usually < 1 minute)
4. You'll get a URL like `random-name-123.netlify.app`

### Step 3: Configure Custom Domain
1. In Netlify dashboard, go to "Domain settings"
2. Click "Add custom domain"
3. Enter `alinapandey.com.np`
4. Also add `www.alinapandey.com.np`

### Step 4: Update DNS Records
In your domain registrar's DNS settings, add:

```
Type: A
Name: @
Value: 75.2.60.5

Type: CNAME
Name: www
Value: [your-site-name].netlify.app
```

### Step 5: Enable HTTPS
1. Netlify will automatically provision an SSL certificate
2. Wait 24-48 hours for DNS propagation
3. Enable "Force HTTPS" in Netlify settings

## Alternative: GitHub Pages (Free)

### Step 1: Create GitHub Repository
1. Create a new repository named `alinapandey.com.np`
2. Make it public

### Step 2: Push Code
```bash
cd alinapandey.com.np
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/alinapandey.com.np.git
git push -u origin main
```

### Step 3: Enable GitHub Pages
1. Go to repository Settings → Pages
2. Source: Deploy from branch `main`
3. Folder: `/ (root)`
4. Save

### Step 4: Configure Custom Domain
1. In GitHub Pages settings, enter `alinapandey.com.np`
2. Enable "Enforce HTTPS" (after DNS propagation)

### Step 5: Update DNS Records
```
Type: A
Name: @
Value: 185.199.108.153

Type: A
Name: @
Value: 185.199.109.153

Type: A
Name: @
Value: 185.199.110.153

Type: A
Name: @
Value: 185.199.111.153

Type: CNAME
Name: www
Value: YOUR_USERNAME.github.io
```

### Step 6: Add CNAME File
Create a file named `CNAME` in the root directory:
```
alinapandey.com.np
```

## Alternative: Traditional Web Hosting

### If you have cPanel/Shared Hosting:

1. **Upload Files**
   - Login to cPanel
   - Open File Manager
   - Navigate to `public_html`
   - Upload all files from `alinapandey.com.np` folder

2. **DNS Configuration**
   - Your hosting provider will give you an IP address
   - Create A record pointing `@` to that IP
   - Create CNAME record for `www` to `alinapandey.com.np`

3. **SSL Certificate**
   - Use cPanel's AutoSSL or Let's Encrypt
   - Enable HTTPS redirect

## DNS Propagation

After updating DNS records:
- Changes take 24-48 hours to propagate globally
- Check status: [whatsmydns.net](https://whatsmydns.net)
- Test your site: `http://alinapandey.com.np`

## Post-Deployment

### Verify Everything Works:
- [ ] Homepage loads correctly
- [ ] All navigation links work
- [ ] Writings page loads
- [ ] Mobile responsive design works
- [ ] HTTPS is enabled
- [ ] www redirects to non-www (or vice versa)

### Performance Check:
- [ ] Test speed: [PageSpeed Insights](https://pagespeed.web.dev)
- [ ] Check mobile: [Mobile-Friendly Test](https://search.google.com/test/mobile-friendly)

### SEO Setup (Optional):
1. **Google Search Console**
   - Add property for `alinapandey.com.np`
   - Submit sitemap (create if needed)

2. **Analytics**
   - Add Google Analytics or Plausible
   - Track visitors and engagement

3. **Social Meta Tags**
   - Add Open Graph tags for social sharing
   - Add Twitter Card tags

## Updating the Website

### For Netlify:
- Drag and drop updated files to Netlify dashboard
- Or connect to GitHub for automatic deployments

### For GitHub Pages:
```bash
git add .
git commit -m "Update content"
git push
```

### For Traditional Hosting:
- Upload changed files via FTP/cPanel File Manager

## Troubleshooting

### Domain Not Resolving
- Check DNS records are correct
- Wait for propagation (up to 48 hours)
- Clear browser cache
- Try incognito/private mode

### HTTPS Not Working
- Wait for SSL certificate provisioning
- Check DNS is propagated
- Ensure HTTPS is enabled in hosting settings

### Styles Not Loading
- Check file paths are relative
- Clear browser cache
- Verify all files uploaded correctly

### Mobile Menu Not Working
- Ensure `main.js` is uploaded
- Check browser console for errors
- Verify file path is correct

## Need Help?

- **Netlify Docs**: [docs.netlify.com](https://docs.netlify.com)
- **GitHub Pages Docs**: [pages.github.com](https://pages.github.com)
- **DNS Help**: Contact your domain registrar

## Security Best Practices

- Always use HTTPS
- Keep backup of website files
- Regularly update content
- Monitor for security issues
- Use strong passwords for hosting accounts

---

**Ready to Deploy?** Choose your hosting method and follow the steps above. Good luck!
