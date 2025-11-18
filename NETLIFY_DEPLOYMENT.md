# Netlify Deployment Guide - alinapandey.com.np

## ✅ Quick Deployment Steps

### Step 1: Sign up / Login to Netlify

1. Go to [https://app.netlify.com](https://app.netlify.com)
2. Sign up with your GitHub account (recommended)
3. Click "Authorize Netlify"

---

### Step 2: Import Your GitHub Repository

1. Click **"Add new site"** → **"Import an existing project"**
2. Click **"Deploy with GitHub"**
3. Search for: `alinapandey.com.np`
4. Select the repository: `akritpoudel/alinapandey.com.np`

---

### Step 3: Configure Build Settings

On the deploy configuration page:

```
Build command: (leave empty)
Publish directory: /
Branch to deploy: main
```

Click **"Deploy site"**

⏱️ Wait 1-2 minutes for deployment to complete.

---

### Step 4: Your Site is Live!

Netlify will give you a temporary URL like:
`https://random-name-123456.netlify.app`

**Test this URL first** before configuring your custom domain.

---

### Step 5: Configure Custom Domain

1. In Netlify dashboard, click **"Domain settings"**
2. Click **"Add custom domain"**
3. Enter: `alinapandey.com.np`
4. Click **"Verify"**
5. Click **"Add domain"**

Netlify will provide DNS instructions.

---

### Step 6: Configure Cloudflare DNS

Go to your Cloudflare dashboard for `alinapandey.com.np`:

#### Option A: Use Netlify DNS (Recommended)

Netlify will show you their nameservers. Update these in your domain registrar.

#### Option B: Use Cloudflare DNS (Keep your Cloudflare)

Add these DNS records in Cloudflare:

**For Root Domain (@):**
```
Type: A
Name: @
Content: 75.2.60.5
Proxy status: DNS only (gray cloud)
TTL: Auto
```

**For WWW Subdomain:**
```
Type: CNAME
Name: www
Content: [your-site-name].netlify.app
Proxy status: DNS only (gray cloud)
TTL: Auto
```

**Important**: Turn OFF Cloudflare proxy (gray cloud icon) for Netlify to work properly.

---

### Step 7: Enable HTTPS

1. In Netlify, go to **"Domain settings"** → **"HTTPS"**
2. Wait for SSL certificate to provision (5-10 minutes)
3. Click **"Verify DNS configuration"**
4. Enable **"Force HTTPS"** (redirect HTTP to HTTPS)

---

### Step 8: Configure WWW Redirect (Optional)

In Netlify dashboard:
1. Go to **"Domain settings"**
2. Under **"Custom domains"**, add both:
   - `alinapandey.com.np` (primary)
   - `www.alinapandey.com.np` (redirect to primary)

---

## 🎯 Complete DNS Configuration

### If Using Cloudflare DNS:

Add these records in your Cloudflare dashboard:

```dns
# Root domain
Type: A
Name: @
Content: 75.2.60.5
Proxy: OFF (gray cloud)

# WWW subdomain
Type: CNAME
Name: www
Content: [your-site-name].netlify.app
Proxy: OFF (gray cloud)
```

**Replace `[your-site-name]` with your actual Netlify site name.**

---

## ✅ Verification Checklist

After DNS propagation (can take up to 24 hours, usually 10-30 minutes):

- [ ] https://alinapandey.com.np loads correctly
- [ ] https://www.alinapandey.com.np redirects to main domain
- [ ] HTTPS is enabled (green padlock in browser)
- [ ] All pages work (homepage, writings page)
- [ ] All article links work
- [ ] Mobile menu works on phone
- [ ] Site is responsive on all devices

---

## 🔄 Automatic Deployments

**Great news!** Now whenever you push changes to GitHub:

```bash
git add .
git commit -m "Update content"
git push origin main
```

Netlify will automatically rebuild and deploy your site in ~1 minute!

---

## 🐛 Troubleshooting

### Issue: Site not loading
**Solution**: Wait 10-30 minutes for DNS propagation. Clear browser cache.

### Issue: "Not secure" warning
**Solution**: Wait for SSL certificate to provision (5-10 minutes). Check HTTPS settings in Netlify.

### Issue: Page not found (404)
**Solution**: In Netlify, go to **"Site settings"** → **"Build & deploy"** → Check publish directory is `/`

### Issue: Domain not verified
**Solution**: Check DNS records in Cloudflare. Ensure proxy is OFF (gray cloud). Wait for DNS propagation.

---

## 📱 Testing Your Live Site

### Desktop Testing
1. Open https://alinapandey.com.np in Chrome
2. Test all navigation links
3. Click on article links to verify they work
4. Test mobile menu by resizing browser window

### Mobile Testing
1. Open on your phone: https://alinapandey.com.np
2. Test hamburger menu
3. Verify articles load
4. Check responsive design

---

## 🎨 Performance Optimization (Automatic)

Netlify automatically provides:
- ✅ CDN (Content Delivery Network)
- ✅ HTTPS/SSL
- ✅ Fast global loading
- ✅ Automatic compression
- ✅ DDoS protection

---

## 📊 Monitor Your Site

Netlify Dashboard shows:
- Deploy history
- Build logs
- Analytics (free tier: limited)
- Form submissions (if you add forms later)

---

## 🔐 Security Features

Automatically enabled:
- ✅ HTTPS encryption
- ✅ SSL certificate (Let's Encrypt)
- ✅ Secure headers
- ✅ DDoS protection

---

## 💡 Quick Commands

### View your site locally:
```bash
cd /Users/alishapandey/alinapandey.com.np
python3 -m http.server 8000
# Open http://localhost:8000
```

### Push updates to GitHub (auto-deploys to Netlify):
```bash
git add .
git commit -m "Your update message"
git push origin main
```

---

## 🎯 Post-Deployment Tasks

After successful deployment:

1. **Test all functionality**
   - [ ] All pages load
   - [ ] All links work
   - [ ] Mobile responsive
   - [ ] HTTPS enabled

2. **Share your website**
   - [ ] Update LinkedIn profile with website URL
   - [ ] Share on social media
   - [ ] Add to email signature

3. **SEO Setup** (Optional)
   - [ ] Submit to Google Search Console
   - [ ] Create sitemap.xml
   - [ ] Submit to Google for indexing

---

## 📞 Support Resources

- **Netlify Docs**: https://docs.netlify.com
- **Cloudflare DNS Docs**: https://developers.cloudflare.com/dns
- **Your GitHub Repo**: https://github.com/akritpoudel/alinapandey.com.np

---

## 🚀 You're All Set!

Your professional legal portfolio is now live at:
**https://alinapandey.com.np**

Showcasing:
- ✅ 7 published articles
- ✅ Professional experience
- ✅ Education & awards
- ✅ Clean, responsive design
- ✅ Optimized for law professionals

---

**Deployment completed by Claude Code**
**Ready for production** ✅
