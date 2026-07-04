# The Signature-Move Framework

A repeatable method for inventing a section's defining visual concept — not a list of effects to copy, but a way to arrive at a new one for any new section. Reverse-engineered from five things that worked: FlutterBytes' orbital Speaker Wheel, TrashPay's Materials card that opens on hover, Allowance's rotating light border on its How It Works cards, TrashPay's hero where particles literally converge like scattered waste being collected, and didii's hub-and-spoke "no switching required" diagram.

Run this before deciding on layout or copy details for a section. Layout should serve the concept, not the other way around.

## Step 1 — Name the section's core idea in one plain phrase

Not its category label. What is this section actually saying to someone, underneath the feature description?

- Not "this is the how-it-works section" — "your money is actively, continuously protected."
- Not "this is the team section" — "a community of real people orbiting this thing."
- Not "this is the materials section" — "there's more value here than the surface shows."
- Not "this is the testimonials section" — "real, different kinds of people are already getting real value."

If the phrase could apply to almost any product's version of this section, keep pushing — it needs to be specific to this one. It should also visibly connect to the product's single core concept (the one identified once, before any individual section work, per `SKILL.md`) — a section whose idea doesn't trace back to that core concept will read as a good illustration of a feature with no relationship to anything else on the page.

## Step 2 — Generate a few candidate physical metaphors before picking one

Force real options. The first idea that comes to mind is usually the most generic one (a fade, a hover-lift, a gentle parallax) — not wrong exactly, but not a signature move either. Check `references/concept-gallery.md` first for specific concepts already invented and built — reusing one that isn't cooling down from overuse is fair game, and often faster than inventing from scratch. The metaphor families below are for when nothing in the gallery fits yet:

| Core idea | Physical metaphor | Seen in |
|---|---|---|
| Convergence, order from chaos | Objects or particles moving toward a point | TrashPay's hero — scattered waste literally collecting |
| Community, a network of individuals | Orbiting satellites, a constellation, a hub with spokes | FlutterBytes' Speaker Wheel; FlutterBytes' "highest commits" team graph; Allowance's PCB-line card; didii's bank-logo hub |
| An active, live, or protected process | Light or energy traveling along a path or edge | Allowance's rotating conic-gradient border on its How It Works cards |
| Hidden depth, more than meets the eye | Something that expands or opens on touch | TrashPay's Materials card, extending on hover to show detail |
| A journey or history over time | A path or timeline with waypoints along it | FlutterBytes' wavy 5-years-history line with a card at each year |
| Certainty, proof, or scale | A number resolving from unsettled to fixed | Count-up animations; an outline that fills in solid; text that scrambles then resolves |
| Transformation or contrast | An explicit before/after pairing | didii's "Before Didii / With Didii" cards, one per use case |
| Individual attention, focus | A spotlight that moves between items, one expanded at a time | Auto-cycling tabs, seen across nearly every project |

None of these are the only option for their core idea — they're evidence that a genuine physical metaphor, chosen deliberately, reads as intentional in a way a generic transition never does.

## Step 3 — Sketch the static composition first, and be honest about whether it's actually obvious

Before animating anything, know what the section looks like frozen. Then ask the only question that actually matters here: would a stranger, looking at just this still frame with no caption, get roughly what it represents within about two seconds? If the honest answer is "only if you already know what it's supposed to mean," the concept has failed, no matter how clever the reasoning behind it was.

This is the mistake worth naming directly: a generic shape animated nicely is still a generic shape. A dot moving in a loop does not read as "your data" just because the surrounding copy says so — a heartbeat-shaped line reads as a heartbeat on its own. The specific *form* of the elements has to recognizably relate to the real thing being represented, not just the composition or the fact that something is moving. If the concept only works with the label attached, go back to Step 2 and pick a more literal, more specific metaphor, even if it feels less clever — obvious-and-good beats subtle-and-missed every time.

Score this formally against the "obviousness" axis in the grading rubric in `SKILL.md` before moving on to Step 4.

## Step 4 — Choose the trigger to match the content, not by default

- **Ambient, looping** — for atmosphere-setting sections. Hero backgrounds, particle fields, a border that's always gently moving.
- **Scroll-triggered reveal** — for narrative or proof moments. Scramble-to-text headlines, count-up numbers, cards scattering into place as the section enters view.
- **Interaction-triggered (hover/tap)** — for exploratory or browsing content. A materials card that opens, a speaker wheel that responds to selection, tabs that swap on click.

Defaulting every section to "fade up on scroll" is the tell that this step got skipped.

## Step 5 — Keep it singular, and never repeat the same signature move twice on one page

One clear idea per section, executed with restraint. Subtle and distinct beats loud and stacked — the goal is a page where each section is quietly, specifically doing its own thing, not a page repeating the same trick eight times. If two sections end up leaning on the same device (two hub-and-spoke diagrams, two scramble reveals), change one of them, even if both look fine in isolation.

## Step 6 — Sanity check before moving on

- Does the section still function with the animation stripped out (accessibility, reduced motion)?
- Does every interactive element have a visible keyboard focus state, not just a mouse hover state?
- Does it cost real performance? Prefer cheap rendering primitives over expensive ones inside anything that runs continuously — simple shapes over emoji or heavy images in a canvas loop, for instance.
- Does it fit the typeface, color system, and headline mechanism already chosen for this project, or does it introduce a one-off style that clashes with everything else on the page?
- Has this exact signature move, or this exact animation primitive, already been used elsewhere on this page, or on the last project logged in `references/build-log.md`? If so, change it.
