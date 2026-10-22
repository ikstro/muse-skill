# Fence

The fence is the first artifact of every run. It separates what is decided (locks) from what is open (free axes) for this specific target, says who the page is for and what only this product can prove, and names the clichés so nobody spends a direction on the page the category already ships. A run without a fence drifts: the model ends up "improving" the brand colour and the owner ends up defending the design system instead of judging ideas. A fence that suggests answers drifts the other way: the list goes exactly where the fence pointed.

## Where locks come from

Read, in this order, and tag the source next to each lock:

1. **Project CLAUDE.md** (and CLAUDE.local.md). Owner calls usually live here: brand colour, faces, theme, motion rules, banned libraries, fixed copy, CTA rules, performance budgets, replica rules.
2. **Tokens and base styles**: `src/styles/tokens*.css`, `tokens.ts`, theme files, a `DESIGN.md` if one exists. Radii, spacing scale, type scale, shadows, z-index, breakpoints.
3. **Component library**: buttons, pills, cards, frames, captions. Existing components are locks for the surfaces that use them.
4. **Memory** (`~/.claude/projects/<project>/memory/`): decisions the owner made in earlier sessions that never reached CLAUDE.md. A memory that names a rejected approach is a lock against that approach.
5. **This skill's `taste.md`**: the owner's standing preferences across projects. Rejects are soft locks: honour by default, mention when a direction deliberately bends one. Pulls are directions the list must serve (see ideation.md, quotas).

Source tags, one per lock:
- `decided (owner)`: the owner said it, here or in a file they wrote.
- `observed (url, date)`: read off a live page; the owner confirms which observed locks stay.
- `substitute`: a locked material that is unavailable here and what stands in for it (a licensed face → the closest available one).
- `assumed`: inferred by you; listed separately and confirmed before it binds anything.
- `provisional`: no visual system exists yet; the owner has been asked for references.

Never choose a visual system for the owner. A system you derived from a reference you picked is a proposal: show it under PROPOSED, get a yes, and only then write it as a lock. The record has a run where an orchestrator-chosen system was locked, built against, and thrown out the same day.

Things that look like locks and are not: the current layout of the section, the current metaphor, the current order of proof, the current illustration style, the current mock data, the current H1 on a Persuade surface. Those are the incumbent design; the incumbent is evidence of the subject, not authority over the next version. When a redesign is requested, the old look is an anti-reference and entry zero for the jury.

## Principles

