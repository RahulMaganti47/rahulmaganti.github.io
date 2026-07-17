# Personal website

A clean, minimal, typography-led personal site — inspired by the layouts of
[mileskwang.com](https://mileskwang.com) and
[sophtang.github.io/articles](https://sophtang.github.io/articles).
Plain HTML + CSS, no build step, no dependencies. Deploys free on GitHub Pages.

## Structure

```
personal-website/
├── index.html        # Home / About · Selected papers (by year) · Background
├── writing/
│   └── index.html    # Writing — essays grouped by year (links out to Jump Crypto posts)
├── style.css         # the whole design system
└── assets/
    ├── portrait.svg  # placeholder headshot — replace with a real photo
    └── lnp.svg       # hero lipid-nanoparticle motif
```

## What to customize (search-and-replace)

Placeholders are marked so they're easy to find:

1. **Email** — replace `you@example.com` everywhere (header + footer).
2. **Social links** — the `x.com`, `scholar.google.com`, and `linkedin.com/in/YOUR-HANDLE`
   hrefs are stubs. Point them at your real profiles (or delete any you don't want).
   The **LinkedIn** URL in particular needs your real handle.
3. **Portrait** — drop a real photo at `assets/portrait.jpg` and change the two
   `portrait.svg` references in `index.html` to `portrait.jpg`. Square images look best.
4. **OpenReview papers** — in `index.html`, the three ML papers are marked `pub--todo`
   under the "Machine learning · to be dated" group. For each: paste the real
   **title, author list, and year**, bold your name as published (some appear as
   *Rohin Maganti*), move it into the right year group, and remove the `pub--todo` class.
5. **Kosha Sciences** — currently linked in the header. If you'd rather not link the
   company, delete that one `<a class="social ext" ...>Kosha Sciences</a>` line.
6. **Bio** — the one remaining `[bracketed]` bit is the machine-learning one-liner in the
   *Background* list.

The two **CycloneMSM / CycloneNTT** papers and the six **Jump Crypto** essays are already
filled in with real titles, authors, and links.

## Adding your own posts later

The Writing page currently links out to your Jump Crypto essays. To add a native,
self-hosted essay: create an HTML file in `writing/` (copy the `<head>` + `<nav>` from
`writing/index.html`, wrap your text in `<article class="article">…</article>`), then add
an `<a class="entry">` linking to it on `writing/index.html`.

## Preview locally

A server may already be running at http://localhost:8080. Otherwise:

```bash
cd personal-website
python3 -m http.server 8080
# open http://localhost:8080
```

## Deploy to GitHub Pages (free)

1. Create a repo. For `https://<username>.github.io`, name the repo
   **`<username>.github.io`** and push these files to its root.
2. Push:
   ```bash
   cd personal-website
   git init && git add . && git commit -m "Initial site"
   git branch -M main
   git remote add origin git@github.com:<username>/<repo>.git
   git push -u origin main
   ```
3. On GitHub: **Settings → Pages → Source: Deploy from a branch → `main` / `root`** → Save.
4. **Custom domain** (optional): add it under Settings → Pages and create a `CNAME` file
   in the repo root containing just the domain.

## Design notes

- **Palette:** warm paper `#f7f6f3`, near-black ink `#17171a`, one restrained indigo
  accent `#3b3fb0` used only for links/hover.
- **Type:** Newsreader (serif, display + prose), IBM Plex Sans (UI), IBM Plex Mono (meta).
- Responsive, keyboard-accessible (visible focus, skip link), respects
  `prefers-reduced-motion`.
