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

### Cord Unravel — a wearable that becomes its own cable
- **Core idea:** the object you're wearing isn't a decoration standing in for the product — it physically *is* the product, and turns back into it on demand
- **Physical metaphor:** a custom multi-strand SVG rig — N parallel strand-paths sharing one ordered point-set across two named states (a coiled wrist-loop bracelet vs. a straight full-length cable) — with a single progress value (0–1) lerped per-point and redrawn every frame, so the asset visibly reconfigures rather than cross-fading between two pre-rendered images
- **Trigger:** ambient looping in the hero (0→1→0 with pauses); interaction-triggered (spring-to-step-target) in a 4-step click-through walkthrough; held static per-variant in a catalog picker (paired with a separate crossfade + diagonal shimmer-sweep on swap)
- **Seen in:** HeadFavour — hero, "How It Unravels" walkthrough, and the finish picker (same rig, three different triggers and narrative jobs on one page)
- **Status:** active
- **Image:** none yet
- **Notes:** built because the brief's product *literally* has a two-state physical story (wearable ⇄ working cable), not invented as a generic transition — only reach for this metaphor when that's true of the product, or it's just a fold/unfold effect with no real referent. Reusing the same rig three times on one page is a deliberate exception to the "never repeat a signature move" rule, justified here because each use has a different trigger and job (atmosphere vs. instruction vs. catalog) and the walkthrough section specifically needs to show the *same* transformation the hero promised — but it's a judgment call, not a precedent to lean on casually. Graded as a Partial against the no-repeat rule in this build's scorecard rather than a clean pass; worth Favour's own read on whether it lands as "one coherent trick" or "the only trick."

### Full-bleed overlay with floating nav pill
- **Core idea:** premium and immediately credible, people-first
- **Physical metaphor:** a full-bleed photo, a rounded floating navbar pill sitting on top of the image, headline overlaid in the lower third in mixed serif/italic accent type, a pill CTA with a small circular icon, one or two floating corner cards surfacing a secondary offer or credential
- **Trigger:** ambient photo, scroll-triggered fade-up for the overlaid text and cards
- **Seen in:** reference example for the mini-business landing page type (provided screenshot, "OPTIMO")
- **Status:** active
- **Image:** none yet
- **Notes:** floating corner cards are doing real trust-signal work here, not just decoration — keep them tied to a real credential or offer, not filler.

### Full-bleed atmospheric photo hero
- **Core idea:** mood and craft, told through a single strong image
- **Physical metaphor:** one full-bleed photo with a dark tonal overlay for legibility, a large serif headline anchored to one upper corner, subtitle and a single solid-accent CTA anchored below it, transparent navbar directly on the image
- **Trigger:** ambient photo, scroll-triggered fade-up for the text block
- **Seen in:** reference example for the mini-business landing page type (provided screenshot, "Restro")
- **Status:** active
- **Image:** none yet

### Circled-keyword hero with frosted stat card
- **Core idea:** one idea in the headline made literally impossible to miss, backed by a real number
- **Physical metaphor:** a photo hero where one keyword gets a circled/pill-outlined accent treatment, an eyebrow label plus one-line blurb, a CTA, and a floating frosted/glass stat card overlapping the photo, with a client-logo strip directly beneath the hero
- **Trigger:** interaction/ambient photo, scroll-triggered reveal for the stat card and logo strip
- **Seen in:** reference example for the mini-business landing page type (provided screenshot, "Busininity")
- **Status:** active
- **Image:** none yet
- **Notes:** the client-logo strip immediately under the hero is doing as much trust-building work as the stat card — don't drop it when adapting this pattern.

### Split image/text hero with trust cluster
- **Core idea:** calm confidence — let the work speak, prove it's already trusted
- **Physical metaphor:** a two-column hero, a real photo filling one side edge-to-edge, the other side calm negative space holding the logo, a small avatar-cluster trust indicator ("50+ founders trust us"), and a bold headline anchored to the bottom of the text column
- **Trigger:** ambient photo, scroll-triggered reveal for headline and trust cluster
- **Seen in:** reference example for the mini-business landing page type (provided screenshot, "Norvex")
- **Status:** active
- **Image:** none yet

### Text-first hero into arched photo reveal
- **Core idea:** state the value plainly first, then let the image confirm it
- **Physical metaphor:** a type-only opening block (eyebrow label, headline with one accent-colored keyword, short paragraph, CTA), immediately followed by a full-width photo masked with a soft arch/curve cutout at its top edge and a centered "scroll down" indicator
- **Trigger:** scroll-triggered reveal into the arched photo section
- **Seen in:** reference example for the mini-business landing page type (provided screenshot, "Clientix")
- **Status:** active
- **Image:** none yet
- **Image:** none yet
- **Notes:** graded as the strongest section of that build by a clear margin. Only reuse for a product with a genuine textile/weave/network conceit — otherwise it's borrowed rather than earned.

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
