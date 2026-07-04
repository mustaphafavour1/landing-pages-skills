---
name: landing-page-craft
description: Use whenever building, designing, or redesigning a landing page, marketing site, product page, portfolio/case-study page, or event/conference site — from a brief, a reference link, or nothing at all. Load whenever the user asks to build a landing page or a site for a product, design a hero section, wants something that "stands out" or "doesn't look templated," or wants a page with real taste. Encodes Favour's process and taste from his real builds (Allowance, didii, Revolut Founder Mode, TrashPay, FlutterBytes), refined by direct feedback across multiple test builds — the workflow, a required concept-and-grade planning pass before any code, a per-section intake checklist, the hard rules (hero built around one signature idea, no dead non-text sides in two-column sections, every section animated, distinctive type, headlines never plain), a framework for inventing each section's signature visual concept, a growing gallery of past signature concepts and typefaces to draw from, and a post-build grading rubric that feeds corrections back into the next build. Never fall back on generic template defaults for a landing-page task without checking this first.
---

# Landing Page Craft

This captures how Favour actually builds landing pages that don't look templated, distilled from his own past conversations building Allowance, didii, Revolut Founder Mode, TrashPay, and the FlutterBytes Conference site, and sharpened repeatedly by his direct feedback on test builds made with this skill. It isn't a generic "landing page best practices" guide — it's specific to what he keeps reaching for, correcting toward, and refusing to accept. It is also a living document: check `references/build-log.md` before starting, and add to it after finishing.

The goal every time: something with a genuine point of view, not a competent template with the client's name swapped in. And critically: a concept that reads as obvious and intentional on sight, not one that only makes sense once explained.

---

## Before anything: is there enough to work with?

If the brief doesn't give a real product to hook a concept to — no name, no sense of who it's for, no hint of tone, nothing that separates it from the generic version of this idea — stop and ask. One or two sharp questions beat inventing a placeholder direction and finding out later it didn't fit.

Two more specific moments to ask rather than assume:
- If a section would clearly benefit from a real photo (not an abstract or vector representation), ask for one before proceeding. If it isn't available, say so and improvise with gradients and line work instead of faking a stock photo.
- If a section needs representative sample content (example names, sample cards, placeholder data), propose one version of it first and explicitly invite changes, rather than quietly finalizing your own guess.

If there's enough — a real name, a real audience, a real point of difference, even a rough one — proceed.

---

## Build stack

Default target is Next.js, TypeScript, Tailwind CSS, and Framer Motion. That's the actual stack behind every project this skill is drawn from. Never plain HTML or vanilla JS as the deliverable.

If the working environment can't render that stack live, say so plainly rather than quietly substituting something weaker. Still build real React components, never vanilla JS, and approximate the intended motion with CSS transitions or the Web Animations API for the preview — but offer the real Next.js/TypeScript/Framer Motion codebase as downloadable files too, and say plainly if an environment that can actually run and screenshot that stack (Claude Code, for instance) is where this belongs, especially once real visual judgment on the output starts to matter more than a quick look.

---

## Type and color, chosen with the person, not decided alone

Before committing to either, do a short visual check-in rather than deciding silently:

- **Type:** check `references/typeface-library.md` for candidates not recently overused, then propose three distinctive, non-obvious display typeface candidates and actually render the product's name in each one, in whatever way the environment supports (an image, a quick preview, a live component) — never just list font names as text. Let the person choose from real letterforms, not a guess about what a name sounds like. A genuinely new typeface outside the library is a welcome option too — if it's picked, add it to `references/typeface-library.md` afterward.
- **Color:** propose a palette (4–6 named values) with the reasoning behind each choice grounded in the subject, and confirm before it's final.

Both test builds so far skipped this and decided both alone — it happened to land well twice, but that's luck, not the process working as intended.

---

## Site type first

Work out which of three shapes this is before anything else — the taste rules and framework below apply to all three, but the section inventory differs:

