---
name: muse
description: Manual-only creative design direction that stays inside the project's design system. Run it with /muse when you want an original idea for a page, section or component instead of the template answer.
version: 1.2.0
user-invocable: true
disable-model-invocation: true
argument-hint: "[target: page, section, component, or URL] [optional steer]"
---

# Muse

Muse finds an idea that sells and builds it without breaking the project's design system. The two goals conflict only when originality is searched in the wrong place. A model asked for "something more original" changes the palette and the typeface, because those are the cheapest levers. A model asked for "an idea" dresses the page as a boarding pass or a tide table, because a costume is the cheapest idea. Both lose to a page where the product does its one thing in front of you. Bauhaus posters share one set of faces and inks and still look nothing alike; the best product sites keep one page system and still sell each product differently. The difference is the idea: what is shown, what happens, and why the visitor wants it afterwards. Muse keeps the materials fixed and moves the idea.

Sources: Anshu Chimala, "How to turn your AI into a world-class designer" (Lenny's Newsletter, 2026-09-01); the calibration and refuse lists of Paul Bakaus's Impeccable 4.0; an audit of twelve real Muse runs, 2026-09 to 2026-10 (what was picked: the product in action, in motion; what lost: costumes, drawn re-creations, critic-driven rounds on an accepted sketch).

## Two rules that outrank everything below

1. **Locks beat ban lists.** A lock is anything the owner or the project's design system has decided: palette, faces, radii, spacing, components, theme, motion rules, stack, budgets, fixed copy, and the brand's principles (the way it shows things). Seeds, juries, critics, "AI-tell" lists and your own taste never touch a lock. "Inter is an AI tell" is a valid observation in general and void where Inter is the brand face. A lock needs a source the owner stands behind. A visual system the orchestrator picked for the owner is a proposal, never a lock.
2. **Originality lives on the free axes, and the first axis is the idea.** In order: the idea of the first viewport (the promise; how the product is shown: scale, state, whose hand, which moment; what happens in the first three seconds; why the visitor wants it afterwards), composition and scroll rhythm, what is demonstrated instead of claimed, illustration and data language, the one signature interaction, authored content and mock data, typographic delivery inside the locked face, and last a world or metaphor, only where it beats the product shown plainly. Every proposal in this skill is expressed on these axes only.

## Talking to the owner

The owner is the person the design is for: they own product logic, flows, UX and taste; you own code and technical choices. Talk in logic and scenarios, not code. Reply in the language the owner writes. Keep replies short: the decision, the reason, what you need from them. Never ask purely technical questions. Every question that touches product, taste, or scope goes through the structured question tool when one is available.

## The flow

Each step has a reference file; load it when you reach the step, not before.

### 0. Fence — [references/fence.md](references/fence.md)

Read the project's CLAUDE.md, tokens, DESIGN.md if present, the memory directory, and this skill's `taste.md` (its pulls as much as its rejects). For a URL target, capture the live page first (fence.md, "URL target"). Produce the fence: LOCKS with a source tag on each, PRINCIPLES (how the brand shows things), AUDIENCE (who feels the problem, when and where), PRODUCT TRUTHS (facts only this product has), FREE AXES written without suggesting answers, CLICHÉS (excluded) and SELLING MECHANICS (kept), the MODE. With the confirmation ask two things: does the owner already see a picture, and are there references that set the bar. Never choose a visual system for the owner; without one, ask for references or mark the locks provisional.

Route on size. A narrow refinement (a button, a spacing fix, contrast, a single state) skips straight to step 6 on the incumbent implementation. A new surface, a section, a redesign, or "make it less generic" runs the whole flow.

### 1. Wide — [references/ideation.md](references/ideation.md)

List 20 to 25 directions, one line each, of mixed idea types: the product as object, a transformation, a demonstration, a moment of use, a tension, a line, a scale fact, a social moment, a reveal, and only then a world. Each line is a hook, a picture, a three-beat moment and a reason to want, and names the audience line and the product truth it joins. The owner's own picture, if any, is line one and always featured. About a quarter of the list is seeded from an external random string; the seed picks an idea type, an audience line, a truth and a constraint, never a world and never a colour or a face. For a physical product the object is modelled and preview-rendered before the board ([references/render.md](references/render.md)), so the board shows the real thing. A fresh jury agent (not the author of the list) scores the shuffled list first as a member of the audience, then as a creative director: WANT (doubled), CLEAR, OWN, TALK, minus a cliché penalty. The incumbent is entry zero; a list where nothing beats it on WANT is re-rolled before anyone sees it. The top 3 to 4, one per idea type, become featured. The owner sees it all as an **idea board**, a local `ideas.html` in the lab folder: the fence, featured cards led by the hook and the want line with a three-frame strip of the moment, the rest as a list they can promote. They pick 2 to 4.

### 2. Sketches — [references/ideation.md](references/ideation.md)

As soon as the owner picks, a render pass makes what each pick needs (its own fold or gesture sequence from its own camera, the `.glb`, specific screens). Then for each pick a motion comp of the signature moment by an opus agent (4 to 6 seconds, the full first viewport, recorded by URL hash, laid out as a contact sheet), all agents briefed from one shared [references/comp-brief.md](references/comp-brief.md). A comp that carries the full first viewport is the sketch; the second screen is built after the reaction, for the chosen direction only. All comps are shown side by side on one local page. A direction whose photograph is its emotional core gets a stand-in image first, or is flagged as not judgeable yet. An idea is judged on its moment, not on a still. The product is shown rendered by default; a flat, drawn rendition is a second version made only when the owner asks for it.

### 3. Reaction and brief — [references/ideation.md](references/ideation.md)

Show the comps and sketches. Ask the owner to react in their own words: what pulls, what went wrong, what is missing. Generalizable reactions go to `taste.md`; specifics go to `brief.md`. Sharpen the chosen direction, write the brief (with its idea type and its three-beat moment) and the direction contract, ask for approval.

### 4. Build

An opus builder (effort high) implements the brief in the lab folder. Production code is not touched until the owner says so. The direction contract sits at the top of the artifact; the build commits to it fully. A safer rendition of the chosen direction is a failure mode, not a compromise.

### 5. Critic — [references/critic.md](references/critic.md)

One round after the build, by default. Further rounds only when the owner asks: the record shows critic-driven rounds making an accepted direction worse. Each round: screenshot the current state and lay out the moment as a contact sheet; spawn a fresh opus critic whose context holds only those, the locks, the principles, the tells list and the quality references. Never the code, never earlier critiques. It names the aesthetic it reads, says what the audience member feels and wants after the first viewport, says how a top studio would execute this system, lists at most five specific gaps with locations, flags tells, and scores out of 10. Log every round to `critic-log.md`. Report the score and the critique to the owner; the owner decides whether another round runs.

### 6. Finish — [references/finish.md](references/finish.md)

Restraint pass (every element has a job or goes), tells check, the project's own verification commands, before/after for the owner with one paragraph in plain logic. Move into production only on the owner's go. Append to `taste.md`: reactions that generalize, and which idea types were picked and where they came from. Write `muse-notes.md`: where the method helped and where it got in the way; it feeds the next revision of this skill.

## Lab folder

All work-in-progress lives in `<project>/design-lab/<yyyy-mm-dd>-<slug>/`: `refs/`, `fence.md`, `wide-list.md`, `jury-input.md`, `jury.md`, `ideas.html`, `sketches/`, `shots/`, `brief.md`, `build/` (with `assets/` for renders and sequences), `critic-log.md`, `muse-notes.md`. Add `design-lab/` to `.git/info/exclude` (never to the repo's `.gitignore`; that file belongs to the team). Keep the folder after the run; it is the record of why the direction was chosen.

## Models and agents

- Jury: `opus`, effort high, a fresh agent that did not write the list.
- Device model (the Blender script, when the product is physical): `opus`, effort high.
- Sketch layout: `sonnet`, effort medium, narrow brief, one sketch each, short structured report (path, the moment in one sentence, one risk). Signature-moment comp: `opus`, effort high.
- Builder: `opus`, effort high.
- Critic: `opus`, effort high, a new agent every round.
- The orchestrating session never sketches, judges or critiques itself; the point of the fresh context is objectivity, and a session that wrote the list or the code will defend it.

## Screenshots

Prefer the project's own Playwright (`npx playwright screenshot --viewport-size=1440,900 --full-page <url-or-file> <out.png>`, then `390,844`). For frame-by-frame capture of comps use a headless Chromium that writes a screenshot at any window size; Playwright's chromium headless shell works from the command line (`chrome-headless-shell --screenshot=<out> --window-size=W,H --hide-scrollbars --virtual-time-budget=5000 <url>#t=<s>`, plus `--use-angle=swiftshader --enable-unsafe-swiftshader` for WebGL). Test the browser once before a run: some headless modes write nothing, and Chrome's new headless clamps windows to a 500 px minimum, so it cannot shoot 390. Fall back to the Playwright MCP tools when the project has no Playwright; that MCP refuses `file://`, so serve the lab folder from a temporary local HTTP server (`python -m http.server <port>`, stopped afterwards) and shoot `http://localhost:<port>/...`. Sketches are standalone HTML files and need no build step. If the build needs the dev server, start it in the background and record how to stop it. A moment is recorded as a video or a frame series and laid out as one contact sheet, so pace and transitions can be read at a glance.

## Rendering

See [references/render.md](references/render.md). A physical product is rendered (Blender, the project's script-and-launcher pattern), not drawn in CSS: in every run on record a drawn re-creation lost to the real thing. Flat UI and diagrams stay in HTML and SVG. Interaction with the object (drag, rotate, a fold driven by scroll) goes through a `.glb` or a frame sequence from the same script.

## Image and video generation

Off by default. When an `OPENAI_API_KEY` (or a harness-native image tool) is present, directions can be visualized as comps before building and authored imagery can replace code-drawn placeholders; read the note at the end of ideation.md. Without a key, imagery is rendered or drawn in code and marked as such; do not fake photography with gradients. Never store keys in the repo.

## What Muse is not

Not a taste transplant: it carries no palette, no faces, no "premium" look of its own. Not a scroll-mechanics playground: the project's motion rules are locks. Not a copy rewrite tool: copy changes only where the brief allows and only in the product's own language; on a Persuade surface the H1 is a free axis unless the fence locks it. Not a costume shop: a world or a metaphor is the last axis, never the first.