Some brands are locked less by tokens than by a way of showing things. Write those as PRINCIPLES, each testable in one look: "one product as the protagonist" (not "one product in frame": a crowd of strangers' phones or a second colour of the same product is not a second protagonist), "one line of copy per viewport", "nothing that does not serve the gesture", "white space is a material, not an absence", "the product is always shown doing something". The jury and the critic check every direction against them. Principles are locks; they are not a style the list may re-skin. Write each one so that it fails only what the brand would refuse; a principle that fails the entry with the highest desire is written too tightly.

## Audience

Five lines, in the audience's own words where possible. Without them the list is derived from the product's attributes and its name, and attributes make puns, not desire.

- Who, in one line.
- The moment they feel the problem: a scene with a place and a time of day, not a persona sheet.
- What they use today instead.
- What they would show a friend if they had the product.
- What stops them buying (the fear, the doubt, the "but").

## Product truths

Three to five facts only this product has, each with a source (the owner, the page, the spec). No invented numbers, no borrowed claims. A direction must join one truth to one audience line; a truth that no direction uses is a truth the page will not prove.

## Owner's picture and the bar

Ask, in the same message as the fence confirmation:
- "Do you already see something: an image, an allegory, a reference, a page you envy?" If yes, save it to `refs/` and it becomes line one of the wide list, always featured, scored by the jury for information only.
- "Any references that set the bar?" Images, pages, videos. Save to `refs/`; a video becomes one contact sheet of frames. The jury and the critic receive them as the bar, never as something to copy.

## Free axes

For the target, list which of these are open. Most are open on a marketing surface; fewer on an operate surface where native expectations rule. Order matters: the list is derived top-down.

- **Promise / H1**: what the page claims in one line, where the fence does not lock the copy.
- **Product presentation**: scale (life size, larger, a detail), state (open, closed, mid-gesture), whose hand, which moment of use, which colour.
- **Moment**: what happens in the first three seconds, and what the visitor does.
- **Composition and rhythm**: reading order, density, scale contrast, where the quiet is, how the scroll paces.
- **Proof**: what is demonstrated instead of claimed. Which real mechanism, at what scale, doing what.
- **Illustration and data language**: how numbers, states, diagrams and mock UI are drawn, inside the locked palette and faces.
- **Signature interaction**: the one authored moment. Inside the project's motion rules.
- **Authored content**: mock names, routes, messages, cities, numbers with the right messiness. Must stay plausible and, where the project says so, derived from the canonical mock world.
- **Typographic delivery**: scale, measure, weight steps, alignment, how much text sits on a line, inside the locked faces.
- **World / metaphor**: what the section is a picture of, when a picture beats the product shown plainly. Last, not first.

Write the axes as sentences about this target that say what is open and never suggest an answer. "The hero may change how the device is shown and what happens when the page opens, but not the device's colour names" is an axis. "The name gives a lever: a notch is a cut, an index mark on a scale" is an answer; it belongs nowhere in the fence. No candidate metaphors, no puns, no favourite worlds.

## Clichés and selling mechanics

The category's defaults split in two. Name both.

**CLICHÉS (excluded)**: the specific pictures and lines this category always ships. For a supplement: a pastel gradient, a floating pack with leaves, "Unlock your focus", a row of benefit icons. For a phone: two hands holding the device on white, "Hello" as the headline, the device floating on a gradient, "headline plus photo" sections in a row. Add the predictable opposite (the brutalist / editorial flip, the black-and-neon flip). Both are already taken.

**SELLING MECHANICS (kept, must be authored)**: the things that sell in this category and are not clichés because they work. The product shown big. One promise. The price next to the action. The product doing its one thing. Excluding these by accident is how a list ends up with no direction the owner can use; the record has a run where "floating pack" was excluded and "the product as the hero" went with it.

## Mode

Pick from the surface, not the product. Persuade (visitor decides and acts: marketing, landing, campaign), Operate (visitor completes a task: app UI, admin, tools), Read (visitor understands: docs, articles), Experience (the work itself leads: portfolio, showcase). A product's landing page is Persuade even when the product is a tool. Persuade and Experience have permission for bolder composition; Operate keeps expression behind the task.

## URL target

When the target is a live page with no project behind it (a competitor, a page the owner wants to beat, a site to redesign):

1. **Capture** to `refs/incumbent-*`: full-page screenshots at 1440 and 390; the page text and section order; an inventory of its images (what each one shows: product state, hands, setting). Then the design system, from computed styles at the site's own breakpoints (for example 1440, 1024, 390): the type scale per element (eyebrow, hero headline, availability or price line, section headline, body, nav), colours, backgrounds in use, the primary button and the text link, nav heights, the logo as SVG when the page carries one. Write it twice: `refs/<site>-ds.md` (a table with the source of each value) and a shared tokens stylesheet every sketch and comp links (`comps/<site>-ds.css`), with the classes the comps will use. Faces whose licence forbids embedding are named in the stack, never embedded; an open-licence stand-in is embedded as a data URI so it loads from `file://`. This is the evidence; the fence cites it.
2. **Default split**, which the owner confirms or edits: locks = the whole visual system (faces and type scale, wordmark, palette, backgrounds, buttons, links, nav and other components), the voice and language, the product facts as published, the commercial state (whether there is a Buy, a price, a date). Free = the hero picture, the H1, the composition, the section order, the moments. A material is freed only by the owner's explicit word, and even then it is decided once for the whole run (see ideation.md, seeds).
3. **Facts** come only from the page. Anything the page does not say is marked unconfirmed and is not a truth.
4. **The incumbent is entry zero** for the jury. The bar is to beat it on WANT and OWN, not merely to differ from it.
5. **The current project's locks do not apply.** The lab folder may live in whatever project is open; its CLAUDE.md and DESIGN.md are not this target's fence.
6. **Imagery**. The sketches cannot have the page's photography. Three honest options, declared per entry: `A` the page's own images used locally as labelled stand-ins, never published; `D` the product rendered or drawn from its published dimensions and labelled "rendered" or "drawn" (render.md); `P` a new photograph is needed, shown as a neutral slot with a shot list (angle, hands, light, what is on the screens). A gradient never stands in for a photo.

## Output format

```
FENCE — <target>
Mode: <persuade|operate|read|experience>

LOCKS
- <lock> · <tag> · <source>
- ...

PRINCIPLES
- <one-look test>
- ...

AUDIENCE
- Who: ...
- Moment of the problem: ...
- Uses today: ...
- Would show a friend: ...
- Stops them buying: ...

PRODUCT TRUTHS
- <fact> · <source>
- ...

FREE AXES
- <axis>: <what specifically is open here, no answers>
- ...

CLICHÉS (excluded)
- <picture or line> · predictable opposite: <one line>

SELLING MECHANICS (kept)
- ...

PROPOSED (not locks until confirmed)
- ...

TASTE (from taste.md, soft)
- <reject or pull>
```

Show it, ask for a one-line confirmation plus the two questions (owner's picture, the bar), and save it as `fence.md` in the lab folder. In an autonomous run the fence may be confirmed as part of the run plan the owner approves; record that in the file. The confirmed fence becomes the "locks package" every later agent receives verbatim.

## Sizing the run

Skip steps 1 to 5 and go to finish.md when the request is a narrow refinement of existing code: a control, a state, a spacing or contrast fix, a single component's polish. Run the full flow for a new surface, a section-level redesign, a "less generic / more original" ask, or any request where the owner has not yet chosen a direction. When unsure, ask once.
