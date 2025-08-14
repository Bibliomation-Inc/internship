# Bibliomation Internship Documentation

This repository contains documentation for Bibliomation's Evergreen ILS internship program, covering environment setup, workflows, and community contribution guidelines.

## Overview

The documentation site is built with Antora and configured by `antora-playbook.yml`. The generated site is written to `build/site` and deployed to GitHub Pages at:
- https://bibliomation-inc.github.io/internship

## Local Development

### Prerequisites

- Node.js 18+
- npm (for npx)

### Build and preview

1. Install dependencies:
   ```bash
   npm ci
   ```
2. Build the site with Antora:
   ```bash
   npx antora antora-playbook.yml
   ```
3. Preview the generated site locally (port 8083):
   ```bash
   npm start
   ```
   This will serve the site at http://localhost:8083

## Adding Content

1. Create or edit AsciiDoc files in `docs/modules/ROOT/pages/`
2. Add images to `docs/modules/ROOT/assets/images/` and reference them using an Antora resource ID, for example:
   ```asciidoc
   image:ROOT:images/your-image.png[Alt text]
   ```
3. Update the navigation in `docs/modules/ROOT/nav.adoc`
4. Rebuild and preview locally before committing

## Contributing

1. Fork this repository to your GitHub account.
2. Create a feature branch for your change.
3. Make edits under `docs/` (pages, images, and nav).
4. Build and preview locally:
   ```bash
   npm start
   ```
5. Commit and push your branch.
6. Open a pull request into the `main` branch of the main repository.

## GitHub Pages Deployment

- One-time setup: Settings → Pages → Build and deployment → Source = “GitHub Actions”.
- CI uses actions/configure-pages + actions/upload-pages-artifact + actions/deploy-pages.
- Antora note: deploy-pages adds .nojekyll automatically (our playbook also injects it; redundant but safe).
- Site URL: https://bibliomation-inc.github.io/internship
  - Ensure antora-playbook.yml site.url matches this URL to avoid wrong canonical and asset paths.

## Site Structure

- `docs/` - Documentation source files
  - `modules/ROOT/pages/` - AsciiDoc content files
  - `modules/ROOT/assets/images/` - Image files
  - `modules/ROOT/nav.adoc` - Navigation definition
- `antora-playbook.yml` - Antora configuration
- `.github/workflows/` - GitHub Actions for deployment

## License

Copyright © 2025 Bibliomation, Inc.
