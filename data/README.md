# Snap Inc. Patent Dataset

> Part of the [Spectacles Patent Map](../README.md) repo; the interactive
> visualization built on this data lives at [`../web/index.html`](../web/index.html).

Metadata for patents and published patent applications associated with **Snap Inc.**
(formerly **Snapchat, Inc.**, renamed Sept 2016) and its subsidiary **Snap Group Ltd.** (UK).


> **Refreshed 2026-07-01:** main dataset **594 → 697 docs** (+103 newly-published);
> Spectacles subset **57 → 65 docs** (8 new family publications, incl. fresh 2025-filed
> continuations of the bending, EMG, Headware and ML-loading families, plus
> "Adaptive posegraph-based localization"). The visualization additionally shows **2
> unpublished 2025 PCT filings** (multifocal, hand-gestures) detected via USPTO ODP
> continuity data. Counts elsewhere in this README reflect the original June snapshot.

## Files

| File | What it is |
|------|-----------|
| `snap_patents.csv` | **Main dataset** — 594 unique documents (genuine Snap-owned). |
| `spectacles_patents.csv` | **Spectacles / AR-glasses subset** — 57 docs curated from the main set (see below). |
| `pdfs/` | 40 downloaded Spectacles patent PDFs (filename = `<patent_number>.pdf`). 17 of the 57 docs have no PDF hosted on Google Patents yet (mostly very recent 2025–26 filings / some CN publications). |
| [`../web/index.html`](../web/index.html) | Interactive visualization mapping the 57 Spectacles patents onto Snap's 2026 **Specs**. Fully self-contained & **offline** (real product photo, background removed, + data embedded — no internet needed). Single combined view: a **photoreal 3D model** of the glasses (the real `spec.glb`, embedded in the file; Three.js) on a hi-tech backdrop — **drag to orbit, scroll to zoom, double-click to reset** (it gently auto-rotates until you touch it). **Leader-line callouts** project from each of the 6 systems to an anchor on the actual 3D geometry and track it as you rotate; clicking a callout **smoothly recenters and zooms the view onto that component** (keeping your current angle); click one for a plain-English "challenge → progress" explainer in the sidebar plus an **innovation cluster rendered as small 3D dot-nodes** (matching the hotspot markers) that radiate from the system's numbered callout — one node per invention, linked by a leader line back to the callout pill, sized by patent-family, coloured core/enabling, labelled. Hover a node for its title, **drag it to reposition** in 3D, and **click it to load that invention's patent family into the sidebar** (no new tab). The nodes orbit with the model. Needs internet (loads the 3D library from a CDN). Two tabs: **Patent Map** (the 3D model + hotspots/clusters/timeline) and **Big Ideas (ELI5)** — a click-through deck that explains, in plain kid-friendly language, which features are a big deal and the patents behind them. The map sidebar also lists the **advertised specs.com features mapped to patents** (with ⚠ flags for features that have no matching patent). An always-visible **timeline strip** plots every patent by **publication year** across the 6 system lanes (showing the 2025–26 surge of recent filings, up to the 2026 launch); selecting a system highlights its lane. **All 57 patents appear regardless of PDF availability** — the ~17 most-recent ones have no hosted PDF yet but are still listed by title with a Google Patents link. |
| `_flagged_for_review.csv` | 6 false positives excluded from the main file (see below). |
| `recent_filings_2025.csv` | 31 Snap docs **filed in 2025** that have already published (continuations publish ~3–5 months after filing). Freshest visible filing: Dec 22, 2025. |
| `new_publications_since_scrape.csv` | 54 Snap publications that appeared after the June 2026 scrape (first page of a newest-first check) — the main dataset is a snapshot and drifts weekly. |
| `continuity_children_2025.csv` | 7 **child applications detected via USPTO ODP continuity data** on the hottest Spectacles families — incl. 2025-filed, likely never-published continuations (EMG silent speech, ML loading) whose titles/status are visible **only** through the file wrapper. Statuses are live as of July 2026. |
| `README.md` | This file. |

**Keeping current:** unpublished applications are confidential for ~18 months from priority, but
(1) weekly newest-first Google Patents queries catch publications same-day, (2) fresh **continuations
publish in ~3–5 months**, and (3) the **USPTO ODP API** (`api.uspto.gov`, free key) exposes each
family's *continuity data* — child application numbers, filing dates, titles and live prosecution
status, even for non-published applications. Snap uses non-publication requests (the B1 kind codes),
so route (3) is the only public window into part of its pipeline.

## `spectacles_patents.csv` — Spectacles (AR glasses) subset

