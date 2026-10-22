# Ideation: wide list, seeds, jury, board, sketches, reaction, brief

Covers steps 1 to 3 of the flow. The goal is a direction the owner recognizes as theirs and a visitor wants to act on, not one the model liked best. Two findings shape this file. Chimala's, confirmed by Impeccable's measurements (30 of 35 runs shipped the same concept across 16 prompt framings): a model's ranking of its own ideas is deterministic. The owner's, from twelve runs: when the list is derived from the product's name and attributes, every entry is a costume (the page dressed as a day planner, a tide table, a tuning fork), the jury crowns the most literal costume, and the owner brings their own idea instead, which is always of another kind: the product in action, in motion, with the felt problem turning into the benefit in front of you. The list must contain that kind of idea before the owner has to supply it.

## 1. The wide list

Ask for breadth across kinds, not depth in one. 20 to 25 directions, one line each.

### Idea types

Every entry names its type. The list must span at least six types, hold at most four entries of one type, and at most four metaphor worlds in total.

- **product as object**: the thing itself, at a scale or in a state that makes you want to pick it up.
- **transformation**: before → after in one scene; the felt problem becomes the benefit.
- **demonstration / try it**: the product does its job at real scale in front of you, or the visitor operates it.
- **moment of use**: a specific place, time and person; the product in that life.
- **enemy / tension**: the problem dramatized big; the product as the relief.
- **copy-led**: the line does the work; the picture serves one headline that means two things.
- **scale / impossible fact**: one true fact pushed to a size that stops you.
- **identity / social**: what having it says, or what it does between two people.
- **ritual / reveal**: the first switch-on, the unboxing, the opening gesture, shown as a ceremony.
- **metaphor world**: the page as a picture of something else. Allowed, last, and only where the picture beats the product shown plainly.

At least two entries serve the Pulls in `taste.md` and are tagged `(taste)`.

### Derivation

Each entry joins one AUDIENCE line (the moment of the problem, what they would show a friend, what stops them buying) to one PRODUCT TRUTH, and says which. An entry derived only from the product's attributes or its name is a pun; it may stay, tagged as a metaphor world, inside that quota. The order of derivation is the order of the free axes in the fence: promise, presentation, moment, then the rest; a world comes last.

### Entry shape

```
N. [type] «Hook / H1» — Picture: the first viewport, where the product is and how big — Moment: before / during / after, with a duration — Want: the desire or fear it touches, in the audience's words — Proof: the truth it uses — Asset: D rendered or drawn · A existing · P needs a photo
```

The Moment has three beats or the entry is a mood, not an idea; "a calm page with the device" is not a moment, "the closed device lies edge-on at life size; on scroll it opens across the whole viewport; the headline lands on the inner screen" is. On a Persuade surface the first viewport also makes the offer intelligible and shows the primary action where one exists.

### Rules for the list

- Concrete: a scene, an object, an action or a line the visitor can picture. Never an adjective ("bold", "clean", "editorial") and never a mood.
- Every entry is buildable on the locks and inside the principles: it works in the locked palette and faces, within the motion rules and the performance budget. Drop or rework any entry that needs a lock to move. A direction that "would need a darker theme" is not a direction for this project.
- The clichés and the predictable opposite from the fence are absent. The selling mechanics are allowed and authored.
- Entry zero is the incumbent (the current page, or the page being beaten), written in the same shape and scored like the rest.
- Entry one is the owner's picture, if they gave one, in the same shape, tagged `(owner)`.
- Seeded entries are tagged `(seed)`. The tags are stripped before the jury sees the list.

### Ambition templates

Use these to push past the safe register, inside the fence:

- "Freeze the best frame of this product's fifteen-second film."
- "The moment the audience would pay to have, or to avoid, shown at life size."
- "The line someone screenshots and sends to a friend."
- "The one thing only this product can do, happening in the first second."
- "If the category leader launched this tomorrow, which hero would we fear?"

## Seeds

About a quarter of the list comes from external randomness, because the author's own order is deterministic. Generate a string:

```
node -e "console.log(require('crypto').randomBytes(24).toString('base64url'))"
```

Read the string for sub-patterns: repeated characters, digit runs, the ratio of upper to lower case, a number that reads as a time or a count. A seed never picks a world, a colour or a face, and never any material (background, button, type, nav), even one the owner has freed: materials are decided once per run and shared by every direction, so that four comps differ by their idea and not by four looks. Where the owner allows several backgrounds, the brief assigns one to each direction by its idea. Each seeded entry draws one cell from three tables and one constraint:

