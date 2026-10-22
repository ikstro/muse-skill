# Finish: restraint, tells, verification, handoff

Step 6, and the whole flow for a narrow refinement. Two passes, then the project's own checks, then the owner.

## Restraint pass

Restraint is what reads as premium; a page that over-explains reads as machine-made. Inventory every element on the surface and give each one a job from this list: **inform** (carries a fact the visitor needs), **direct** (moves the visitor to the action), **prove** (demonstrates the mechanism), **brand** (a decided identity element from the locks). An element with no job is removed, not softened. Typical removals: a gradient or glow that decorates, a label that names what is already visible, a second CTA in the same viewport, a caption repeating the heading, a custom component doing what a native or existing one does better, a stat repeated from another section, an eyebrow above a section whose heading already says it.

The article's example: a calorie tracker lost its pink glows, random colored text and extra labels, and became an image-led grid on native components. The check to run on your own work: "look over the design and ask what really needs to be there."

## Tells

Defaults to notice, not bans. A tell is what a model reaches for when it stops deciding; the brief's own words, or a lock, can legitimately call for any of them. When one appears on a free axis, rewrite the element rather than softening it. When the project locks one (a kicker system, a mono face for numbers, a specific separator), it is not a tell there.

**Page scaffolds**
- Text-left / graphic-right repeated section after section; or three (or four) equal cards of icon + heading + text as the page structure. Nested cards.
- The hero-metric template: big number, small label, supporting stats, accent color.
- A tracked uppercase eyebrow over every section. One named kicker system is a decision; an eyebrow everywhere is grammar nobody chose.
- Section numbers (01 / 02 / 03), "Step 1 / Stage 2 / Phase 03", "00 / INDEX", pagination labels on tiles, when the sequence itself carries no information.
- Centered hero with pill tags underneath and stamp badges floating on the headline.
- A modal for a task that needs no interruption. Accordion FAQ by reflex. Carousel testimonials with dots.
- The same entrance animation on every section.

**Surface habits**
- Gradient text; neon outer glows; glass and blur as decoration rather than as a specific effect; zero-offset colored halos as "shadow".
- Colored `border-left` thicker than 1px on cards, list rows, callouts.
- Hairlines under every row of a long table; both top and bottom borders on each row.
- Crosshair or grid lines drawn only to feel designed; vertical rotated text; `<br>`-split italicized headlines as a default move.
- Sparklines, progress rings and rounded rectangles standing in for content; filled-track progress bars as comparison visuals on a marketing page.
- Monospace as a costume for "technical" (only for code, data, measurement; and only where the project does not already assign it).
- Pure `#000` text or background; oversaturated accents beyond the palette; a light/dark choice made by category instead of by the use scene.
- Decorative status dots before nav items, list rows, badges. A dot means live state, at most one per section.
- Middle-dot separators chained across a line ("a · b · c · d").
- Div-built fake product UI where a real replica, screenshot, or nothing would be honest. (A deliberate, responsive re-composition of real product UI with a caption is the opposite of this tell.)

**Copy**
- Filler verbs and adjectives: elevate, seamless, unleash, next-gen, game-changer, revolutionize, delve, tapestry, "in the world of".
- The template hinge: "Describe X — AI does Y" repeated across sections; em-dash as the structure of every lead sentence. Em-dashes in headlines, labels, pills, button text. Where the project has its own separator rule (arrows for routes, for instance), follow it.
- "Quietly trusted by", "From the field", "Field notes", "On our desks": performative-craftsman labels. Plain functional labels or none.
- Version stamps and build strings on a marketing page (v0.6, BETA, "last sync 4s ago"), locale and weather strips, "Scroll to explore" cues.
- Micro-meta sentences under headings explaining why the section is short.
- H1 longer than three lines.
- Mock data that is too clean: "John Doe", "Acme", 99.99%, 50%, round thousands. Names, routes, numbers should have the messiness of real records and, where the project has a canonical mock world, come from it.

**System repeats** (the ones only a whole-page read catches)
- Several vocabularies for the same set of ideas (a five-beat story named three different ways in the rail, the kickers and the hero).
- The same proof line repeated in multiple sections (a certification string four times on one page).
- Dozens of tracked micro-labels adding up to noise.
- One destination reached by three different link labels.

**Calibration** (where the brief leaves the aesthetic free; irrelevant where a lock decides)
- AI interfaces cluster in three looks regardless of subject: warm cream ground + high-contrast serif display + terracotta or signal-red accent; near-black + one neon accent + glowing edges; broadsheet-editorial hairlines + italic serif + small tracked mono labels. Landing in one of them on a free axis means the self-check failed: if someone could guess the aesthetic from the category alone, rework.
- Faces that mean you stopped looking (on a free typography axis only): Fraunces, Playfair Display, Cormorant, Lora, Crimson, Newsreader, Syne, Space Grotesk, Space Mono, IBM Plex, DM Sans, DM Serif, Outfit, Plus Jakarta Sans, Instrument Sans, and Inter-as-display. Naming one anyway needs a reason no other face satisfies; "books want a serif" is not one.

## Verification

1. Run the project's own checks from its CLAUDE.md (type check, build, screenshot widths, reduced-motion pass, performance budgets). Do not invent new ones.
2. Read the render against the direction contract, block by block, at both widths. On a Persuade surface, a first-time visitor should know what this is, why it matters and what to do within seconds.
3. Optional deterministic scan: if `npx impeccable --help` lists a `detect` command, run it on the changed files and treat its findings as leads, not verdicts (it flags the project's own motion tokens as false positives, for example).
4. Contrast: body and placeholder text at 4.5:1, large text at 3:1, unless a lock records an owner call that accepts a lower ratio on a specific element.

## Handoff to the owner

Before/after screenshots at 1440 and 390, one paragraph in plain logic (what the idea is, what changed, what was removed and why), the critic trajectory if the loop ran, and the list of anything that needs real assets or a decision. Then wait. Production files change only after the owner's go; the lab folder stays as the record.

Finally, two records.

`taste.md`: reactions from this run that generalize, dated, with the project name, under Pulls, Rejects or Wants more of; and one line under "Idea types picked": the date, the project, the idea type of the direction the owner chose, and where it came from (list, seed, owner). Keep each line short; the file is read at the start of every run.

`muse-notes.md` in the lab folder: where the method helped and where it got in the way on this run, in a few dated lines (a rule that produced junk, a step the owner skipped, a question that should have been asked earlier). The next revision of this skill is written from these notes.
