# Repository Setup - Make Private & Separate

## Current Status
- Repository: `akritpoudel/alinapandey.com.np`
- Location: https://github.com/akritpoudel/alinapandey.com.np

---

## Option 1: Make Current Repository Private

### Step 1: Verify/Change Privacy Settings

1. Go to: https://github.com/akritpoudel/alinapandey.com.np
2. Click **Settings** (gear icon)
3. Scroll down to **Danger Zone**
4. Find **Change repository visibility**
5. Click **Change visibility** → **Make private**
6. Confirm by typing the repository name

✅ Your repository is now private!

---

## Option 2: Create New Private Repository Under Different Account

### If you want a separate repository under `alishaha29`:

### Step 1: Create New Private Repository on GitHub

1. Go to: https://github.com/new
2. Fill in:
   - **Owner**: Select `alishaha29` (or your preferred account)
   - **Repository name**: `alinapandey-portfolio` (or any name)
   - **Description**: Professional portfolio website for Alina Pandey
   - **Privacy**: ✅ Select **Private**
   - **DO NOT** initialize with README (we already have files)
3. Click **Create repository**

### Step 2: Change Remote URL to New Repository

```bash
cd /Users/alishapandey/alinapandey.com.np

# Remove current remote
git remote remove origin

# Add new remote (replace with your actual username and repo name)
git remote add origin https://github.com/alishaha29/alinapandey-portfolio.git

# Push to new repository
git push -u origin main
```

### Step 3: Delete Old Repository (Optional)

If you no longer need the old repository:

1. Go to: https://github.com/akritpoudel/alinapandey.com.np/settings
2. Scroll to **Danger Zone**
3. Click **Delete this repository**
4. Follow confirmation steps

---

## Option 3: Transfer Repository Ownership

### Transfer to Different GitHub Account

1. Go to: https://github.com/akritpoudel/alinapandey.com.np/settings
2. Scroll to **Danger Zone**
3. Click **Transfer ownership**
4. Enter new owner username: `alishaha29`
5. Confirm transfer

The repository will move to the new account and remain private.

---

## ✅ Verify Repository is Private

After making changes:

1. Go to your repository on GitHub
2. Look for **🔒 Private** badge next to repository name
3. If you see **Public** instead, follow Option 1 above

---

## 🔐 Privacy Checklist

- [ ] Repository visibility set to **Private**
- [ ] Only authorized users have access
- [ ] Repository under correct GitHub account
- [ ] All commits pushed to private repository
- [ ] No sensitive data exposed

---

## 📝 Current Configuration

After changing repository, update deployment settings:

### For Cloudflare Pages:
1. Go to Cloudflare Pages dashboard
2. Click your project
3. Go to **Settings** → **Build & Deploy**
4. Update GitHub connection if repository changed
5. Re-authorize if needed

### For Netlify (if used):
1. Go to Netlify dashboard
2. Site settings → Build & deploy
3. Update repository link
4. Re-connect GitHub if needed

---

## 🚀 Commands Summary

### Check current remote:
```bash
git remote -v
```

### Change to new repository:
```bash
# Remove old remote
git remote remove origin

# Add new remote
git remote add origin https://github.com/[USERNAME]/[REPO-NAME].git

# Push to new repo
git push -u origin main
```

### Verify connection:
```bash
git remote -v
```

---

## 🔗 Quick Links

- **Current Repository**: https://github.com/akritpoudel/alinapandey.com.np
- **GitHub New Repository**: https://github.com/new
- **GitHub Settings**: https://github.com/settings/repositories

---

## ⚠️ Important Notes

1. **Private repositories** are only visible to:
   - Repository owner
   - Collaborators you invite
   - Organization members (if applicable)

2. **Deployment services** (Cloudflare Pages, Netlify) can still access private repositories when you authorize them.

3. **Making repository private does NOT affect**:
   - Your deployed website (still public)
   - Cloudflare Pages/Netlify access
   - Your ability to push/pull code

4. **Only the code is private**, not the live website.

---

## 💡 Recommended Setup

For best security and organization:

```
Repository: alishaha29/alinapandey-portfolio
Privacy: 🔒 Private
Branch: main
Hosting: Cloudflare Pages
Domain: alinapandey.com.np
```

---

**Let me know which option you'd like to proceed with!**
