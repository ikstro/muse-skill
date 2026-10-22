# Comp brief — common rules (Lanework hero, 2026-10-22)

Every motion comp in this folder follows these rules. Your own brief adds the direction.

## Decided (do not propose changing)
- Read `../fence.md` (locks, principles, audience, truths, clichés) and `../product.md` (the fictional product and its mock world: Northfield Studio, six people, client Halden & Co.).
- **Lanework design system is locked.** Link `../lanework-ds.css` in every comp and use its classes; never restyle them locally (position and layout only). Values: `../refs/lanework-ds.md`.
  - Nav: paste `lanework-nav.html` (in this folder) verbatim as the first element of `<body>`.
  - Hero type: `.lw-eyebrow`, `h1.lw-h1` (72/76; 60 at ≤1068; 44 at ≤734), `.lw-lead` for one supporting line if the direction needs it.
  - Action: `a.lw-btn` "Start free", with `.lw-price` "$6 per person / month · free for 3" next to or under it. A secondary `.lw-link` only if the direction needs one.
  - Product UI: `.lw-panel`, `.lw-row`, `.lw-av` (a2…a6 tints), `.lw-chip` (ok / wait / late / done). Build the product's interface as real HTML; never put it in a browser frame, never tilt it, no drop shadows.
  - `<body class="lw bg-page">` (white) or `<body class="lw bg-surface">` (#f4f4f1); the background is fixed in your own brief.
  - During the moment a headline may animate in from another size or position; the end state is exactly the classes above.
- Copy in English. Facts only from PRODUCT TRUTHS T1–T6. No invented customers, logos, statistics or comparisons. Names, tasks and dates only from the mock world, consistent across the comp.
- The first viewport's end state carries: the nav, the H1, at most one supporting line, the product UI doing its job, the action with the price line. Nothing else.
- No gradients, no glows, no blurred blobs, no illustrations of people, no icon cards in threes.

## Build
- Your folder: `comps/<nn>-<slug>/`; the page is `index.html`, one file, inline CSS and JS, no framework, no network. Link `../lanework-ds.css` (it embeds the font as a data URI, so it works from file://).
- 5–6 s, autoplay, a small "Replay" text button bottom-right (12px, ink-2) after the end; `prefers-reduced-motion: reduce` shows the end frame.
- Seeking for recording: `#t=<seconds>` renders exactly that moment and holds it (WAAPI: set `currentTime` on `document.getAnimations()` and pause; or drive everything from one time variable and render once).
- 1440×900: the product UI dominates. 390×844: stacks with 16 px gutters, no horizontal scroll; the UI may simplify (fewer rows, fewer columns) but stays real.
- Interactions are welcome if the direction calls for them (click, drag, paste); the auto-play moment must work without them.
- Commit to the direction fully. A safer rendition is a failure, not a compromise.

## Record
Use this headless browser (it writes screenshots at any width):
```
chrome-headless-shell --screenshot="<absolute out.png>" --window-size=1440,900 --hide-scrollbars --virtual-time-budget=5000 "file:///<path to>/comps/<nn>-<slug>/index.html#t=<seconds>"
```
- 1440×900 at eight evenly spaced times from 0 to the end → `frames/1440-00.png` … `07`
- 390×844 at four times (start, two beats, end) → `frames/390-00.png` … `03`
- `contact.html`: white, 1600 px wide, a title line with the hook, the eight 1440 frames 4×2 with times, the four 390 frames beneath, 1 px hairlines; shot at `--window-size=1600,1500` to `contact.png`. View it; fix anything clipped, missing or off-timing; re-record.

## Report (under 10 lines)
Paths (index.html, contact.png), the moment in one sentence as it actually plays, one risk.
