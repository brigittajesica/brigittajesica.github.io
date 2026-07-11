# Personal Website — Brigitta Jesica Kartono

A polished, single-page researcher homepage built with plain HTML + CSS (no build step).
Layout: sticky profile sidebar + content column, a dated **News** feed, **Publications** with
clickable titles, and a tagged **Experience** timeline. Light/dark mode included.

## Files
- `index.html` — all content and structure
- `style.css` — styling, theme tokens, responsive rules
- `.nojekyll` — serve files as-is on GitHub Pages (no Jekyll processing)

## Before you publish — quick edits
A few links are placeholders. Search `index.html` for these and update them:

| What | Where (in `index.html`) | Current value |
|------|-------------------------|---------------|
| Profile photo | `.avatar` block | Monogram "BJK" — replace with an `<img>` (see below) |
| Google Scholar | `aria-label="Google Scholar"` link | `https://scholar.google.com/` |
| arXiv author page | `aria-label="arXiv"` link | `https://arxiv.org/a/kartono_b_1` |
| CV download | `.cv-btn` `href` | `#` — point to your CV PDF, e.g. `cv.pdf` |

### Adding your photo
Replace the monogram in the `.avatar` div with:
```html
<img src="profile.jpg" class="avatar-img" alt="Brigitta Jesica Kartono" />
```
then add this to `style.css`:
```css
.avatar-img { width: 132px; height: 132px; border-radius: 50%; object-fit: cover;
  border: 3px solid var(--surface); box-shadow: var(--shadow); }
```

## Preview locally
Open `index.html` in a browser, or run a local server from this `site/` folder:
```bash
python3 -m http.server 8000
# open http://localhost:8000
```

## Deploy to GitHub Pages

### Option A — Personal site at `https://<username>.github.io`
1. Create a repo named exactly `<username>.github.io`.
2. Copy the **contents** of this `site/` folder into the repo root.
3. Push:
   ```bash
   git init && git add . && git commit -m "Add personal website"
   git branch -M main
   git remote add origin https://github.com/<username>/<username>.github.io.git
   git push -u origin main
   ```
4. Live at `https://<username>.github.io` within ~1 minute.

### Option B — Project site (keep this repo)
1. Push this repo to GitHub.
2. **Settings → Pages → Source: Deploy from a branch**, branch `main`, folder `/site`.
3. Live at `https://<username>.github.io/<repo-name>/`.

## Updating content
- **News:** add an `<li>` in the `#news` section (date + text).
- **Publications:** copy a `<article class="pub">…</article>` block; the title is the link.
- **Experience:** add a `<div class="tl-row">…</div>` in `#journey`.
