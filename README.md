# Internship Docs (Antora)

A minimal [Antora](https://antora.org/) site to get you started.

## What’s included

- `antora-playbook.yml` — site playbook
- `docs/antora.yml` — component descriptor (name, title, version, nav)
- `docs/modules/ROOT/pages/index.adoc` — starter page
- `docs/modules/ROOT/nav.adoc` — site navigation
- `build/` — output directory (generated on build)

## Prereqs

- Node.js 18+ recommended

## Build the site

Using npx (no global install required):

```powershell
npx --yes antora@latest .\antora-playbook.yml
```

The site will be generated into `build/site`. Open `build/site/index.html` in your browser.

### Alternative: Docker

```powershell
# Runs Antora in Docker, mounting the repo and writing output to build/site
docker run --rm -u $((Get-Item .).GetAccessControl().Owner.Value.Split("-")[-1]) -v "$PWD:/antora" -v "$PWD/build:/antora/build" antora/antora:3.2.0 antora antora-playbook.yml
```

## Next steps

- Add more pages under `docs/modules/ROOT/pages/`
- Organize content into additional modules (e.g., `docs/modules/user-guide/pages/...`)
- Extend the nav in `docs/modules/ROOT/nav.adoc`
- Customize the UI bundle in the playbook
