# aussieveen.github.io

Personal portfolio and CV site for Simon McWhinnie, built with [Zola](https://www.getzola.org/) and hosted on GitHub Pages.

## Stack

- **Zola** — static site generator
- **SCSS** — compiled by Zola, using the Nord colour palette
- **Inter** + **JetBrains Mono** — fonts via Google Fonts
- **GitHub Actions** — auto-deploys to GitHub Pages on push to `main`

## Structure

```
content/        # Markdown pages (_index.md for homepage, cv.md for CV)
templates/      # Tera templates (base.html, index.html, cv.html)
sass/           # SCSS stylesheets (main.scss, cv.scss)
static/         # Static assets (JS, GIFs)
config.toml     # Site config and all content data
```

All content — bio, experience, skills, projects — lives in `config.toml` under `[extra]`. The templates read from there, so most updates only require editing that one file.

## Local development

```bash
zola serve
```

Opens at `http://127.0.0.1:1111`. Reloads on file changes.

## CV

The CV is a separate print-optimised page at `/cv/`. To export as PDF: open it in Chrome, `File → Print → Save as PDF`, paper size A4, margins None.

## Deployment

Pushing to `main` triggers the GitHub Actions workflow (`.github/workflows/deploy.yml`), which builds the site with Zola and pushes the output to the `gh-pages` branch.
