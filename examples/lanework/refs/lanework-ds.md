# Lanework design system (fictional brand)

Proposed for this example and approved by the owner on 2026-10-22. Implemented in `../comps/lanework-ds.css`; nav markup in `../comps/lanework-nav.html`.

## Idea
Calm, plain, exact. The product is a list of who owns what; the brand looks like a well-set list: one face, generous white, one green for the action, quiet status colours.

## Type
One face: **Figtree** (SIL Open Font License), embedded in the stylesheet.

| Element | ≥1069 | 735–1068 | ≤734 |
|---|---|---|---|
| Hero headline (700, −0.025em) | 72/76 | 60/64 | 44/48 |
| Section headline (700, −0.02em) | 40/44 | 36/40 | 30/34 |
| Lead (400) | 20/30 | 20/30 | 18/27 |
| Body (400) | 17/26 | 17/26 | 16/24 |
| Eyebrow (600) | 15/20, ink-2 | same | same |
| Small / UI (500) | 14/20 | same | same |

## Colour
| Token | Hex | Use |
|---|---|---|
| ink | #15171c | text |
| ink-2 | #5b606b | secondary text |
| ink-3 | #8b909a | tertiary, placeholders |
| page | #ffffff | page |
| surface | #f4f4f1 | panels, alternate sections |
| line | #e4e4df | 1px rules and borders |
| accent | #0f7b5f | primary button, focus, the one highlight |
| accent-press | #0b6650 | pressed / hover |
| status on track | bg #e3f1ec · text #0f6b53 | task chip |
| status waiting | bg #f6eedb · text #8a5a00 | task chip |
| status late | bg #f7e3e1 · text #a3352b | task chip |
| status done | bg #ecece8 · text #5b606b | task chip |

## Components
- **Primary button**: accent fill, white text, Figtree 600 16px, height 44px, padding 0 20px, radius 10px.
- **Secondary action**: ink text, 1px underline, offset 4px.
- **Nav**: 64px; wordmark left (three-lane mark + "Lanework", 800); links Product · Pricing · Customers · Changelog; right: "Log in" and a small primary button "Start free".
- **Panels and app UI**: radius 12px, 1px line border, no shadows except a 1px hairline; never inside a browser frame.
- **Task row**: avatar (initials on a muted tint), task name, owner name, due date, status chip.
- **Avatars**: initials on #dfe7f1, #efe3d6, #e2ecdf, #ece0ec, #e6e4f3, #f1e6d9 with ink text.

## Don't
- No browser chrome around product UI; no floating tilted screenshots with drop shadows.
- No gradient blobs, no glows, no illustrations of people.
- No icon-heading-text feature cards in threes.