- idea type (the list above, metaphor world excluded from seeding),
- audience line (one of the five),
- product truth (one of the three to five),
- constraint: the product is not visible · only the product is visible · the H1 is one word · the visitor's own hand · life size · exactly one interaction · no copy below the H1.

Write the entry that satisfies all four. Do not print the string in the design or on the board; it is only the dice. Each sketch agent later gets its own seed and applies it the same way inside its direction, so two sketches of similar directions still diverge.

## The jury

Twenty one-liners without pictures is a blind choice, and the author of the list ranking its own entries reproduces the argmax rut. So the featured entries are chosen by a separate judge with named criteria, and the owner sees them drawn.

Spawn one jury agent (`opus`, effort high) that did not write the list. Give it the fence (locks, principles, audience, truths, clichés), the bar references if any, and the entries in shuffled order without your numbering and without the `(seed)`, `(owner)` and `(taste)` tags. The incumbent is in the shuffle too, unmarked.

The jury reads every entry twice, in two roles, and scores:

1. As the person from the AUDIENCE block, after the first viewport:
   - **WANT** 1–5: do they want the product more than before? The jury writes the desire in that person's words, one line. 1 means "I understand it"; 5 means "I want it now".
   - **CLEAR** 1–5: within three seconds they know what this is and why it is for them.
   - **TALK** 1–5: the sentence they would say to a friend an hour later. A specific scene scores high; a mood scores 1.
2. As an executive creative director:
   - **OWN** 1–5: could a rival run this hero by swapping the logo? 5 means impossible, it only works for this product.
   - **PENALTY** 0–2: closeness to a cliché or to the predictable opposite.
   - **PRINCIPLES** yes/no: passes every principle in the fence.
   - **VIABLE** yes/no: buildable on the locks, the stated stack and the declared assets, at 390 as well as 1440.

Total = 2×WANT + CLEAR + OWN + TALK − PENALTY (maximum 25). Entries that fail PRINCIPLES or VIABLE are listed but cannot be featured.

The jury also writes one block, **What is missing**: what kind of idea the list over-represents, what it lacks (a truth no entry uses, a fear no entry answers with proof, a moment no entry shows), and which entries only a rival could not stage. The orchestrator reads it before the board and feeds it to any re-roll.

Featured = the top three or four by total with **no two of the same idea type**; ties break by dice. If no entry beats the incumbent on WANT, the list is re-rolled before the board is made; the owner is told it happened. The owner's picture, if any, is scored for information and stays featured regardless. The jury's scores stay in the lab folder (`jury.md`); the board shows the featured set and the rest as a list. The owner may promote any listed entry to a card, and that promotion outranks the jury.

## The idea board

Present step 1 as a page (`ideas.html` in the lab folder, local; publish only if the owner asks), not as chat text. Structure, top to bottom:

1. The fence in two columns: locks and principles; audience, truths and free axes. The clichés in one line underneath.
2. Featured cards, three or four, plus the owner's card when there is one, plus two riffs on the owner's picture (the same desire, a different idea type). Each card leads with the hook and the Want line, then the three beats of the moment, then a **moment strip**: three frames (before / during / after) of the first viewport at 1440 and one frame at 390, drawn on the project's tokens, with the product shown as its preview render (render.md) rather than a grey block. It is a plan of the stage, not a mockup: no real copy beyond the H1 and the CTA label. A `P` entry shows its photo slot as a neutral rectangle with the shot caption.
   Each card also lists the **assets the comp would need** (a sequence from which camera, a `.glb`, a screen texture, a photo), so the render pass can start the moment the owner picks. A `P` entry whose photograph is the emotional core (a face, a person's reaction, a hand doing the gesture) is flagged "cannot be judged as a moment until the photo exists": it gets a stand-in image before its comp (the owner's photo, an image tool, a reference used locally), or the owner decides whether to spend a comp on it. On the board the device carries such a card; in the comp it does not.
3. The remaining entries as a numbered list with their type and hook, each with a "show" checkbox. Checked entries get their card drawn on the next version of the page.
4. A re-roll control: when the owner asks for it, every shown entry is dropped and a new list is made; after two consecutive re-rolls ask what quality is missing.

Do not recommend on the board. Featured means "the jury scored it", not "the author likes it"; say so in one line on the page. Ask the owner for 2 to 4 picks and an optional one-line steer.

## 2. Comps and sketches

**Render pass for the picks.** As soon as the owner picks, list the assets each pick needs (the card already names them) and render them before the comps: every direction that moves the object gets its own sequence from its own camera, with that scene's screen content; a direction that the visitor operates gets the `.glb`; a direction that shows a specific screen gets that texture. One shared sequence is not enough: a cross-dissolve between two poses from different cameras reads as a swap, not a fold. A comp that needs nothing new starts at once.

