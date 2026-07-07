# Concept Gallery

A growing catalogue of specific signature-visual-concept *instances* — not the generative method (that's `signature-moves.md`), and not the abstract metaphor families (that's the table in `signature-moves.md` step 2). This is the concrete inventory: real concepts that have actually been built, so a new project can be checked against what already exists before inventing something that turns out to be a repeat.

Check this before Step 2 of the signature-move framework. Add to it after every build, real or test — anything used counts, whether it was invented fresh or pulled from here.

**Never delete an entry.** Retire it instead (see Status below) so the history stays honest.

---

## How to add an entry

Append a new entry at the bottom of the relevant category, using the template below. Images are optional — a concept with only a description is still worth logging, especially the moment it's invented and before it's ever been rendered.

If an image exists (a screenshot, a still frame, an export from the actual build), drop it in `assets/concepts/` using a `kebab-case-name.png` (or `.gif`/`.mp4` for motion) filename that matches the entry name, and reference it with a relative path.

```md
### [Concept name] — [one-line core idea it represents]

- **Core idea:** the plain-phrase idea from Step 1 of signature-moves.md
- **Physical metaphor:** what it literally is
- **Trigger:** ambient / scroll-triggered / interaction-triggered
- **Seen in:** project — section
- **Status:** active / retired (reason)
- **Image:** ![alt text](../assets/concepts/filename.png)  *(or "none yet")*
- **Notes:** anything worth remembering — what made it land, what almost went wrong, a variant worth trying
```

Mark a concept **retired** once it's shown up on two or three builds — not because it stopped working, but because `taste-rules.md`'s rule against repeating a signature move means it needs a rest. A retired concept can come back later if enough time/builds have passed; note that in its entry rather than deleting it.

---

## Hero concepts

### Convergence — scattered elements collecting into order
- **Core idea:** disorder becoming order, on command
- **Physical metaphor:** particles/objects literally moving toward a point and assembling
- **Trigger:** ambient, with a scroll- or load-triggered convergence moment
- **Seen in:** TrashPay — hero (scattered waste collecting)
- **Status:** active
- **Image:** none yet
- **Notes:** works because the *form* of the scattered elements matters — waste-shaped fragments, not generic dots. Reuse only if the product has a real "mess becomes order" story.

### Woven lattice with traveling light
- **Core idea:** an intelligent, continuously active material
- **Physical metaphor:** a woven thread lattice as page background, with light pulses traveling along threads
- **Trigger:** ambient, looping
- **Seen in:** Weft (test build) — hero
- **Status:** active
- **Image:** none yet
- **Notes:** graded as the strongest section of that build by a clear margin. Only reuse for a product with a genuine textile/weave/network conceit — otherwise it's borrowed rather than earned.

### Photo composing into a cover — the raw input becoming the finished output
- **Core idea:** your ordinary photo becomes a real, art-directed magazine cover
- **Physical metaphor:** cover "furniture" (masthead, cover lines, category tab, barcode) fading/rising into place over a plain photograph, with a floating chip that morphs from a raw filename (`DSC_0642.JPG`) into an issue label (`Cover · N°14`)
- **Trigger:** load-triggered compose (staggered), the chip crossfade timed to land after the furniture settles
- **Seen in:** Kronikl — hero
- **Status:** active
- **Image:** none yet
- **Notes:** reads in two seconds with no caption because the *form* is literal — it's an actual cover assembling, not an abstract stand-in. Reuse only for products whose value is "raw input → finished designed artifact" (photo→cover, draft→published, clip→edit). The filename→label chip is the detail that makes the transformation legible; keep it.

### Spread assembling — an empty layout filling with the user's content
- **Core idea:** you bring the pieces, the template arranges them into a designed page
- **Physical metaphor:** an open two-page magazine spread where photo slots wipe in (clip-path reveal), text lines draw in (scaleX from left), a masthead fades up, and a "Print-ready · 300 DPI" stamp lands at the end — each phase tied to the active how-it-works step
- **Trigger:** state-driven (auto-cycling steps, also clickable), photos on step 1, text/masthead on step 2, export stamp on step 3
- **Seen in:** Kronikl — How It Works (the alive non-text side of a two-column section)
- **Status:** active
- **Image:** none yet
- **Notes:** strong pattern for any "upload → arrange → export" product. Distinct from the hero's single-cover compose because it's a full editorial spread reacting to step state, and it uses clip-wipe + line-draw rather than fade — deliberately avoids the traveling-dot primitive flagged in the build log.

