# AR Glasses — a long-term thesis

Patents, product, business, and technical deep-dives on AR glasses, one company
at a time. Each chapter reads the same hardware story through four lenses:
**business** (the strategic bet), **product** (what the device chooses to be),
**technical** (what the patents and teardowns reveal), and **application**
(what builders can ship today — the live demo is the proof).

## Chapter 1 — Snap Spectacles

An interactive 3D map of Snap Inc.'s AR-glasses patent portfolio, projected onto
the 2026 **Specs** hardware — plus the underlying curated dataset (697 Snap
documents, 65 Spectacles-specific) and the downloaded patent PDFs.

> I went through Snap's Spectacles patent history. The product strategy is
> questionable, but the technical progression is more coherent than people realize.

## Try it

Open **[`web/index.html`](web/index.html)** in a browser — it is a single
self-contained file (data and 3D model embedded; only the Three.js library
loads from a CDN).

- **Patent Map** tab — a photoreal 3D model of the glasses with leader-line
  callouts for 6 hardware systems. Drag to orbit, scroll to zoom, double-click
  to reset. Click a callout for a plain-English "challenge → progress"
  explainer and the system's innovation cluster (one 3D node per invention,
  sized by patent family; click a node to load that family in the sidebar).
- **Big Ideas (ELI5)** tab — a click-through deck explaining which features are
  a big deal and the patents behind them.
- **Timeline strip** — every patent plotted by publication year across the 6
  system lanes, showing the 2025–26 filing surge into the 2026 launch.

## Repository layout

| Path | What it is |
|------|-----------|
| `web/` | The interactive visualization (`index.html`) plus `assets/spec.glb`, an original 3D reconstruction of the glasses made by the author from public reference images (a copy is embedded in the HTML). This is the code that grows into the website. |
| `data/` | The patent dataset: curated CSVs + [`data/README.md`](data/README.md) documenting scope, methodology, and caveats. |
| `data/pdfs/` | 40 downloaded Spectacles patent PDFs (filename = publication number). Patent documents are public records — see `LICENSE` scope notes. |
| `local/` | **Not in git.** Per-project working area (video productions, essay drafts, source assets, capture variants). See `local/README.md`. |

## Roadmap

`web/index.html` is deliberately a single file today so anyone can download and
open it. Planned evolution into a proper site:

- [ ] Split the monolith: extract data JSON, styles, and modules from the inline HTML
- [ ] Host the demo (static hosting — no build step required)
- [ ] Pipeline to refresh the dataset (weekly Google Patents sweep + USPTO ODP continuity check, per `data/README.md` "Keeping current")
- [ ] Next chapters: the same four-lens treatment for other AR-glasses makers (Meta, Google/Android XR, Xreal, …), each with its own patent map and dataset

Contributions and issues welcome.

## License & affiliation

Code is MIT-licensed. Patent documents and bibliographic data are public
records (details in [`LICENSE`](LICENSE)). This is an independent research
project, not affiliated with or endorsed by Snap Inc.
