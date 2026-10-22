# Comp brief — template

Fill this in once per run, save it as `<lab>/comps/BRIEF-common.md`, and give every comp agent its path plus its own direction (the wide-list entry, the jury's WANT line, the seed, the folder, which poses or sequences to view). The rules below stay identical across agents; that is the point. Proven on a four-comp run: four parallel agents, one shared brief, short prompts.

```
# Comp brief — common rules (<target>, <date>)

## Decided (do not propose changing)
- Read `../fence.md`: locks, principles, audience, truths, clichés.
- Type: <locked faces, with the stand-in for this machine>. H1 <weight, tracking>, one H1 per viewport, one line of copy.
- Copy in <language>. Facts only from the fence's PRODUCT TRUTHS.
- The end state of the first viewport carries: <nav, eyebrow, H1, availability or price, the action, exactly as the fence and the mode require>. Nothing else.
- Design system: link `../<site>-ds.css` (or the project's tokens) in every comp and use its classes; a comp positions them and never restyles them. During the moment a headline may animate from another size; the end state is exactly the system's.
- Background: <the token for this comp, assigned in its own brief by its idea; a seed never picks it>. No gradients, no glows, no blurred blobs.
- No person drawn in code. Where the direction needs a photograph, show a neutral slot with a caption starting "P ·", and keep the product as the protagonist.

## Assets
- Poses: <list, one line each: what the pose shows>.
- Sequences: <folder, frame count, parameter range, camera, screen set>.
- Model: <.glb path, node names, how the moving part rotates>.
- Screens: <textures and their HTML sources>.
- Do not edit the render script unless your own brief says you own it.

## Build
- Your folder: `comps/<nn>-<slug>/`; the page is `index.html`, one file, inline CSS and JS, no framework, assets referenced relatively; any library vendored into your folder (no CDN at runtime).
- 5–6 s, autoplay, "Replay" after the end; `prefers-reduced-motion: reduce` shows the end frame.
- Seeking for recording: `#t=<seconds>` renders exactly that moment and holds it (WAAPI: set `currentTime` on `document.getAnimations()` and pause; canvas or WebGL: one time variable drives everything, render once). Images loaded and sized before the frame is drawn.
- 1440×900: the product dominates. 390×844: the composition stacks, 16 px gutters, no horizontal scroll.
- If the moment needs an in-between the renders do not have (a turn, a fold from this camera), ask for it in your report instead of cross-dissolving two poses.
- Commit to the direction fully. A safer rendition is a failure, not a compromise.

## Record
<the working headless browser command for this machine, with the swiftshader flags for WebGL>
- 1440×900 at eight evenly spaced times → `frames/1440-00.png` … `07`
- 390×844 at four times (start, two beats, end) → `frames/390-00.png` … `03`
- `contact.html`: white, 1600 px wide, the eight 1440 frames 4×2 with times, the four 390 frames beneath, 1 px hairlines; shot to `contact.png`. View it; fix anything clipped, missing or off-timing; re-record.

## Report (under 10 lines)
Paths (index.html, contact.png), the moment in one sentence as it actually plays, the background and why in one line, one risk, any in-between you need from the render pass.
```

## Packing

When the comps go into one offline file, the packer inlines the shared stylesheet into each comp (the font inside is already a data URI), normalises line endings before exact replacements, and fails loudly when an expected string is missing.

## The viewer

After the comps, write `comps/index.html`: one page, each comp live in an iframe scaled from 1440×900 to the card width, with its hook, type, jury total, links to open it full size and to its contact sheet, and one honest note per comp (which parts are photo slots, which in-betweens are faked, how heavy it is). No order of preference on the page.
