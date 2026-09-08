# JSG Hohe Warte — Website

Hugo-basierte Website der JSG Hohe Warte (Jugendspielgemeinschaft). Statisch generiert, Deployment via GitHub Pages.

## Projektstruktur

```
config.toml              Hugo-Site-Konfiguration
content/                 Seiteninhalte (Sections/Pages als Markdown)
layouts/                 Hugo-Templates
static/                  Statische Assets (ohne Verarbeitung übernommen)
assets/jsg/              Design-System-Artefakte (siehe Hinweis unten)
.github/workflows/       CI/CD (Build & Deploy nach GitHub Pages)
```

## ⚠️ Generierte Design-System-Dateien

`assets/jsg/tokens.css` und `assets/jsg/jsg-components.css` sind **generierte Artefakte**
aus den Paketen `@jsg/tokens` bzw. `@jsg/css` des Design-Systems **jsg-ui**.

**Diese Dateien dürfen nicht von Hand bearbeitet werden** — Änderungen gehen beim nächsten
Sync verloren. Stattdessen Änderungen im `jsg-ui`-Repo vornehmen und anschließend
synchronisieren:

```bash
npm run sync
```

Das erwartet ein lokal ausgechecktes `jsg-ui`-Repo als Sibling-Verzeichnis (`../jsg-ui`).

## Lokale Entwicklung

```bash
hugo server -D
```

Danach [http://localhost:1313](http://localhost:1313) öffnen.

## Deployment

Push nach `main` löst den GitHub-Actions-Workflow (`.github/workflows/deploy.yml`) aus,
der die Seite mit Hugo baut und `public/` auf den `gh-pages`-Branch veröffentlicht.
