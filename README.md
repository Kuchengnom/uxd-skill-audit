# UX Skills Review

A critical evaluation framework for Claude design skills. Every skill gets audited against a transparent, reproducible methodology—not stars, not hype, not the author's claim.

## What This Is

This blog evaluates Claude design skills using a **4-Dimensional Framework**: methodological rigor, transparency of limitations, testability, and maintenance sustainability. The goal: help designers and students distinguish between skills that are genuinely useful and skills that are well-packaged marketing.

Each post explains a design technique, audits an existing skill against it, and provides a reproducible scorecard.

## Quick Start

### Deploy to GitHub Pages

1. Clone or copy this repo to your local machine
2. Push to GitHub: 
   ```bash
   git push -u origin main
   ```
3. In your GitHub repo settings: **Settings → Pages → Source: Deploy from a branch → Branch: main / (root)**
4. GitHub Pages builds Jekyll automatically. Site will be live at `https://USERNAME.github.io/uxd-skill-audit`

### Local Development

```bash
# Install dependencies
gem install bundler jekyll
bundle init
bundle add jekyll jekyll-feed jekyll-seo-tag

# Start local server
bundle exec jekyll serve
# → http://localhost:4000
```

## Creating a Skill Evaluation Post

Create a new file: `_posts/YYYY-MM-DD-skill-name.md`

```yaml
---
layout: post
title: "Skill Name: Critical thesis in one sentence"
date: 2026-04-09
category: Skill-Evaluation      # or: Methodology / DESIGN.md / Tool
skill_reviewed: "author/repo-name"
verdict: caution                # exemplary | trust-with-caveats | caution | not-recommended
reading_time: 8
last_audited: "April 9, 2026"

skill_scores:
  methodological_rigor: 3
  methodological_rigor_note: "Brief explanation of rating"
  transparency: 2
  transparency_note: "Brief explanation of rating"
  testability: 1
  testability_note: "Brief explanation of rating"
  maintenance: 4
  maintenance_note: "Brief explanation of rating"

tags:
  - frontend
  - accessibility
---

Post content in Markdown...
```

## Project Structure

```
blog/
├── _config.yml              # Jekyll configuration
├── _layouts/
│   ├── default.html         # Base layout
│   ├── post.html            # Blog post with scorecard
│   └── skill.html           # Skill reference page
├── _includes/
│   ├── head.html
│   ├── header.html
│   ├── footer.html
│   └── skill-scorecard.html # 4-dimensional scorecard component
├── _posts/                  # Blog posts (YYYY-MM-DD-slug.md)
├── skills/                  # Skill reference pages
├── assets/css/main.css      # Complete stylesheet (WCAG AA)
├── index.md                 # Homepage
├── methodik.md              # The 4-Dimensional Framework explained
└── ueber.md                 # About page
```

## Color Palette (WCAG 2.1 AA)

All color combinations meet WCAG AA contrast requirements (4.5:1+).

| Token | Value | Usage |
|-------|-------|-------|
| `--color-bg` | `#F8F5F0` | Page background |
| `--color-text` | `#1C1917` | Body text (16.7:1 contrast) |
| `--color-accent` | `#5C7A5C` | Sage green, accents |
| `--color-link` | `#4A6B8A` | Muted blue, links |

## The 4-Dimensional Framework

Every skill evaluation scores on four dimensions (1–5):

1. **Methodological Rigor** — Is the underlying technique recognized and correctly ported?
2. **Transparency** — Does the skill acknowledge what it cannot do?
3. **Testability** — Are there test cases, reference outputs, or comparisons to expert work?
4. **Maintenance** — Who maintains it? Is it actively updated? Is there a succession plan?

See [methodik.md](methodik.md) for full methodology.

## Contributing

To add a new evaluation:

1. Write a post in `_posts/YYYY-MM-DD-skill-name.md`
2. Include the four scorecard dimensions
3. Provide concrete examples and red flags
4. Explain why the verdict matters for students or practitioners
5. Commit and push

## License

Content © 2026 Sebastian. Code is MIT.
