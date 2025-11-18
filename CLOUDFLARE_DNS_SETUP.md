# Cloudflare DNS Setup for alinapandey.com.np

This guide will help you configure your domain in Cloudflare once it's activated.

## Prerequisites
- Domain `alinapandey.com.np` is registered and active
- Access to your domain registrar account
- Cloudflare account (free tier works perfectly)

---

## Step 1: Add Domain to Cloudflare

1. **Login to Cloudflare**
   - Go to [dash.cloudflare.com](https://dash.cloudflare.com)
   - Sign up if you don't have an account

2. **Add Your Site**
   - Click "Add a Site" button
   - Enter: `alinapandey.com.np`
   - Click "Add Site"

3. **Select Plan**
   - Choose **Free** plan (sufficient for this website)
   - Click "Continue"

4. **Wait for DNS Scan**
   - Cloudflare will scan existing DNS records
   - This takes about 1 minute

---

## Step 2: Configure DNS Records in Cloudflare

Once the scan completes, you'll need to add/modify these DNS records:

### Option A: Using Netlify (Recommended)

After deploying to Netlify, add these records:

```
Type: A
Name: @
Content: 75.2.60.5
Proxy status: Proxied (Orange Cloud)
TTL: Auto

Type: CNAME
Name: www
Content: [your-netlify-site].netlify.app
Proxy status: Proxied (Orange Cloud)
TTL: Auto
```

**Example:**
```
Type: A
Name: @
Content: 75.2.60.5
Proxy: ✅ Proxied

Type: CNAME
Name: www
Content: alinapandey-site.netlify.app
Proxy: ✅ Proxied
```

### Option B: Using GitHub Pages

```
Type: A
Name: @
Content: 185.199.108.153
Proxy status: Proxied (Orange Cloud)
TTL: Auto

Type: A
Name: @
Content: 185.199.109.153
Proxy status: Proxied (Orange Cloud)
TTL: Auto

Type: A
Name: @
Content: 185.199.110.153
Proxy status: Proxied (Orange Cloud)
TTL: Auto

Type: A
Name: @
Content: 185.199.111.153
Proxy status: Proxied (Orange Cloud)
TTL: Auto

Type: CNAME
Name: www
Content: [your-github-username].github.io
Proxy status: Proxied (Orange Cloud)
TTL: Auto
```

### Option C: Traditional Web Hosting

```
Type: A
Name: @
Content: [Your hosting provider's IP address]
Proxy status: Proxied (Orange Cloud)
TTL: Auto

Type: CNAME
Name: www
Content: alinapandey.com.np
Proxy status: Proxied (Orange Cloud)
TTL: Auto
```

---

## Step 3: Update Nameservers at Domain Registrar

After adding DNS records in Cloudflare, you'll see nameservers like:

```
kara.ns.cloudflare.com
walt.ns.cloudflare.com
```

**Update these at your domain registrar:**

1. Login to your domain registrar (where you bought alinapandey.com.np)
2. Find DNS/Nameserver settings
3. Replace existing nameservers with Cloudflare's nameservers
4. Save changes

**Common registrars:**
- **Namecheap**: Domain List → Manage → Nameservers → Custom DNS
- **GoDaddy**: Domains → DNS → Nameservers → Change
- **Porkbun**: Domain → DNS → Nameservers
- **Nepal-specific**: Check with your .np registrar

---

## Step 4: Cloudflare Settings (Recommended)

### SSL/TLS Settings
1. Go to **SSL/TLS** tab
2. Set mode to: **Full** (or **Full (Strict)** if using Netlify/GitHub)
3. Enable **Always Use HTTPS**
4. Enable **Automatic HTTPS Rewrites**

### Security Settings
1. Go to **Security** → **Settings**
2. Security Level: **Medium**
3. Challenge Passage: **30 minutes**

### Speed Settings
1. Go to **Speed** → **Optimization**
2. Enable **Auto Minify**: CSS, JavaScript, HTML
3. Enable **Brotli** compression
4. Enable **Rocket Loader** (optional)

### Caching
1. Go to **Caching** → **Configuration**
2. Caching Level: **Standard**
3. Browser Cache TTL: **4 hours** or **1 day**

---

## Step 5: Verify Setup

### DNS Propagation Check
- Wait 24-48 hours for full propagation
- Check status: [whatsmydns.net](https://whatsmydns.net)
- Enter: `alinapandey.com.np`

### Test Your Site
```
http://alinapandey.com.np
http://www.alinapandey.com.np
https://alinapandey.com.np
https://www.alinapandey.com.np
```

All should redirect to: `https://alinapandey.com.np`

---

## Quick Reference: DNS Records Summary

### For Netlify Deployment:
| Type | Name | Content | Proxy |
|------|------|---------|-------|
| A | @ | 75.2.60.5 | ✅ Proxied |
| CNAME | www | your-site.netlify.app | ✅ Proxied |

### For GitHub Pages:
| Type | Name | Content | Proxy |
|------|------|---------|-------|
| A | @ | 185.199.108.153 | ✅ Proxied |
| A | @ | 185.199.109.153 | ✅ Proxied |
| A | @ | 185.199.110.153 | ✅ Proxied |
| A | @ | 185.199.111.153 | ✅ Proxied |
| CNAME | www | username.github.io | ✅ Proxied |

---

## Complete Deployment Workflow

### Timeline:
1. **Now**: Deploy website to Netlify/GitHub
2. **Now**: Add domain to Cloudflare
3. **Now**: Configure DNS records in Cloudflare
4. **Now**: Update nameservers at domain registrar
5. **1-2 hours**: Nameservers update
6. **24-48 hours**: Full DNS propagation
7. **Done**: Website live at alinapandey.com.np

---

## Troubleshooting

### "DNS_PROBE_FINISHED_NXDOMAIN"
- Nameservers not updated yet
- Wait for propagation
- Verify nameservers at registrar

### "Too Many Redirects"
- Change SSL mode to **Full** or **Full (Strict)**
- Clear browser cache
- Wait 5 minutes and retry

### "Website Not Secure"
- Wait for SSL certificate provisioning (5-10 minutes)
- Ensure **Always Use HTTPS** is enabled
- Check SSL/TLS mode is **Full**

### Mixed Content Warnings
- Enable **Automatic HTTPS Rewrites**
- Update any hardcoded HTTP links to HTTPS

---

## Cloudflare Benefits

✅ **Free SSL Certificate** - Automatic HTTPS
✅ **CDN** - Fast loading worldwide
✅ **DDoS Protection** - Security included
✅ **Analytics** - Traffic insights
✅ **Caching** - Improved performance
✅ **Always Online** - Backup if hosting fails

---

## Next Steps After DNS is Active

1. ✅ Verify site loads on all URLs
2. ✅ Test mobile responsiveness
3. ✅ Check page load speed
4. ✅ Setup Cloudflare Web Analytics
5. ✅ Add site to Google Search Console
6. ✅ Submit sitemap (create one if needed)

---

## Need Help?

- **Cloudflare Docs**: [developers.cloudflare.com](https://developers.cloudflare.com)
- **Cloudflare Community**: [community.cloudflare.com](https://community.cloudflare.com)
- **DNS Help**: Contact your domain registrar
- **Netlify + Cloudflare**: [netlify.com/docs](https://docs.netlify.com/domains-https/custom-domains/)

---

## Important Notes

⚠️ **Orange Cloud (Proxied)**
- Recommended for most records
- Enables Cloudflare features (CDN, security)
- May need "DNS Only" (grey cloud) for some hosting

⚠️ **Nameserver Updates**
- Changes are **not instant**
- Takes 1-48 hours depending on registrar
- During transition, site may be temporarily unavailable

⚠️ **SSL Certificate**
- Cloudflare provisions automatically
- May take 5-15 minutes after DNS propagation
- "Always Use HTTPS" should be enabled

---

**Ready to Deploy?** Follow the steps above once your domain is activated!
