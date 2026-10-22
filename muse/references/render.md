# Render: the product as a real object

A physical product is rendered, not drawn in CSS. In every run on record a drawn re-creation of a real thing lost to the real thing, and a board whose cards show grey blocks where the product should be is judged on the blocks. The object exists before the board; the board shows it; the sketches reuse it.

## When what

- **Blender** (script + launcher): any physical object where light, material and reflection carry the desire: a device, a pack, a glass, a tablet. Produces poses, sequences, a `.glb`.
- **three.js with the `.glb`**: when the visitor operates the object: drags a hinge, turns it, opens it. The same script exports the model; the site animates it.
- **Frame sequence on a canvas**: when a gesture is driven by time or scroll (a fold opening). The script renders N frames of one parameter from the scene's own camera with the scene's own screens (for example a `--seq --seq-screens <set>` flag); the page draws them. One sequence per direction that moves the object; never a cross-dissolve between poses shot from different cameras. In a comp, 48 PNGs are fine; in a build, encode the sequence as a video or a WebP sprite.
- **three.js route, details**: vendor three.js and the loaders into the comp folder (no CDN at runtime); Chromium blocks module imports and `fetch` of the `.glb` from `file://`, so a small Node script embeds the `.glb` and textures as base64 in a `data.js` the page loads with a plain script tag. Drive the fold by rotating the moving half (and the hinge cover by half the angle); swap screen textures by posture with a short cross-fade; `preserveDrawingBuffer: true` for screenshots.
- **HTML / SVG / CSS**: flat UI, screens, diagrams, data graphics, type. Never a fake photograph.

## The pattern

A structure that has worked in practice:

- `blender/<slug>.py` builds the whole scene from scratch from dimensions declared as constants at the top of the file (metres, in the object's real size), in Blender's Python. No hand-edited `.blend` as a source of truth; the script is the truth and the `.blend` is a by-product saved next to it.
- `blender/<slug>.cmd` (or `.sh`) is the launcher: `blender --background --factory-startup --python <slug>.py -- <flags>`, with the full path to Blender on your machine. Flags after `--` go to the script.
- Flags: `--preview` (half resolution, few samples, denoised, output to `blender/render/` or the lab's `build/assets/`), `--no-render` (only save the `.blend` and export the `.glb`), `--glb` (export for the site), `--seq` (the frame sequence).
- Finals go to `design-lab/<run>/build/assets/` (`poses/`, `seq/`, `screens/`, `<slug>.glb`).
- The script prints what it wrote, the size of each image and the time it took; on a background render that log is the report.

## Outputs

- **Poses**: PNG with alpha (`film_transparent`), the floor as a shadow catcher so only the contact shadow comes along. A device modelled from a page's published figures is a likeness, not a replica (two diagonals do not pin the bezels); label it "rendered from published dimensions". One file per state the directions need (closed, edge-on, half-open, flat, in hand). Long side 1600 px for previews, 3200 px for finals.
- **Sequence**: N frames of one parameter (a hinge angle 0→180°, a lid, a tablet falling), numbered, same alpha, for a scroll-scrubbed canvas. 48 frames is enough for a fold; the page interpolates nothing.
- **`.glb`**: the moving parts as separate nodes under an empty the site can rotate (a `Hinge` empty with the two halves as children). Materials exported; cameras not.
- **Contact sheet**: the sequence laid out as one image, so the owner reads pace and transitions at a glance.

## Screens on devices

Screen content is real UI, at scale, not a gradient. Write the screen as an HTML mock at the screen's pixel size, screenshot it (the project's Playwright, or the Playwright MCP served from a temporary local HTTP server such as `python -m http.server`, since that MCP refuses `file://`), and use the PNG as the emissive texture of the screen plane. One texture per orientation the poses need: a portrait texture shows sideways on a half that stands with the hinge across the frame. Keep the mocks in `build/assets/screens/`. No trademarked icons on a foreign product; generic glyphs on rounded tiles read as "a home screen" without copying one.

## Light

Product-shot light: a soft key from the upper left, a gentle fill, a soft contact shadow on the floor. Transparent background, so the render sits on any page colour the direction chooses. No glows, no bloom, no coloured halos.

## Budget

Preview poses are minutes: 64 samples, denoised, half resolution, run in the background while the list is written. Finals and the sequence are made only for the directions the owner picked. A render that takes longer than the list to write is a final, not a preview; drop samples before dropping the pose.
