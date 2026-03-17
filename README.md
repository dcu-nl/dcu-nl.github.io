# Dosimetry Core Unit (DCU) Website

This repository contains the source code and content for the official DCU website.
The site is built with Jekyll (Minimal Mistakes theme) and deployed to GitHub Pages via GitHub Actions.

## What This Repository Includes

- Main website pages (Aim, Publications, Partners, Pillars, Research)
- Homepage with a dynamic Events section and featured publications preview
- Publication list generated from BibTeX using `jekyll-scholar`
- Sidebar partner logo block (RadboudUMC, ErasmusMC, TU_Delft, UMCG)
- GitHub Actions workflow for build and deployment

## Main Content Locations

- `home.html`: Homepage content and Events preview section
- `_pages/`: Main static pages of the website
- `_events/`: One Markdown file per event (collection-based)
- `_bibliography/papers.bib`: Publications source in BibTeX format
- `_data/navigation.yml`: Top menu/navigation links
- `_includes/sidebar-custom.html`: Custom sidebar content (partners logos)
- `assets/images/partners/`: Partner logo files used in the sidebar
- `assets/css/main.scss`: Homepage and custom visual styling overrides
- `_config.yml`: Site configuration, plugins, collections
- `.github/workflows/deploy.yml`: GitHub Pages deployment pipeline

## Events Workflow

Events are managed as a Jekyll collection.

1. Add a new file in `_events/` (for example `2026-04-01-example-event.md`)
2. Include front matter fields:
	- `title`
	- `publication_date` (YYYY-MM-DD)
	- `subscription_deadline` (YYYY-MM-DD)
	- `event_url` (external event page)
	- `excerpt` (short text shown on homepage)
3. The homepage automatically shows the latest 3 events.
4. Event cards include status labels based on deadline (`Open`, `Closing soon`, `Closed`).

## Publications Workflow

- Publications page: `_pages/publications.md`
- Bibliography source: `_bibliography/papers.bib`
- Rendering uses `jekyll-scholar` (configured in `_config.yml`)
- DOI links on the publications page are converted to clickable links in the page script
- Homepage shows only the latest 3 publications in a featured section

## Homepage Notes

- Hero section includes quick calls-to-action to publications and events
- Events are rendered in 2 columns: date (left) and details (right)
- Deadline text is highlighted in red for visibility
- Top masthead and sidebar are configured to stay visible while scrolling

## Local Development

Prerequisites:
- Ruby (compatible with the project Gemfile)
- Bundler

Run locally:

```bash
bundle install
bundle exec jekyll serve
```

Then open:
- `http://127.0.0.1:4000/`

## Deployment

- Deployment is handled by `.github/workflows/deploy.yml`
- The workflow runs on pushes to `master`
- GitHub Pages should be configured to use **GitHub Actions** as the source

## Notes

- This repository was adapted from a Minimal Mistakes template and cleaned to keep only project-relevant files and workflows.
- Content updates are typically done by editing Markdown files in `_pages/`, `_events/`, and `_bibliography/`.
