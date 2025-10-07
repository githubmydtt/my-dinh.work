Hugo site skeleton for `my-dinh.work` (minimal files only)

What's included
- `config.toml` — minimal site config (baseURL, theme = "hugo-brewm")
- `.gitmodules` — points the theme submodule to https://github.com/foxihd/hugo-brewm.git
- `content/_index.md` — minimal home content
- `static/CNAME` — contains `my-dinh.work` (optional for Cloudflare Pages)
- `.gitignore`

Why this minimal approach
- The chosen theme (`hugo-brewm`) is large and maintained upstream. To keep this folder minimal I configured it as a git submodule instead of copying theme files.

Quick next steps (PowerShell commands)

1) Install Hugo Extended ✅ COMPLETED
```powershell
# Hugo Extended v0.151.0 is now installed at C:\Hugo\bin\hugo.exe
# Use full path or restart PowerShell to use 'hugo' command
C:\Hugo\bin\hugo.exe version
```

2) Initialize git, add theme as submodule, and run locally ✅ COMPLETED
```powershell
# Git configured with user: githubmydtt
# Theme submodule added successfully
# Hugo dev server is running at http://localhost:1313

# To restart the dev server later:
cd "D:\00000 RMIT MASTER OF A.I\0. Projects\5. My-dinh.work\my-dinh-site"
C:\Hugo\bin\hugo.exe server -D --minify
# Open http://localhost:1313
```

3) Push to GitHub and connect to Cloudflare Pages ⏳ NEXT STEP
```powershell
# Step 3a: Create a GitHub repo
# Go to https://github.com/new and create a repo named "my-dinh-work"
# Make it public (required for free Cloudflare Pages)

# Step 3b: Push to GitHub
cd "D:\00000 RMIT MASTER OF A.I\0. Projects\5. My-dinh.work\my-dinh-site"
git remote add origin https://github.com/githubmydtt/my-dinh-work.git
git branch -M main
git add .
git commit -m "chore: add hugo-brewm theme"
git push -u origin main
```

4) Configure Cloudflare Pages
- In Cloudflare dashboard, Pages → Create a project → Connect your Git provider and pick this repo.
- Build settings:
  - Framework: Hugo
  - Build command: hugo
  - Build output directory: public
- Add the custom domain `my-dinh.work` in Pages after the first successful deploy. Cloudflare will manage TLS automatically.

Notes
- If the theme requires Node tooling or additional build steps, follow the theme README after cloning the submodule.
- I did not copy the theme into this folder; the `.gitmodules` file instructs git to fetch it. This keeps the folder minimal per your request.

If you want, I can:
- initialize the git repo here and add the submodule for you (requires network access from this machine), or
- fetch the theme files into `themes/` (this will add more files).

Tell me which of those you prefer and I will proceed.
