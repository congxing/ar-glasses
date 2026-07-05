# Patent PDF summaries — plain-English explainers

Plain-English summaries of the **40 downloaded Spectacles patent PDFs** (`../pdfs/`),
grouped by patent area. Each was read from the actual patent — full text via
extraction for the 27 text PDFs, and page-by-page (vision) for the 13 image-only
scans — not from the ~300-char abstract snippets. These are the source notes behind
the interactive "how it works" demos in [`../../web/index.html`](../../web/index.html).

Each file gives, per patent: a one-line plain-English summary, how it actually works,
an everyday analogy, why it matters for the glasses, and a confidence note; plus an
area-level synthesis (the big idea, the challenge → breakthrough arc, and an ELI5 line).

| File | Area | PDFs | The big idea |
|------|------|-----:|--------------|
| [`ar-optics.md`](ar-optics.md) | AR optics & display (waveguides) | 2 | Interleaved-rectangular gratings make the see-through image brighter and more even, and kill rainbow sun-glare |
| [`microdisplay.md`](microdisplay.md) | Microdisplay / display engine | 5 | LCoS pixels are on/off switches; timed binary-weighted flashes fake smooth 16.7M-colour images |
| [`xr-tracking.md`](xr-tracking.md) | XR tracking & spatial | 5 | The frame bends on your face; cross-check the cameras against the motion tracker to cancel it — and read the bend to tell who's wearing them |
| [`eyewear-hardware.md`](eyewear-hardware.md) | Eyewear hardware & form factor | 9 | A whole computer won't fit, so split the work across two chips and a paired phone; shrink controls to one button + LEDs |
| [`connectivity.md`](connectivity.md) | Wearable connectivity & location | 2 | The frame's own structural wire is the antenna (and heat sink); your phone is the GPS |
| [`interaction-emg.md`](interaction-emg.md) | Head-worn interaction & neural/EMG | 2 | Your index finger becomes a slider; silently-mouthed words become commands via muscle signals |
| [`health-a.md`](health-a.md) | Health-sensing eyewear (Facense) A | 6 | Inward thermal cameras read your face; a stack of corrections makes the reading trustworthy in the wild |
| [`health-b.md`](health-b.md) | Health-sensing eyewear (Facense) B | 6 | Skin-colour flush = heartbeat; posture/ambient corrections turn face-sensing into real vitals |
| [`software-perception.md`](software-perception.md) | Spectacles software / perception | 3 | Blend billboard↔headlock so content sits right; a standardized widget schema turns the glasses into a universal remote |

**Method:** `pdftotext` for extraction; vision reading for the scanned PDFs; KR/CN
patents translated from the original. Grounded in abstract + summary + claim 1 +
figures. Confidence is noted per patent (most are high; a few Facense entries are
abstract+summary level). Generated 2026-07.
