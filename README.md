# Chathura Gunasekara: personal website

Plain static site: one HTML page, one stylesheet, no build step.

```
index.html        all content
styles.css        design tokens at the top (colours, fonts, widths)
404.html          not-found page
vercel.json       clean URLs + asset caching
assets/
  profile.jpg     portrait (square, ~320px)
  CV.pdf          linked from the header
  favicon.svg     NTT butterfly mark
```

## Preview locally

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

## Publish

1. Create a new GitHub repo (e.g. `website`) and push this folder:
   ```bash
   git init && git add . && git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/PRO-GUNE/website.git
   git push -u origin main
   ```
2. On [vercel.com](https://vercel.com) → **Add New → Project** → import the repo.
3. Framework preset: **Other**. Leave build command and output directory empty. Deploy.
4. Optional: add a custom domain under **Project → Settings → Domains**, then update `og:url` in `index.html`.

Every push to `main` redeploys automatically.

## Editing

- **New publication**: copy an `<li class="pub">` block in `index.html`; newest goes first.
- **Google Scholar / ORCID**: uncomment the placeholder in the header links.
- **Colours / fonts**: change the variables at the top of `styles.css`. Dark mode follows the visitor's system setting.

Some project links point to pages on the old site (`pro-gune.github.io/...`). Keep that repo live, or move those pages here, so they don't break.
