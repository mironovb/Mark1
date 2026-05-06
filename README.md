# Mark 1 - ETAD 130 Final Project Portfolio

Source for the portfolio site that documents Bogdan Mironov's ETAD 130 final project. The build is a 1916 silhouette tracked vehicle with a printed bevel gear differential, driven by an Arduino through a single NEMA 17 stepper.

**Live site:** https://mironovb.github.io/Mark1/

## Stack

- Jekyll 4.3 (static site generator)
- GitHub Actions (build and deploy)
- GitHub Pages (host)

## First-time deploy setup

After the initial push to `main`, Pages needs to be turned on once:

1. Open the repo on GitHub.
2. Go to **Settings, then Pages**.
3. Under **Build and deployment**, set **Source** to **GitHub Actions**.
4. Wait about 2 minutes. Check the **Actions** tab for the green check on the `Build and deploy Jekyll site` workflow.
5. The live URL will appear under Settings, then Pages.

The workflow re-runs on every push to `main` and can be triggered by hand from the Actions tab via **Run workflow**.

## Layout

```
_config.yml                 site configuration
_data/                      structured data (parts, dimensions, timeline, and more)
_includes/                  reusable component partials
_layouts/                   page templates
_sass/_portfolio.scss       all custom styles
assets/css/main.scss        SCSS entry point
assets/images/              photos, renders, diagrams (renamed from source)
assets/drawings/            sheet-1.jpg through sheet-7.jpg
drawings/index.md           gallery
drawings/sheet-N.md         one full page per drawing sheet
parts/index.md              full BOM
process/index.md            print and assembly photo log
media/                      videos and extra build photos
index.md                    landing page (all sections)
.github/workflows/jekyll.yml  build and deploy
```

`information/` and `drawings/0..6.jpg` (the source of truth deck content and the original drawing JPGs) stay in the repo for traceability. They are referenced from the build via the renamed copies under `assets/`.

## Editing content

Most content lives in `_data/*.yml`. Edit there first. The page templates render from those files.

- Hero stats: `_data/stats.yml`
- BOM: `_data/parts.yml`
- Dimension comparison: `_data/dimensions.yml`
- Print and assembly times: `_data/timeline.yml`
- Mass and cost: `_data/filament.yml`
- Design changes: `_data/changes.yml`
- Limitations: `_data/limitations.yml`
- Future improvements: `_data/future.yml`
- References: `_data/references.yml`
- Rubric self-check: `_data/rubric.yml`

Long form prose, like the "design journey" subsections, the reflection text, and the per section ledes, lives in `index.md` directly.

## How preview works

The GitHub Action is the source of truth. Push to `main` and check the Actions tab. The build artifact is what ends up on Pages. There is no local build step in this workflow.
