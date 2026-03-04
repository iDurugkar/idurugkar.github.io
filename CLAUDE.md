# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal academic website for Ishan Durugkar (Research Scientist at Sony AI), built with Jekyll using a customized fork of the [academicpages](https://github.com/academicpages/academicpages.github.io) template (based on Minimal Mistakes). Deployed to GitHub Pages at `https://idurugkar.github.io`.

## Commands

### Local Development
```bash
bundle install                        # Install Ruby dependencies
bundle exec jekyll liveserve          # Serve locally at localhost:4000 with live reload
bundle exec jekyll serve --config _config.yml,_config.dev.yml  # Serve with dev config
```

### JavaScript Assets
```bash
npm install                           # Install Node.js dependencies
npm run build:js                      # Minify JavaScript files
npm run watch:js                      # Watch and rebuild JS on changes
```

## Architecture

### Content Collections
- `_pages/` — Main site pages (about, publications, CV, thesis, talks)
- `_publications/` — Individual publication markdown files with YAML frontmatter
- `_talks/` — Talk/presentation entries
- `_teaching/` — Teaching materials

### Templates & Styling
- `_layouts/` — HTML layout templates (Liquid templating)
- `_includes/` — Reusable template partials
- `_sass/` — Modular SCSS stylesheets (18 files)

### Configuration
- `_config.yml` — Main Jekyll config: site metadata, author profile, social links, plugins, collection definitions, layout defaults
- `_config.dev.yml` — Dev overrides: sets `url: http://localhost:4000`, disables analytics, expands SASS output
- `_data/navigation.yml` — Controls which pages appear in the nav menu
- `_data/ui-text.yml` — UI string overrides

### Bulk Content Generation
`markdown_generator/` contains Python/Jupyter scripts to generate markdown files from TSV data:
- `publications.tsv` + `publications.py` → `_publications/*.md`
- `talks.tsv` + `talks.py` → `_talks/*.md`

Run these scripts when adding multiple publications or talks at once instead of creating individual markdown files manually.

### Navigation
Pages are enabled/disabled in `_data/navigation.yml`. Talks, Teaching, Portfolio, and Blog are currently commented out.

### Publication/Talk Frontmatter
Each `_publications/*.md` file uses YAML frontmatter with keys like `title`, `date`, `venue`, `paperurl`, `citation`. See existing files for the expected format.
