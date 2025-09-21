# 🚀 GitHub Pages Deployment Guide

Follow these steps to deploy your AI Agent Protocols presentation to GitHub Pages with your custom domain.

## Step 1: Create GitHub Repository

1. Go to [GitHub.com](https://github.com) and sign in to your `mctar` account
2. Click the "+" icon in the top right corner and select "New repository"
3. Set the repository name to: `ai-agent-protocols-2025`
4. Make it **Public** (required for GitHub Pages on free accounts)
5. **Don't** initialize with README, .gitignore, or license (we already have these)
6. Click "Create repository"

## Step 2: Push Local Repository to GitHub

Run these commands in your terminal from the project directory:

```bash
# Add the GitHub remote (replace with your actual repo URL)
git remote add origin https://github.com/mctar/ai-agent-protocols-2025.git

# Push to GitHub
git branch -M main
git push -u origin main
```

## Step 3: Configure GitHub Pages

1. Go to your repository on GitHub: `https://github.com/mctar/ai-agent-protocols-2025`
2. Click on **Settings** tab
3. Scroll down to **Pages** section in the left sidebar
4. Under **Source**, select "Deploy from a branch"
5. Select **main** branch and **/ (root)** folder
6. Click **Save**

## Step 4: Configure Custom Domain

### In GitHub:
1. Still in the **Pages** section of repository settings
2. Under **Custom domain**, enter: `agpro.btrbot.com`
3. Click **Save**
4. Wait for DNS check to complete (may take a few minutes)
5. Once verified, check **Enforce HTTPS**

### DNS Configuration:
You need to configure your DNS settings for `btrbot.com` domain:

#### Option A: CNAME Record (Recommended)
Add this CNAME record to your DNS provider:
```
Name: agpro
Type: CNAME
Value: mctar.github.io
TTL: 3600 (or default)
```

#### Option B: A Records (Alternative)
If CNAME doesn't work, use these A records:
```
Name: agpro
Type: A
Value: 185.199.108.153
Value: 185.199.109.153
Value: 185.199.110.153
Value: 185.199.111.153
TTL: 3600 (or default)
```

## Step 5: Verify Deployment

1. Wait 5-10 minutes for DNS propagation
2. Visit: `https://agpro.btrbot.com`
3. Your presentation should be live!

## 📝 Files Created for GitHub Pages

- ✅ `index.html` - Main presentation file
- ✅ `CNAME` - Custom domain configuration
- ✅ `README.md` - Repository documentation
- ✅ `.gitignore` - Git ignore rules

## 🔧 Troubleshooting

### Domain Not Working?
- Check DNS propagation: [whatsmydns.net](https://www.whatsmydns.net)
- Verify CNAME file contains only: `agpro.btrbot.com`
- Ensure repository is public
- Wait up to 24 hours for full DNS propagation

### HTTPS Certificate Issues?
- GitHub automatically provisions SSL certificates for custom domains
- May take 5-10 minutes after DNS verification
- Try accessing via HTTP first, then enable HTTPS enforcement

### Page Not Updating?
- Clear browser cache (Ctrl+F5 or Cmd+Shift+R)
- Check GitHub Actions tab for deployment status
- Verify latest commit is on main branch

## 🎯 Quick Commands Reference

```bash
# Update presentation and deploy
git add .
git commit -m "Update presentation content"
git push origin main

# Check repository status
git status
git log --oneline

# View remote URL
git remote -v
```

---

**🎉 Once deployed, your presentation will be available at:**
# [https://agpro.btrbot.com](https://agpro.btrbot.com)

*Generated with Claude Code*