### Contents-index tips — a magazine table of contents as the section layout
- **Core idea:** practical guidance framed as editorial contents, native to the product
- **Physical metaphor:** a two-column numbered index with oversized outlined folio numbers (text-stroke, filling solid yellow on hover) and hairline dividers between entries, each title getting a marker-underline draw on hover
- **Trigger:** interaction-triggered (per-item hover), scroll reveal on entry
- **Seen in:** Kronikl — "Field Guide" pro-tips section
- **Status:** active
- **Image:** none yet
- **Notes:** a way to render a 6-item tips/steps list *without* another auto-cycling one-expanded showcase, so it doesn't repeat the archetype already used by the templates showcase and how-it-works on the same page. Good default when a page needs a third multi-item section and the first two already used single-focus cycling.

---

## Section / content concepts

### Speaker Wheel — orbital showcase
- **Core idea:** a community of real people orbiting the thing
- **Physical metaphor:** satellites/avatars arranged in a ring, selectable
- **Trigger:** interaction-triggered (click/hover to bring one to the front)
- **Seen in:** FlutterBytes — speaker showcase
- **Status:** active
- **Image:** none yet
- **Notes:** strong alternative to a flat speaker grid for any "showcase of people" section.

### Materials card — opens to reveal depth on hover
- **Core idea:** there's more value here than the surface shows
- **Physical metaphor:** a card that physically extends/unfolds on hover to reveal more
- **Trigger:** interaction-triggered (hover)
- **Seen in:** TrashPay — materials section
- **Status:** active
- **Image:** none yet

### Rotating light border
- **Core idea:** an active, live, continuously-protected process
- **Physical metaphor:** a conic-gradient border that rotates around a card, like light traveling a track
- **Trigger:** ambient, looping
- **Seen in:** Allowance — How It Works cards
- **Status:** active
- **Image:** none yet

### Hub-and-spoke diagram
- **Core idea:** one thing connects to many, without needing to switch between them
- **Physical metaphor:** a central node with lines radiating to satellite nodes
- **Trigger:** ambient or scroll-triggered draw-in
- **Seen in:** didii — "no switching required"; also FlutterBytes' bank/commit-graph variant
- **Status:** active — used twice already; treat as due for a rest on the next build unless the product's story is unusually well-suited to it
- **Image:** none yet

### Before/after paired cards
- **Core idea:** the concrete old pain next to the concrete new resolution, per use case
- **Physical metaphor:** two-state card pair, explicit labels, one per scenario
- **Trigger:** scroll-triggered reveal, or click-to-toggle between states
- **Seen in:** didii — "Before Didii / With Didii"
- **Status:** active
- **Image:** none yet

### Branching result cards
- **Core idea:** one input personalizes into several distinct outputs
- **Physical metaphor:** a single card visually branching into multiple result cards, connected by traveling dots
- **Trigger:** scroll-triggered
- **Seen in:** Flare (test build) — How It Works
- **Status:** active — liked in principle, flagged as under-executed visually. Worth retrying with a stronger, more literal branch/fork visual before reusing as-is.
- **Image:** none yet

### Regenerating template grid
- **Core idea:** the same system produces endless distinct outputs
- **Physical metaphor:** a grid of near-identical cards, one periodically regenerating its content
- **Trigger:** ambient, looping
- **Seen in:** Flare (test build) — hero
- **Status:** retired for hero use — competed with a separate headline effect on the same hero and diluted both (see build-log.md). Could work as a *section* concept instead of a hero concept, on its own with a quiet headline.
- **Image:** none yet

---

## Retired / cooling-down concepts

Concepts that have been used enough times recently that they should sit out a build or two, tracked here so it's a quick glance instead of re-reading every build-log entry:

- **Traveling dot/pulse along a path** — used on both test builds so far (Weft, Flare) as the default animation primitive. Not retired as an idea, but explicitly flagged in `build-log.md` to avoid defaulting to it a third time. Try a line-draw reveal or an expand/contract shape instead.
- **Hub-and-spoke diagram** — used twice (didii, FlutterBytes). See above.

---

## Typeface library

A separate, growing list of distinctive display/body typefaces — used ones and untested candidates — lives in `references/typeface-library.md`. Check it during the type-and-color step alongside this file.