For each pick, then, in this order.

**The moment first.** An opus agent (effort high) builds the signature moment as a motion comp: 4 to 6 seconds, HTML with CSS or the Web Animations API, or a frame sequence from render.md, on the project's tokens, with the rendered object. Record it (frame captures by URL hash, see [comp-brief.md](comp-brief.md)) and lay the frames out as one contact sheet. Give every comp agent the shared rules in comp-brief.md, filled in for this run and saved as `comps/BRIEF-common.md`, plus its own direction; the prompts stay short and the rules stay identical. A comp agent that needs an in-between the renders do not have asks for it instead of faking it. The owner judges the moment here; a still cannot carry a kinetic idea, and every kinetic idea on record was chosen over a static one.

**Then the sketch, only if the comp is not one.** When the comp already carries the complete first viewport (nav, H1, availability or price, the action), it is the sketch: show the comps and go to step 3; the second screen is built after the reaction, for the chosen direction only. Otherwise a sonnet agent (effort medium) builds one standalone HTML file with inline CSS on top of the linked tokens, real content, the rendered object and the comp embedded or linked, no framework, no build step. Target: the first viewport and one more screen, enough to judge the composition around the moment. Screenshots at 1440 and 390 into `shots/<n>-<slug>-{1440,390}.png`. Three-line report: file path, the moment in one sentence, the biggest risk.

Each agent gets: the confirmed fence verbatim; its entry and the owner's steer; its own seed and the seed procedure; the real content (paths, not paraphrase); the path to the tokens and base CSS and to the render assets; the lab folder path; the mode and its rules.

The product is rendered by default. A flat, drawn rendition is a second version made only when the owner asks. Show the owner all comps side by side on one local page (`comps/index.html`: each comp live in a scaled frame, with its contact sheet), without commentary that steers. Say plainly which parts are slots for photography and which in-betweens are faked.

## 3. Reaction, taste, brief

Ask the owner to react in their own words, per sketch, on three prompts: what pulls you, what went wrong, what is missing. Do not offer a scale, do not ask for scores. The register to aim for: "I imagined something tactile; clicky buttons. I first pictured cartoony or skeuomorphic and that feels tacky, avoid it. Gray gradients would be boring; needs texture."

Sort the reactions:

- **Generalizable** ("cartoony reads as tacky to me", "I like density that resolves into one quiet moment", "no faux-3D") goes to `taste.md` in this skill's folder, one line each, dated, with the project it came from.
- **Specific to this target** goes to `brief.md`.

Then sharpen the winning direction and write the brief.

### brief.md template

```
# Brief — <target> — <date>

## Thesis
One idea this surface owns, and the category default it refuses.

## Idea type and moment
The type from the list. The three beats (before / during / after) with durations.

## Audience line and truth
Which line of the AUDIENCE block this joins to which PRODUCT TRUTH.

## Locks and principles (from fence.md)
Verbatim list.

## Choices on the free axes
- Promise / H1: ...
- Product presentation: ...
- Composition and rhythm: ...
- Proof: what is demonstrated, at what scale
- Illustration and data language: ...
- Signature interaction: the one authored moment, within motion rules
- Authored content: what mock data is needed and where it comes from
- Typographic delivery: ...
- World / metaphor: only if one is used

## Don'ts (owner's words)
Quotes from the reaction, verbatim.

## First viewport
Exact composition: what is where, at what scale, where the primary action sits.

## Assets
Renders, sequences, photos needed (shot list), with paths or owners.

## Memory test
If someone left after one viewport, what would they describe an hour later? (If the answer is a mood, the brief is not done.)

## Open
Anything the owner still has to decide.
```

Ask for approval of the brief. Then write the direction contract at the top of the build artifact: THESIS, MOMENT, STORY (what the visitor understands, believes, does), FIRST VIEWPORT, FORM, five short blocks, 150 words at most. The finishing review audits the render against this contract.

## Image generation (only when available)

When `OPENAI_API_KEY` or a harness-native image tool is present, two extra moves become possible; both are optional and the owner is told the cost before the first call. First, visualize the approved brief as two or three compositional comps before building, and let the owner pick. Second, replace rendered placeholders with authored imagery in the build, always through a gitignored `.env.agents`, never through the repo. Without a key, render or draw imagery in code, keep it honest (no gradient standing in for a photo), and hand the owner the list of assets to author later.
