# Portfolio — Vishwanath Sanapur

Static site. No build step, no dependencies, no framework.

```
portfolio/
├── index.html
├── styles.css
├── main.js
└── README.md
```

## Run locally

```bash
python3 -m http.server 8777
# open http://127.0.0.1:8777
```

## Content sources

Every fact on the page is traceable:

| Section | Source |
|---|---|
| Commit counts, stars, repo names, descriptions | GitHub API — `github.com/AceMythos` |
| CGPA, semester, certifications, training, contact | `resume_it.tex` / `resume_it_v2.pdf` |
| Skills, availability window | Same resume |

No invented metrics. If you cannot verify a number, do not add it.

## Editing

- **Projects** — each `<article class="card">` in `index.html`. Add `card--wide` to make one span two columns.
- **Commit counts** — the chart bars use `style="--v: 73%"`. Recompute as `commits / 122 * 100`.
- **Colours** — top of `styles.css`. One accent only (`--accent`). Dark and light are both defined; dark is the default.
- **Theme** — the toggle stores the choice in `localStorage` under `vs-theme`.

## Deploy to GitHub Pages

```bash
cd portfolio
git init
git add .
git commit -m "portfolio"
git branch -M main
git remote add origin https://github.com/AceMythos/portfolio.git
git push -u origin main
```

Then: repository **Settings → Pages → Source: Deploy from a branch → main → / (root)**.

Live in about a minute at `https://acemythos.github.io/portfolio/`.

For a custom domain or root-level hosting (Netlify, Vercel, Cloudflare Pages), just drag the folder in — it is static HTML.

## Known gaps

- **No photograph.** The hero uses a live commit chart built from real GitHub data instead of stock imagery. If you want a portrait, drop `assets/portrait.jpg` in and add an `<img>` to the hero.
- **No favicon.** Add `favicon.svg` and link it in `<head>`.
- **No OG image.** Social previews currently show text only.
