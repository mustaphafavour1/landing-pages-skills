---
name: landing-page-craft
description: Use whenever building, designing, or redesigning a landing page, marketing site, product page, portfolio/case-study page, or event/conference site — from a brief, a reference link, or nothing at all. Load whenever the user asks to build a landing page or a site for a product, design a hero section, wants something that "stands out" or "doesn't look templated," or wants a page with real taste. Encodes Favour's process and taste from his real builds (Allowance, didii, Revolut Founder Mode, TrashPay, FlutterBytes), refined by direct feedback across multiple test builds — the workflow, a required concept-and-grade planning pass before any code, a per-section intake checklist, the hard rules (hero built around one signature idea, no dead non-text sides in two-column sections, every section animated, distinctive type, headlines never plain), a framework for inventing each section's signature visual concept, a growing gallery of past signature concepts and typefaces to draw from, a 194-entry section design bank (layout, background, type, and motion detail per entry) to adapt sections from, and a post-build grading rubric that feeds corrections back into the next build. Never fall back on generic template defaults for a landing-page task without checking this first.
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

## Forms always submit to a Google Form

Any form on the site — waitlist, contact, enquiry, apply-to-speak, order/booking, whatever — is a **branded, custom-built form in the site's own design** whose submissions are forwarded to a Google Form behind the scenes via that form's **pre-fill link**. The visitor never sees a raw Google Form; they see the site's styling, and the data lands in the Google Form's responses (and its linked responses spreadsheet).

