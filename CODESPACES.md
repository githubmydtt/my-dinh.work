# GitHub Codespaces Quick Start

## 🚀 Launch GitHub Codespaces

1. **Go to your repository**: https://github.com/githubmydtt/my-dinh.work
2. **Click the green "Code" button**
3. **Select "Codespaces" tab**
4. **Click "Create codespace on main"**
5. **Wait 2-3 minutes for setup**

## ⚡ Immediate Development Commands

Once Codespaces loads, open the terminal and run:

```bash
# Start Hugo development server
hugo server -D --bind=0.0.0.0 --baseURL=https://$(hostname)

# Or use the npm script
npm run dev
```

## 🎯 What You Get Instantly

✅ **Live Preview**: Click the "Ports" tab → Open port 1313 in browser
✅ **File Editor**: Full VS Code with Hugo syntax highlighting  
✅ **Terminal**: Run Hugo commands directly
✅ **Git Integration**: Commit and push changes instantly
✅ **Extensions**: Hugo, Markdown, Live Server pre-installed

## 🔧 Fix CSS Loading (in Codespaces)

### Step 1: Check Theme Assets
```bash
# Check if theme CSS exists
ls -la themes/hugo-brewm/assets/css/
ls -la themes/hugo-brewm/static/css/
```

### Step 2: Force Asset Rebuild
```bash
# Clean and rebuild
hugo mod clean
rm -rf public resources
hugo server -D --bind=0.0.0.0
```

### Step 3: Debug CSS Path
```bash
# Check what's generated
hugo --minify
ls -la public/css/
```

## 🎨 Live CSS Editing

1. **Edit**: `assets/css/custom.css`
2. **Save**: Auto-reload in preview
3. **Commit**: Changes push to GitHub → Cloudflare Pages

## 🚨 If CSS Still Missing

Add this to `config.toml`:
```toml
[params]
  custom_css = ["css/custom.css"]
```

## 📱 Mobile Preview

Codespaces gives you a public URL for testing on mobile devices!

---

**Next Steps**: Launch Codespaces and I'll guide you through fixing the CSS loading issue interactively!