- **Product landing page** (Allowance, didii, TrashPay) — waitlist or download-focused, pricing, use cases, feature grid.
- **Portfolio / case-study page** (Revolut Founder Mode) — a designer's own concept pitch: a bio block, real-world stats to justify relevance, "reach out" instead of a waitlist.
- **Event / conference page** (FlutterBytes) — speaker showcase, past-editions history, organizing-team credit, sponsors, agenda.

Read `references/site-types.md` for the section inventory and structural notes for each. If it's genuinely none of these, treat it as closest to a product landing page and adapt.

---

## The process

1. **Get oriented.** Brand name, what it does, who it's for, any reference site or mood named.

2. **Find the one core concept before touching any section.** Not a feature list — the single thing the user actually gets or feels from this product, stated as one plain sentence, plus two or three supporting ideas. Every section's signature move gets checked against this later.

3. **Choose type and color with the person** (above), grounded in the subject, not decided alone.

4. **Decide the site type** (above) and skim its section inventory. Check `references/build-log.md` for what recent projects used, so this one doesn't rhyme with the last one by accident.

5. **Run every section through the intake checklist below, side by side, then grade honestly before writing any layout or code.**

   Intake, per section:
   - What is this section, and how much visual weight does it deserve? A hero earns more than a trust blurb.
   - What's the product about generally, and what's this section about specifically, based on its actual title, subtitle, and content — not a generic label for its category?
   - What concept follows from that content, specifically? Check `references/concept-gallery.md` for concepts already invented — reuse one that isn't cooling down, adapt one, or invent something new and add it there afterward.
   - What animation or hover interaction brings it to life?
   - How long is the title and subtitle? Short ones can carry a centered/surrounded treatment (see the layout archetypes in `references/taste-rules.md`); longer ones can't.
   - What layout and what signature move did the section immediately before this one use, and what did the last project use? Don't repeat either.

   Grade honestly, using falsifiable checks rather than comfortable numbers:
   - Does the concept land on one of the three generic AI-design defaults (warm cream + serif + terracotta, near-black + one acid accent, or broadsheet/hairline-rule newspaper style) without a brief-specific reason? That's a fail — go back to the intake.
   - Would this exact choice show up if the same prompt were run for a completely different product? If yes, it isn't specific enough yet.
   - Would a stranger get what it represents in about two seconds, with no caption? A concept that only works once explained has failed regardless of how clever the reasoning was.

   Grading is a discipline that always runs, not something to show — the person sees the resulting concept and a plain verdict, not a scoreboard. And be honest about the real limitation: without a way to actually see a render, self-grading is closer to careful code review than genuine visual judgment, so lean skeptical rather than generous. If the environment can actually run and screenshot the build, use that — a real look beats predicting one.

6. **Build the full first draft**, using the graded concepts plus the standing rules in `references/taste-rules.md`.

7. **Go section by section and quality-check each one individually**, against the built page. For each section, ask:
   - Does this section visibly connect to the core concept from step 2, or does it just illustrate its own feature in isolation?
   - Is the non-text side of any two-column section actually alive (animated, specific), or is it a dead flat image — not "is this two columns," but "is anything here static that shouldn't be"?
   - Is this a plain bordered card where a fading divider or something more considered would serve better? If it's a card, does it have a real hover interaction?
   - Does it have some animation or interaction, however subtle, and does the body text itself animate in rather than just appearing?
   - Has this exact signature move, or this exact animation primitive, already been used somewhere else on the page?
   - Is the spacing between this section and its neighbors generous, roughly 1.75x what would otherwise feel sufficient?
   - Does the copy sound like this brand specifically, not a generic template voice?

8. **Mobile pass.** Check line breaks inside headlines especially. Check anything with fixed pixel dimensions still works at small viewports. Auto-cycling sections often need a genuinely different mobile layout, not just a smaller copy of the desktop one.

9. **Harden pass**, if this is heading to production. Design tokens for anything needing light/dark mode. Cheap rendering primitives over expensive ones inside anything that animates continuously. Visible keyboard focus states, not just mouse hover states.

