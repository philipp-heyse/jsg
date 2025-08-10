# Hugo Two-Level Navigation Starter

**Folders = Menu.** Place content like:
```
content/<section>/_index.md             ->  /<section>/
content/<section>/<page>/_index.md      ->  /<section>/<page>/
```
Top nav lists sections. When viewing a section or page, a second nav shows pages in that section.

## Quick start
```bash
hugo server -D
```
Then open http://localhost:1313

## Deploy to GitHub Pages
Push to `main`. The workflow builds with Hugo and publishes `public/` to the `gh-pages` branch.
It auto-detects whether this is a **user/organization site** (`<owner>.github.io`) or a **project site** and sets `baseURL` accordingly.

If you prefer to hardcode it, set `baseURL` in `config.toml` to your final URL.
