# Critic loop

Step 5. A builder reviewing its own work defends its decisions; that is not a flaw of the model, it is what any author does. The fix is a second agent that never saw the code and never saw the previous critique. It judges the picture, the way a design director walks past a screen, and it judges the moment, the way a visitor meets the page.

## When the loop runs

One round after the build, by default. Further rounds only when the owner asks. The record has four critic-driven rounds taking an accepted sketch from 5 to 7 in the critic's eyes and to "the first versions looked better" in the owner's; the sketch was rolled back. Once the owner has accepted a direction, it changes on the owner's notes, and the critic is a second opinion the owner requests, not a loop that runs on its own.

## What the critic receives

Only these, nothing else:

1. The current screenshots (1440 and 390, full page or the section under work) and the contact sheet of the signature moment.
2. The locks package and the PRINCIPLES from `fence.md`, verbatim, under the heading "These are decided; do not propose changing them."
3. The AUDIENCE block from `fence.md`.
4. The tells list from [finish.md](finish.md) (section "Tells").
5. Quality references if the owner provided any (the bar from `refs/`): framed as the bar, never as something to copy.
6. The brief's thesis, idea type, moment and first-viewport blocks. Not the rest of the brief, not the contract, not the code.

Never pass: source, the previous rounds' critiques, the builder's notes, your own opinion of the current state.

## The critic's prompt

Spawn `opus`, effort high, a new agent every round. The prompt, adapted from Chimala with the fence and the audience added:

```
You are a design critic in a fresh context. You see only screenshots and a contact sheet of a design's moment, a list of decisions that are fixed, the brand's principles, a description of the person the page is for, a list of patterns that read as machine-made, and (optionally) reference images that set the quality bar.

Procedure:
1. Name the aesthetic this design is going for, in one sentence, from the screenshots alone.
2. DESIRE: as the person described, after the first viewport and the moment, write the sentence you would say. Do you want the product more than before? What would you tell a friend an hour later? One line each.
3. Imagine how a top design studio would execute this exact aesthetic *inside these fixed decisions and principles*: same palette, same typefaces, same components, same motion rules. Not a different product; this one, done by the best.
4. Outline the biggest gaps between the current design and that execution. At most five. Each gap names a location (section, element, viewport, or a frame of the moment) and states what specifically is wrong and what the studio version would do instead. One gap may be about desire: what the first viewport fails to make the person want.
5. Check every principle; name any the design breaks, with location.
6. Flag any pattern from the tells list you can see, with location.
7. Score the current design out of 10 for how close it is to that studio-level execution. 9 or higher means a studio would ship it with minor notes.

Guidance:
- Think high-level about overall structure, composition and the moment first, then look at fine details.
- Watch for patterns that feel overdone, excessive, or obviously AI-generated, and penalize them.
- Tight, specific feedback, not vague prose. "The proof is claimed in text where the mechanism could be shown" beats "could be more engaging".
- Be bold and opinionated; do not rely on what is safe or easy.
- The fixed decisions are not gaps. If you believe the palette or the typeface is the problem, say so in one line at the end under "Outside my brief", and do not let it affect the score.
- Judge both viewports and the moment. A composition that only works at 1440, or an idea that only works as a still, is not done.

Output format:
AESTHETIC: ...
DESIRE: "<what I would say>" · want more: yes/no · to a friend: "<sentence>"
STUDIO VERSION: ... (3-5 sentences)
GAPS:
1. [location] what is wrong → what the studio would do
...
PRINCIPLES BROKEN: [location] principle · ... (or none)
TELLS: [location] pattern · ...
SCORE: n/10
OUTSIDE MY BRIEF: (optional, one line)
```

## The round

1. Screenshot the current state to `shots/round-<n>-{1440,390}.png`; record the moment and lay it out as `shots/round-<n>-moment.png`.
2. Spawn the critic with the package above.
3. Append the full critique to `critic-log.md` under `## Round n — score x/10`.
4. Report to the owner. If they ask for fixes: hand the gaps to the builder (same builder agent, or the orchestrator if the build is small) with the instruction to fix them without opening new fronts. A fix that requires moving a lock or breaking a principle is refused and noted.
5. Another round only on the owner's word.

## Stop rules (when the owner has asked for a loop)

Stop and report when any of these is true:

- Score is 9 or higher.
- Five rounds have run.
- Plateau: the score improved by 0.5 or less over the last two rounds.
- The critic's gaps repeat a previous round's gaps nearly verbatim (the builder is not converging on them; escalate to the owner instead of looping).

Without a stop rule the loop runs forever on a critic that keeps finding something, and the cost of each round is a full opus critique. Chimala's note: test that the loop converges before trusting the stopping criterion; if the first two rounds show no movement, stop and check whether the gaps are actionable at all.

## Reporting to the owner

One short block: the score (or the trajectory, e.g. 6 → 7.5 → 8.5 → 9), the DESIRE lines, the last critique's gaps and what was done about them, anything under "Outside my brief" (so the owner can decide whether a lock should move; that is their call, not the critic's), and the path to `critic-log.md`.

## Calibration notes

- Critic tokens are cheap compared with build tokens; the critic typically consumes under 10% of the run. Do not economize on the critic's model.
- Overly subjective criteria ("looks beautiful, not AI-generated") make the loop wander. Concrete references beat adjectives. When the owner has none, use the brief's memory test, moment and first-viewport block as the concrete bar.
- A critic that scores 9 in round one is suspicious. Check that the screenshots show the full page and both widths, that the contact sheet was included, and that the tells list was included.
