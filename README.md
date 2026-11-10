# DSC180A Methodology Assignment 4 — Task 2

A barebones Jekyll site for GitHub Pages.

## Files
- `_config.yml` — site config; sets the theme to **cayman**.
- `index.md` — the homepage (Jekyll renders this Markdown to HTML automatically).

## Publish it on GitHub Pages
1. Create a **public** repository named `DSC180A-Methodology-4`.
2. Add, commit, and push `_config.yml` and `index.md` to it:
   ```
   git init
   git add _config.yml index.md README.md
   git commit -m "Methodology 4: Jekyll site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/DSC180A-Methodology-4.git
   git push -u origin main
   ```
3. On GitHub: **Settings → Pages**, set **Source = Deploy from a branch**, **Branch = `main` / `/ (root)`**, Save.
4. Wait a minute, then visit `https://<your-username>.github.io/DSC180A-Methodology-4/`.

## Before you submit
- Fill in your **section** and **mentor** in `index.md`.
- Re-read the four brainstorm answers and make them your own — they're drafted from your Q1 wildfire project but the assignment is individual.
- (Optional) Browse other themes at <https://pages.github.com/themes/> and change the `theme:` line.

## Render locally (optional)
Needs Ruby + Jekyll:
```
gem install bundler jekyll
jekyll serve   # then open http://localhost:4000
```