57 documents (32 distinct inventions) selected from the main dataset as related to Snap's
**Spectacles** AR-glasses line. Adds `tier` and `category` columns. Tiers reflect confidence:

- **Tier 1 — Core Spectacles (28 docs):** directly about the AR-glasses device — eyewear
  hardware/form-factor (incl. the SoC-in-frame patent and "Headware with computer and optical
  element"), AR optics (waveguides, diffraction gratings, multifocal assemblies), XR tracking
  (frame-bending stereo correction, spatial scanning), head-worn interaction (micro hand
  gestures, head-wearable mic control), and wearable connectivity/location (antenna, location).
- **Tier 2 — Adjacent / enabling (29 docs):** microdisplay/display-driver engine (from the
  Compound Photonics / Brillian / LCoS acquisitions), neural/EMG inner-speech input,
  health-sensing smart eyewear (the Facense acquisition — these abstracts explicitly reference
  "Spectacles by Snap Inc."), and Snap software/perception that names Spectacles or head-wearables.

**Selection method:** complete-title analysis + an abstract-level keyword sweep (eyewear, temple,
near-ocular, waveguide, head-wearable, "Spectacles", etc.), with each candidate read individually.
**Deliberately excluded:** phone-based Snapchat AR Lenses/filters, generic computer-vision/3D/SLAM
patents not tied to the wearable, the Pixy **drone** product, and AI-accelerator chip patents.
**Caveat:** abstracts in the source are ~300-char snippets, so a borderline patent whose only
glasses context appears deep in the full text could be missed; the Tier-1 set is high-precision.

## Summary of `snap_patents.csv`

- **594 unique documents**
  - **293 granted patents**
  - **301 published applications**
- **By provenance**
  - **471 `snap_filed`** — filed by a Snap entity (incl. Chinese `斯纳普公司` / Korean `스냅 인코포레이티드` family members, and applications listed under inventor names).
  - **123 `other_assignee`** — surfaced under a Snap assignee query but **originally filed under a different entity**. This is a mixed bucket: genuine Snap acquisitions (IBM ~48, Gfycat, Vaporstream, Placed, Mobli, Foursquare, Metamarkets, Vertebrae, Adshir, Ariel AI, Compound Photonics, etc.), plus some co-assignments and assignee-normalization artifacts (e.g. a Canva-filed document). **Review these before relying on them.**
- **By jurisdiction** (patent-number prefix): US ~480, CN ~38, KR ~34, WO ~27 (PCT), EP ~16, AU 1.

## Columns

| Column | Description |
|--------|-------------|
| `patent_number` | Publication number incl. country prefix + kind code (e.g. `US10802683B1`). |
| `kind` | Kind code. `A1`/`A` = application publication; `B1`/`B2`/`B` = granted patent. |
| `type` | `grant` or `application` (derived from kind code). |
| `provenance` | `snap_filed` or `other_assignee` (see above). |
| `title` | Patent title. |
| `assignee` | Original assignee as listed by Google Patents. |
| `matched_assignee` | Which assignee query/queries matched (`Snap Inc`, `Snapchat Inc`, `Snap Group`, or a `|`-joined combination). |
| `inventor` | Inventor(s). |
| `priority_date`, `filing_date`, `publication_date`, `grant_date` | Key dates (may be blank if not provided). |
| `pdf` | Direct link to the PDF on Google Patents (blank for ~80 docs that have no hosted PDF). |
| `google_patents_url` | Human-readable Google Patents page. |
| `abstract` | Abstract snippet. |

## Excluded false positives (`_flagged_for_review.csv`)

6 patents from **"Insta Snap Inc"**, an unrelated 1970s hand-tool company (wrenches, pliers,
a vise) whose name contains the substring "Snap Inc". Not Snap the technology company.

## Methodology & caveats

- **Source:** Google Patents (`patents.google.com`) query API. No API key required.
  PatentsView and the USPTO Open Data Portal were either retired, unreachable from this
  environment, or require a key.
- **Queries:** assignee = `"Snap Inc"`, `"Snapchat Inc"`, `"Snap Group"`. Google's per-query
  result cap (~300) was overcome by **recursive bisection of the publication-date range** plus
  an unbounded safety pass per assignee; results were unioned and de-duplicated by publication number.
- **Caveats:**
  - "Acquired" patents are Snap-*owned* but not Snap-*filed*; filter on `provenance` if you want
    only original Snap filings.
  - Google attributes documents to a *current* normalized assignee, so a handful of co-assigned
    or recently-reassigned documents may be debatable.
  - A document and its later grant can both appear (an `A1` application + its `B2` grant) — these
    are distinct publications and both are retained.

_Generated 2026-06._