10. **Grade the finished build.** Using `references/grading-rubric.md`, fill out the scorecard against the real render (live preview, deployed URL, or screenshots), honestly and skeptically. This is a draft — hand it to the person to correct before it's final. Their correction is the actual record, not a formality.

11. **Update the reference files** with the corrected grade in hand:
    - `references/build-log.md` — what this project used (typefaces, palette, the hero's signature idea, which section concepts and layout archetypes and animation primitives came up) plus the corrected scorecard and carry-forward actions, so the next build has something real to check against.
    - `references/concept-gallery.md` — any new signature concept invented this build, and retire anything that's now been used enough times to need a rest.
    - `references/typeface-library.md` — any new typeface that got picked, and retire anything overused.

---

## Hard rules — never break these

1. **The hero is built around exactly one signature idea, and everything else on it stays quiet by comparison.** Two competing loud ideas on one hero (a showy headline treatment plus a separate showy visual concept that don't reinforce each other) is a specific, repeatable failure — it dilutes both instead of strengthening either. Pick the one thing this hero should be remembered for, ideally something that expresses the core of the product rather than just introducing it, and let the headline treatment and everything around it support that one thing rather than compete with it.

2. **A two-column layout is fine, even good, as long as whichever side isn't text is genuinely alive, not a flat image or static decoration.** TrashPay's For Companies section (title, subtitle, and chips on one side, an animated mini-dashboard on the other) and Allowance's How It Works (numbered content on one side, an image with a flowing light on the other) are both two-column and both work, because the non-text side is doing something specific. The failure is a dead side, not the column split itself — if there's nothing alive yet to put there, that's a sign to keep developing the concept, not to reach for a stock photo.

3. **Every section needs its own signature visual concept that is obvious on sight**, decided before layout details, not applied after as generic decoration, and not so abstract it needs a caption to be understood. `references/signature-moves.md` is the method.

4. **Every section needs some animation or interaction, however subtle, including its own text** — body copy should animate in, not just appear. No fully static section, ever. Subtle and distinctive beats loud.

5. **Never use a boring, common, or system typeface for display type.** Something memorable and specific to the brand, chosen with the person per the type-and-color step above.

6. **Never leave a headline rendering as plain, uniform text.** One deliberate mechanism per project, applied consistently everywhere a major headline appears.

---

## Reference files

- `references/signature-moves.md` — the generative method for inventing a section's defining visual concept, including the obviousness test.
- `references/taste-rules.md` — the standing checklist: layout archetypes, card avoidance, animation-primitive variety, subtle gradients, headline mechanisms, title formatting, spacing, and the design-token pattern for light/dark theming.
- `references/site-types.md` — section inventories for product pages, case-study pages, and event pages.
- `references/concept-gallery.md` — the growing, appendable catalogue of specific signature-visual-concept instances (with optional images), checked before inventing a new one and added to after every build.
- `references/typeface-library.md` — the growing, appendable list of distinctive typefaces, used and candidate, checked during the type-and-color step and added to whenever something new gets picked.
- `references/grading-rubric.md` — the post-build scorecard: Claude drafts it against the real render, the person corrects it, and the corrected version is what gets logged.
- `references/build-log.md` — what past builds used and how they graded, checked before starting a new one and updated after finishing it.

---

## Before calling it done

Read back through the section-by-section checklist in step 7 against the finished page. If every section could be swapped onto a different, unrelated product without changing anything but the copy, something in the concept pass got skipped. Each section should feel like it could only belong to this specific thing, and someone should be able to point at a section and say what it's about without being told.

---

## Keeping this current

After finishing a real build, check whether anything genuinely new happened: a signature-move metaphor not in `references/signature-moves.md`, a pattern that belongs in `references/taste-rules.md`, a concept worth logging in `references/concept-gallery.md`, a typeface worth adding to `references/typeface-library.md`, or a process step that needed adjusting or was missing. Propose the specific addition, with the concrete example it came from, grade the build against `references/grading-rubric.md` with the person's corrections, and record it all in `references/build-log.md` regardless of how the build went. This skill is only as good as what keeps getting fed back into it.