**Ask for this early, as soon as it's clear the site needs a form** — it's a dependency on the person, like photos are. Ask them to create a Google Form with fields that match what the site's form collects, and to send back its **pre-fill link**. Then map each on-site field to the corresponding Google Form entry ID parsed from that pre-fill link, and submit to it on the form's submit handler (the standard approach is a POST to the form's `/formResponse` endpoint with the `entry.<id>` parameters, or an equivalent). If the person hasn't provided the link yet, build the branded form UI fully but leave the submission target clearly stubbed and flagged, rather than inventing an endpoint.

Always give the person the steps to fetch a Google Form's pre-fill link, since most people don't know where it is:

1. Open the Google Form in edit mode.
2. Click the three-dot **⋮** overflow menu at the top right.
3. Choose **"Get pre-filled link."**
4. Fill in each field with a recognizable placeholder value (e.g. type the field's own name into it), then click **"Get link"** at the bottom.
5. Click **"Copy link"** in the popup and send it over.

That link contains every field's `entry.<id>` and is exactly what's needed to map the branded form's fields to the Google Form.

---

## Type and color, chosen with the person, not decided alone

Before committing to either, do a short visual check-in rather than deciding silently:

- **Type:** check `references/typeface-library.md` for candidates not recently overused, then propose three distinctive, non-obvious display typeface candidates and actually render the product's name in each one, in whatever way the environment supports (an image, a quick preview, a live component) — never just list font names as text. Let the person choose from real letterforms, not a guess about what a name sounds like. A genuinely new typeface outside the library is a welcome option too — if it's picked, add it to `references/typeface-library.md` afterward. **Never skip this proposal-and-confirmation step** — even when a strong recommendation is obvious or a library typeface is already going to be used, still surface the candidates and confirm rather than deciding silently.
- **Color and theme:** propose a palette (4–6 named values) with the reasoning behind each choice grounded in the subject, and decide light vs. dark theme deliberately here rather than defaulting to dark (see the theme rule in `references/taste-rules.md` — plenty of brands read better light). Confirm both before they're final.
- **Style direction:** alongside type and color, pick one dominant style family for the whole page from the named families in `references/section-bank.md` (aurora/pastel glow, neo-glow dark tech, clean-tech organic, editorial/brutalist, minimalist high-key, luxury/premium showcase, corporate B2B/fintech) — chosen for a brief-specific reason, not by habit. This is the lane the section bank gets shopped in later; borrowing outside it is a deliberate accent, not a default.

Both test builds so far skipped this and decided both alone — it happened to land well twice, but that's luck, not the process working as intended.

---

## Site type first

Work out which of seven shapes this is before anything else — the taste rules and framework below apply to all of them, but the section inventory and, for the business, European, and mini-business types, the visual approach differ:

- **Product landing page** (Allowance, didii, TrashPay) — waitlist or download-focused, pricing, use cases, feature grid.
- **Portfolio / case-study page** (Revolut Founder Mode) — a designer's own concept pitch: a bio block, real-world stats to justify relevance, "reach out" instead of a waitlist.
- **Event / conference page** (FlutterBytes) — speaker showcase, past-editions history, organizing-team credit, sponsors, agenda.
- **Business page** (a fashion label, a bakery, a salon, a studio — an established real-world business, not a startup) — sells a real product or service that already exists, so it leans image-heavy and atmosphere-first rather than feature-grid-first. Aim for roughly 75% of sections to be built around real photography (menu/lookbook/gallery/space), with the signature-move and animation rules layered on top of the imagery rather than replacing it.
- **Hybrid** — a deliberate mix of two or three of the above (a product that's also pitching an event, a business with a portfolio of past work). Pick the dominant type for the overall structure and spacing, then borrow the specific sections that the secondary type needs.
- **European website** — a clean, restrained, premium-feeling site in the style of high-end European studio/Framer-template work. Same foundations as the others, but the hero is deliberately simple: one or more suitable real photographs (fetched and downloaded from Unsplash, Pexels, or Pixabay) set as the hero background inside a ~98%-width rounded rectangular frame, with no busy signature-visual layered on top. No waitlist. Simple, but not boring.
- **Mini-business landing page** — a tight, premium one-pager, **exactly four sections** (hero, offering, proof, contact), built to pitch established, often traditional businesses that don't yet have a web presence — machinery dealers, bulk exporters, manufacturers, industrial suppliers, wholesalers. This one has to be convincing enough on its own to make a business without a website believe in having one, so it leans hard on premium real photography, real trust signals (stats, client logos, certifications), and a confident, varied hero — see `references/site-types.md` for the five hero iterations to rotate between and the mandatory Contact Us section.

Read `references/site-types.md` for the section inventory and structural notes for each. If it's genuinely none of these, treat it as closest to a product landing page and adapt.

---

## The process

1. **Get oriented.** Brand name, what it does, who it's for, any reference site or mood named. If it's clear the site will need a form (waitlist, contact, enquiry, order), raise the Google Form dependency now per the forms section above — ask the person to create the Google Form and send its pre-fill link, so it isn't a scramble at the end.

2. **Find the one core concept before touching any section.** Not a feature list — the single thing the user actually gets or feels from this product, stated as one plain sentence, plus two or three supporting ideas. Every section's signature move gets checked against this later. Also ask the person directly whether they already have concepts, visuals, or ideas they'd love to include or illustrate — especially for the hero — so their own vision feeds the concept rather than being overwritten by an invented one.

3. **Choose type and color with the person** (above), grounded in the subject, not decided alone.

4. **Decide the site type** (above) and skim its section inventory. Check `references/build-log.md` for what recent projects used, so this one doesn't rhyme with the last one by accident.

5. **Run every section through the intake checklist below, side by side, then grade honestly before writing any layout or code.**

   Intake, per section:
   - What is this section, and how much visual weight does it deserve? A hero earns more than a trust blurb.
   - What's the product about generally, and what's this section about specifically, based on its actual title, subtitle, and content — not a generic label for its category?
   - What concept follows from that content, specifically? Check `references/concept-gallery.md` for concepts already invented — reuse one that isn't cooling down, adapt one, or invent something new and add it there afterward.
   - What does the section design bank offer? Pull two or three candidate rows from `references/section-bank.md` (matched by section category, then by the project's style direction), weigh them against an invented-from-scratch option, and adapt the winner per the bank's adapt-never-transplant rules — the row's palette, typefaces, and pixel specs get re-mapped to this project's, and the section still has to pass the two-second test for this specific brand.
   - What animation or hover interaction brings it to life? The bank's motion column is a vocabulary to draw from here (dash-offset draws, odometer count-ups, flex-grow expansions, staggered entries, mask reveals) — still never the same primitive twice on one page.
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
   - Is the non-text side of any two-column section actually alive — an animated mini-interface, screen snippet, or self-contained concept — or is it a dead flat image? Not "is this two columns," but "is anything here static that shouldn't be"?
   - Is this a plain bordered card where a fading divider or something more considered would serve better? Is the whole page staying within one or two card-using sections total? If it's a card, does it have a real customization touch (glossy gradient fill, glass-like border, animated icon) and a real hover interaction?
   - Are all icons from the chosen custom icon library (Lucide/Phosphor/Heroicons/Tabler), with no emojis standing in where an icon belongs?
   - Does it have some animation or interaction, however subtle, and does the body text itself animate in rather than just appearing?
   - Has this exact signature move, or this exact animation primitive, already been used somewhere else on the page?
   - Is the spacing between this section and its neighbors generous, roughly 1.75x what would otherwise feel sufficient?
   - Does the copy sound like this brand specifically, not a generic template voice?

8. **Mobile pass.** Check line breaks inside headlines especially. Check anything with fixed pixel dimensions still works at small viewports. Auto-cycling sections often need a genuinely different mobile layout, not just a smaller copy of the desktop one.

9. **Harden pass**, if this is heading to production. Design tokens for anything needing light/dark mode. Cheap rendering primitives over expensive ones inside anything that animates continuously. Visible keyboard focus states, not just mouse hover states.

10. **Grade the finished build.** Using `references/grading-rubric.md`, fill out the scorecard against the real render (live preview, deployed URL, or screenshots), honestly and skeptically. This is a draft — hand it to the person to correct before it's final. Their correction is the actual record, not a formality.

11. **Update the reference files** with the corrected grade in hand:
    - `references/build-log.md` — what this project used (typefaces, palette, style direction, the hero's signature idea, which section concepts and layout archetypes and animation primitives came up, and **which section-bank row IDs influenced which sections**) plus the corrected scorecard and carry-forward actions, so the next build has something real to check against.
    - `references/concept-gallery.md` — any new signature concept invented this build, and retire anything that's now been used enough times to need a rest.
    - `references/typeface-library.md` — any new typeface that got picked, and retire anything overused.
    - `references/section-bank.csv` — if this build produced a section design worth reusing, describe it in the bank's column language and append it as a new row.

---

## Hard rules — never break these

1. **The hero is built around exactly one signature idea, and everything else on it stays quiet by comparison.** Two competing loud ideas on one hero (a showy headline treatment plus a separate showy visual concept that don't reinforce each other) is a specific, repeatable failure — it dilutes both instead of strengthening either. Pick the one thing this hero should be remembered for, ideally something that expresses the core of the product rather than just introducing it, and let the headline treatment and everything around it support that one thing rather than compete with it.

2. **A two-column layout is fine, even good, as long as whichever side isn't text is genuinely alive, not a flat image or static decoration.** The non-text side should as much as possible be an animated mini-interface or a self-contained concept, not a picture — a mini-dashboard, a snippet of a mobile screen, a subtle vertical or horizontal revolving/scrolling screen, a custom-style animated card, or similar. TrashPay's For Companies section (title, subtitle, and chips on one side, an animated mini-dashboard on the other) and Allowance's How It Works (numbered content on one side, an image with a flowing light on the other) are both two-column and both work, because the non-text side is doing something specific and alive. The failure is a dead side, not the column split itself — if there's nothing alive yet to put there, that's a sign to keep developing the concept, not to reach for a stock photo.

3. **Every section needs its own signature visual concept that is obvious on sight**, decided before layout details, not applied after as generic decoration, and not so abstract it needs a caption to be understood. `references/signature-moves.md` is the method.

4. **Every section needs some animation or interaction, however subtle, including its own text** — body copy should animate in, not just appear. No fully static section, ever. Subtle and distinctive beats loud.

5. **Never use a boring, common, or system typeface for display type.** Something memorable and specific to the brand, chosen with the person per the type-and-color step above.

6. **Never leave a headline rendering as plain, uniform text.** One deliberate mechanism per project, applied consistently everywhere a major headline appears.

---

## Reference files

- `references/signature-moves.md` — the generative method for inventing a section's defining visual concept, including the obviousness test.
- `references/taste-rules.md` — the standing checklist: layout archetypes, card avoidance, animation-primitive variety, subtle gradients, headline mechanisms, title formatting, spacing, and the design-token pattern for light/dark theming.
- `references/site-types.md` — section inventories for product pages, case-study pages, and event pages.
- `references/section-bank.md` — how to use the section design bank (adapt-never-transplant rules, style families, usage tracking) plus a category index of all entries; `references/section-bank.csv` is the bank itself — 194 described sections with layout, background, typography, and motion detail per row.
- `references/concept-gallery.md` — the growing, appendable catalogue of specific signature-visual-concept instances (with optional images), checked before inventing a new one and added to after every build.
- `references/typeface-library.md` — the growing, appendable list of distinctive typefaces, used and candidate, checked during the type-and-color step and added to whenever something new gets picked.
- `references/grading-rubric.md` — the post-build scorecard: Claude drafts it against the real render, the person corrects it, and the corrected version is what gets logged.
- `references/build-log.md` — what past builds used and how they graded, checked before starting a new one and updated after finishing it.

---

## Before calling it done

Read back through the section-by-section checklist in step 7 against the finished page. If every section could be swapped onto a different, unrelated product without changing anything but the copy, something in the concept pass got skipped. Each section should feel like it could only belong to this specific thing, and someone should be able to point at a section and say what it's about without being told.

---

## Keeping this current

After finishing a real build, check whether anything genuinely new happened: a signature-move metaphor not in `references/signature-moves.md`, a pattern that belongs in `references/taste-rules.md`, a concept worth logging in `references/concept-gallery.md`, a typeface worth adding to `references/typeface-library.md`, a section design worth appending to `references/section-bank.csv`, or a process step that needed adjusting or was missing. Propose the specific addition, with the concrete example it came from, grade the build against `references/grading-rubric.md` with the person's corrections, and record it all in `references/build-log.md` regardless of how the build went. This skill is only as good as what keeps getting fed back into it.
