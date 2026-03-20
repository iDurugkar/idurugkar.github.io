# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal academic website for Ishan Durugkar (Research Scientist at Sony AI), built with **Zola** using the **Apollo** theme. Deployed to GitHub Pages at `https://idurugkar.github.io` via GitHub Actions.

- Theme: [Apollo](https://github.com/not-matthias/apollo) (git submodule at `themes/apollo/`)
- Framework: [Zola](https://www.getzola.org/) static site generator (Rust)

## Commands

### Local Development
```bash
zola serve          # Serve locally at http://127.0.0.1:1111 with live reload
zola build          # Build to public/
```

## Architecture

### Content
- `content/_index.md` — Homepage (bio)
- `content/research.md` — Research areas page
- `content/thesis.md` — PhD thesis page
- `content/publications/_index.md` — Publications listing (uses custom template)
- `content/publications/*.md` — Individual publication entries
- `content/blog/_index.md` — Blog/writing section
- `content/blog/*.md` — Individual blog posts (LaTeX via MathJax, enabled globally)

### Templates & Styling
- `templates/index.html` — Homepage override (renders bio only, no post list)
- `templates/publications.html` — Custom publications listing template
- `static/custom.css` — Style overrides (publications, bio photo, research areas)
- `themes/apollo/` — Apollo theme (do not edit; override via root `templates/`)

### Configuration
- `config.toml` — Main Zola config: site metadata, nav menu, social links, theme settings
  - `[extra].theme = "toggle"` — light/dark toggle
  - `[extra].mathjax = true` — MathJax enabled globally (for blog posts with LaTeX)
  - `[extra].menu` — nav items (publications, research, blog, cv)
  - `[extra].socials` — social icons (github, twitter, google-scholar)

### Static Assets
- `static/images/` — Images (profile photo, etc.)
- `static/files/` — PDFs (CV, papers)
- `static/custom.css` — Loaded via `[extra].stylesheets`

### Deployment
- `.github/workflows/deploy.yml` — Builds with Zola and deploys to GitHub Pages via Actions
- Requires GitHub Pages source set to "GitHub Actions" in repo settings

### Publication Frontmatter
Each `content/publications/*.md` uses TOML frontmatter:
```toml
+++
title = "Paper Title"
date = 2021-10-18
description = "One-line excerpt shown in the publications list"

[extra]
venue = "NeurIPS 2021"
paperurl = "https://arxiv.org/abs/..."
+++
```

### Blog Post Frontmatter
```toml
+++
title = "Post Title"
date = 2024-01-15
description = "Brief summary"
[taxonomies]
tags = ["reinforcement-learning"]
+++

Use `$inline math$` and `$$display math$$` — MathJax renders both.
```
