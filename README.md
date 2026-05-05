# Mark 1 — ETAD 130 Final Project Portfolio

Source for the portfolio site documenting Bogdan Mironov's ETAD 130 final project — a 1916-silhouette tracked vehicle with a printed bevel-gear differential, driven by an Arduino through a single NEMA 17 stepper.

**Live site:** https://mironovb.github.io/Mark1/

## Stack

- Jekyll 4.3 (static site generator)
- GitHub Actions (build + deploy)
- GitHub Pages (host)

## First-time deploy setup

After the initial push to `main`, the site needs Pages turned on once:

1. Open the repo on GitHub.
2. Go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to **GitHub Actions**.
4. Wait ~2 minutes; check the **Actions** tab for the green check on the `Build and deploy Jekyll site` workflow.
5. The live URL will appear under Settings → Pages.

The workflow re-runs on every push to `main` and can be triggered manually from the Actions tab via **Run workflow**.

## Layout

```
_config.yml                 site configuration
_data/                      structured data (parts, dimensions, timeline, etc.)
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
index.md                    landing page (all sections)
.github/workflows/jekyll.yml  build + deploy
```

`information/` and `drawings/0..6.jpg` (the source-of-truth deck content and original drawing JPGs) are kept in the repo for traceability. They are referenced from the build via the renamed copies under `assets/`.

## Editing content

Most content lives in `_data/*.yml`. Edit there first; the page templates render from those files.

- Hero stats → `_data/stats.yml`
- BOM → `_data/parts.yml`
- Dimension comparison → `_data/dimensions.yml`
- Print + assembly times → `_data/timeline.yml`
- Mass + cost → `_data/filament.yml`
- Design changes → `_data/changes.yml`
- Limitations → `_data/limitations.yml`
- Future improvements → `_data/future.yml`
- References → `_data/references.yml`
- Rubric self-check → `_data/rubric.yml`

Long-form prose (the "design journey" subsections, the "what didn't work" reflection, the per-section ledes) lives in `index.md` directly.

## How preview works

The GitHub Action is the source of truth. Push to `main` and check the Actions tab — the build artifact is what ends up on Pages. There is no local-build step in this workflow.
