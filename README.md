# UX Skills Review

Kritische Evaluationen von Design-Skills fuer Claude — nach einem transparenten 4-Dimensionen-Rahmen.

## GitHub Pages einrichten

1. Diesen Ordner in dein GitHub-Repo pushen (Repo-Root = Inhalt dieses Ordners)
2. Im Repo: **Settings → Pages → Source: Deploy from a branch → Branch: main / (root)**
3. In `_config.yml` anpassen:
   - `url:` auf `https://DEIN-USERNAME.github.io`
   - `baseurl:` leer lassen wenn das Repo `username.github.io` heisst, sonst `/repo-name`
4. Fertig — GitHub Pages baut Jekyll automatisch

## Lokale Entwicklung

```bash
gem install bundler jekyll
bundle init
bundle add jekyll jekyll-feed jekyll-seo-tag
bundle exec jekyll serve
# → http://localhost:4000
```

## Neuen Evaluations-Post erstellen

Datei anlegen: `_posts/YYYY-MM-DD-skill-name.md`

```yaml
---
layout: post
title: "Skill-Name: Kurze kritische These"
date: 2026-04-09
category: Skill-Evaluation        # oder: Methodik / DESIGN.md / Werkzeug
skill_reviewed: "autor/repo-name"
verdict: vorsicht                 # solide | vertrauen | vorsicht | ablehnen
reading_time: 8
last_audited: "9. April 2026"

skill_scores:
  methodische_fundierung: 3
  methodische_fundierung_note: "Kurze Begruendung"
  transparenz: 2
  transparenz_note: "Kurze Begruendung"
  validierbarkeit: 1
  validierbarkeit_note: "Kurze Begruendung"
  wartbarkeit: 4
  wartbarkeit_note: "Kurze Begruendung"

tags:
  - frontend
  - accessibility
---

Post-Inhalt in Markdown...
```

## Struktur

```
blog/
├── _config.yml              # Site-Konfiguration
├── _layouts/
│   ├── default.html         # Basis-Layout
│   ├── post.html            # Blog-Post mit Scorecard
│   └── skill.html           # Skill-Referenz-Seite
├── _includes/
│   ├── head.html
│   ├── header.html
│   ├── footer.html
│   └── skill-scorecard.html # 4-Dimensionen-Scorecard
├── _posts/                  # Blog-Posts (YYYY-MM-DD-titel.md)
├── skills/                  # Skill-Referenz-Seiten (_skills Collection)
├── assets/css/main.css      # Vollstaendiges Stylesheet
├── index.md                 # Startseite
├── methodik.md              # Der 4-Dimensionen-Rahmen
└── ueber.md                 # Ueber-Seite (noch zu erstellen)
```

## Farbpalette (WCAG AA)

| Token | Wert | Verwendung |
|-------|------|------------|
| `--color-bg` | `#F8F5F0` | Seitenhintergrund |
| `--color-text` | `#1C1917` | Haupttext (Kontrast 16.7:1) |
| `--color-accent` | `#5C7A5C` | Sage-Gruen, Links/Akzente |
| `--color-link` | `#4A6B8A` | Gemaessigtes Blau |

Alle Farbkombinationen erfuellen WCAG 2.1 AA (Kontrast >= 4.5:1).
