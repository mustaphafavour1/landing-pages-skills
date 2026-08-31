# Landing Page Craft — Complete Skill Reference

A single-file export of the `landing-page-craft` skill: every rule, process step, framework, and reference table used to build landing pages, marketing sites, portfolio/case-study pages, and event pages with a genuine point of view — not generic template output. It encodes how Favour actually builds these pages, distilled from his own past conversations building Allowance, didii, Revolut Founder Mode, TrashPay, and the FlutterBytes Conference site, and sharpened repeatedly by his direct feedback on test builds made with this skill.

It isn't a generic "landing page best practices" guide — it's specific to what gets reached for, corrected toward, and refused. The goal every time: something with a genuine point of view, not a competent template with the client's name swapped in. And critically: a concept that reads as obvious and intentional on sight, not one that only makes sense once explained.

**Never fall back on generic template defaults for a landing-page task without checking this first.**

## 1 Overview

### What this file is

This repository normally holds the skill as a folder — `landing-page-craft/SKILL.md` plus everything under `landing-page-craft/references/` — so that Claude Code (or another agent) can load it as a skill and follow the cross-references between files directly. This document flattens that entire structure into one place, in the order the skill itself points to each piece, so the whole thing can be read, searched, or handed off as a single artifact.

The multi-file version in `landing-page-craft/` remains the living source of truth — it's what actually gets edited and appended to after every real build (new concepts, new typefaces, new section-bank rows, corrected grades). Treat this file as a generated, point-in-time snapshot of that source rather than a second place to make edits.

**The two feedback loops this skill runs on**, for context before diving into the sections below:

1. **The concept gallery.** Every signature visual concept that gets invented or reused — hero concepts and section concepts alike — gets logged: what it is, the core idea it represents, the physical metaphor, where it's been used, and whether it's active or "cooling down" from overuse. Checked before inventing a new concept; appended to after every build.
2. **Grading.** After a build is actually viewable — live preview, deployed link, or screenshots — a scorecard gets filled out against the real render, honestly and skeptically. The person then corrects anything that reads wrong; their correction is the actual record, not the first pass. The corrected scorecard, plus a short list of carry-forward actions, gets appended to that build's entry in the build log, so the next build starts by reading what the last one got right and wrong.

There's also a running **typeface library** for the same kind of feedback loop, specific to type, and a **194-entry section design bank** — a library of described website sections (layout, background, typography, and motion detail per entry) that gets shortlisted and *adapted*, never transplanted as-is, during the per-section concept pass.

### Contents

1. [Overview](#1-overview) — this section
2. [The Skill and Process](#2-the-skill-and-process) — when to use it, the build stack, the forms rule, type/color check-in, site types, the eleven-step process, and the six hard rules
3. [The Signature Move Framework](#3-the-signature-move-framework) — the generative method for inventing a section's defining visual concept
4. [Standing Taste Rules](#4-standing-taste-rules) — the checklist confirmed across multiple past builds
5. [Site Types](#5-site-types) — full section inventories and structural notes for all seven page shapes
6. [Section Design Bank](#6-section-design-bank) — how to use the bank, its style families, the category index, and the full 194-row dataset
7. [Concept Gallery](#7-concept-gallery) — the catalogue of specific signature-visual-concept instances, active and retired
8. [Typeface Library](#8-typeface-library) — distinctive typefaces, used and candidate
9. [Grading Rubric](#9-grading-rubric) — the post-build scorecard template and how grading works
10. [Build Log](#10-build-log) — what past builds used and how they graded
11. [Source Files](#11-source-files) — where each section above lives in the original multi-file skill

---

## 2 The Skill and Process

*Source: `landing-page-craft/SKILL.md`*

### Skill metadata (frontmatter)

- **Skill name:** `landing-page-craft`
- **Trigger description:** Use whenever building, designing, or redesigning a landing page, marketing site, product page, portfolio/case-study page, or event/conference site — from a brief, a reference link, or nothing at all. Load whenever the user asks to build a landing page or a site for a product, design a hero section, wants something that "stands out" or "doesn't look templated," or wants a page with real taste. Encodes Favour's process and taste from his real builds (Allowance, didii, Revolut Founder Mode, TrashPay, FlutterBytes), refined by direct feedback across multiple test builds — the workflow, a required concept-and-grade planning pass before any code, a per-section intake checklist, the hard rules (hero built around one signature idea, no dead non-text sides in two-column sections, every section animated, distinctive type, headlines never plain), a framework for inventing each section's signature visual concept, a growing gallery of past signature concepts and typefaces to draw from, a 194-entry section design bank (layout, background, type, and motion detail per entry) to adapt sections from, and a post-build grading rubric that feeds corrections back into the next build. Never fall back on generic template defaults for a landing-page task without checking this first.

This captures how Favour actually builds landing pages that don't look templated, distilled from his own past conversations building Allowance, didii, Revolut Founder Mode, TrashPay, and the FlutterBytes Conference site, and sharpened repeatedly by his direct feedback on test builds made with this skill. It isn't a generic "landing page best practices" guide — it's specific to what he keeps reaching for, correcting toward, and refusing to accept. It is also a living document: check `references/build-log.md` before starting, and add to it after finishing.

The goal every time: something with a genuine point of view, not a competent template with the client's name swapped in. And critically: a concept that reads as obvious and intentional on sight, not one that only makes sense once explained.

---

### Before anything: is there enough to work with?

If the brief doesn't give a real product to hook a concept to — no name, no sense of who it's for, no hint of tone, nothing that separates it from the generic version of this idea — stop and ask. One or two sharp questions beat inventing a placeholder direction and finding out later it didn't fit.

Two more specific moments to ask rather than assume:
- If a section would clearly benefit from a real photo (not an abstract or vector representation), ask for one before proceeding. If it isn't available, say so and improvise with gradients and line work instead of faking a stock photo.
- If a section needs representative sample content (example names, sample cards, placeholder data), propose one version of it first and explicitly invite changes, rather than quietly finalizing your own guess.

If there's enough — a real name, a real audience, a real point of difference, even a rough one — proceed.

---

### Build stack

Default target is Next.js, TypeScript, Tailwind CSS, and Framer Motion. That's the actual stack behind every project this skill is drawn from. Never plain HTML or vanilla JS as the deliverable.

If the working environment can't render that stack live, say so plainly rather than quietly substituting something weaker. Still build real React components, never vanilla JS, and approximate the intended motion with CSS transitions or the Web Animations API for the preview — but offer the real Next.js/TypeScript/Framer Motion codebase as downloadable files too, and say plainly if an environment that can actually run and screenshot that stack (Claude Code, for instance) is where this belongs, especially once real visual judgment on the output starts to matter more than a quick look.

---

### Forms always submit to a Google Form

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

### Type and color, chosen with the person, not decided alone

Before committing to either, do a short visual check-in rather than deciding silently:

- **Type:** check `references/typeface-library.md` for candidates not recently overused, then propose three distinctive, non-obvious display typeface candidates and actually render the product's name in each one, in whatever way the environment supports (an image, a quick preview, a live component) — never just list font names as text. Let the person choose from real letterforms, not a guess about what a name sounds like. A genuinely new typeface outside the library is a welcome option too — if it's picked, add it to `references/typeface-library.md` afterward. **Never skip this proposal-and-confirmation step** — even when a strong recommendation is obvious or a library typeface is already going to be used, still surface the candidates and confirm rather than deciding silently.
- **Color and theme:** propose a palette (4–6 named values) with the reasoning behind each choice grounded in the subject, and decide light vs. dark theme deliberately here rather than defaulting to dark (see the theme rule in `references/taste-rules.md` — plenty of brands read better light). Confirm both before they're final.
- **Style direction:** alongside type and color, pick one dominant style family for the whole page from the named families in `references/section-bank.md` (aurora/pastel glow, neo-glow dark tech, clean-tech organic, editorial/brutalist, minimalist high-key, luxury/premium showcase, corporate B2B/fintech) — chosen for a brief-specific reason, not by habit. This is the lane the section bank gets shopped in later; borrowing outside it is a deliberate accent, not a default.

Both test builds so far skipped this and decided both alone — it happened to land well twice, but that's luck, not the process working as intended.

---

### Site type first

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

### The process

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

### Hard rules — never break these

1. **The hero is built around exactly one signature idea, and everything else on it stays quiet by comparison.** Two competing loud ideas on one hero (a showy headline treatment plus a separate showy visual concept that don't reinforce each other) is a specific, repeatable failure — it dilutes both instead of strengthening either. Pick the one thing this hero should be remembered for, ideally something that expresses the core of the product rather than just introducing it, and let the headline treatment and everything around it support that one thing rather than compete with it.

2. **A two-column layout is fine, even good, as long as whichever side isn't text is genuinely alive, not a flat image or static decoration.** The non-text side should as much as possible be an animated mini-interface or a self-contained concept, not a picture — a mini-dashboard, a snippet of a mobile screen, a subtle vertical or horizontal revolving/scrolling screen, a custom-style animated card, or similar. TrashPay's For Companies section (title, subtitle, and chips on one side, an animated mini-dashboard on the other) and Allowance's How It Works (numbered content on one side, an image with a flowing light on the other) are both two-column and both work, because the non-text side is doing something specific and alive. The failure is a dead side, not the column split itself — if there's nothing alive yet to put there, that's a sign to keep developing the concept, not to reach for a stock photo.

3. **Every section needs its own signature visual concept that is obvious on sight**, decided before layout details, not applied after as generic decoration, and not so abstract it needs a caption to be understood. `references/signature-moves.md` is the method.

4. **Every section needs some animation or interaction, however subtle, including its own text** — body copy should animate in, not just appear. No fully static section, ever. Subtle and distinctive beats loud.

5. **Never use a boring, common, or system typeface for display type.** Something memorable and specific to the brand, chosen with the person per the type-and-color step above.

6. **Never leave a headline rendering as plain, uniform text.** One deliberate mechanism per project, applied consistently everywhere a major headline appears.

---

### Reference files

- `references/signature-moves.md` — the generative method for inventing a section's defining visual concept, including the obviousness test.
- `references/taste-rules.md` — the standing checklist: layout archetypes, card avoidance, animation-primitive variety, subtle gradients, headline mechanisms, title formatting, spacing, and the design-token pattern for light/dark theming.
- `references/site-types.md` — section inventories for product pages, case-study pages, and event pages.
- `references/section-bank.md` — how to use the section design bank (adapt-never-transplant rules, style families, usage tracking) plus a category index of all entries; `references/section-bank.csv` is the bank itself — 194 described sections with layout, background, typography, and motion detail per row.
- `references/concept-gallery.md` — the growing, appendable catalogue of specific signature-visual-concept instances (with optional images), checked before inventing a new one and added to after every build.
- `references/typeface-library.md` — the growing, appendable list of distinctive typefaces, used and candidate, checked during the type-and-color step and added to whenever something new gets picked.
- `references/grading-rubric.md` — the post-build scorecard: Claude drafts it against the real render, the person corrects it, and the corrected version is what gets logged.
- `references/build-log.md` — what past builds used and how they graded, checked before starting a new one and updated after finishing it.

---

### Before calling it done

Read back through the section-by-section checklist in step 7 against the finished page. If every section could be swapped onto a different, unrelated product without changing anything but the copy, something in the concept pass got skipped. Each section should feel like it could only belong to this specific thing, and someone should be able to point at a section and say what it's about without being told.

---

### Keeping this current

After finishing a real build, check whether anything genuinely new happened: a signature-move metaphor not in `references/signature-moves.md`, a pattern that belongs in `references/taste-rules.md`, a concept worth logging in `references/concept-gallery.md`, a typeface worth adding to `references/typeface-library.md`, a section design worth appending to `references/section-bank.csv`, or a process step that needed adjusting or was missing. Propose the specific addition, with the concrete example it came from, grade the build against `references/grading-rubric.md` with the person's corrections, and record it all in `references/build-log.md` regardless of how the build went. This skill is only as good as what keeps getting fed back into it.

---

## 3 The Signature Move Framework

*Source: `landing-page-craft/references/signature-moves.md`*


A repeatable method for inventing a section's defining visual concept — not a list of effects to copy, but a way to arrive at a new one for any new section. Reverse-engineered from five things that worked: FlutterBytes' orbital Speaker Wheel, TrashPay's Materials card that opens on hover, Allowance's rotating light border on its How It Works cards, TrashPay's hero where particles literally converge like scattered waste being collected, and didii's hub-and-spoke "no switching required" diagram.

Run this before deciding on layout or copy details for a section. Layout should serve the concept, not the other way around.

### Step 1 — Name the section's core idea in one plain phrase

Not its category label. What is this section actually saying to someone, underneath the feature description?

- Not "this is the how-it-works section" — "your money is actively, continuously protected."
- Not "this is the team section" — "a community of real people orbiting this thing."
- Not "this is the materials section" — "there's more value here than the surface shows."
- Not "this is the testimonials section" — "real, different kinds of people are already getting real value."

If the phrase could apply to almost any product's version of this section, keep pushing — it needs to be specific to this one. It should also visibly connect to the product's single core concept (the one identified once, before any individual section work, per `SKILL.md`) — a section whose idea doesn't trace back to that core concept will read as a good illustration of a feature with no relationship to anything else on the page.

### Step 2 — Generate a few candidate physical metaphors before picking one

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

### Step 3 — Sketch the static composition first, and be honest about whether it's actually obvious

Before animating anything, know what the section looks like frozen. Then ask the only question that actually matters here: would a stranger, looking at just this still frame with no caption, get roughly what it represents within about two seconds? If the honest answer is "only if you already know what it's supposed to mean," the concept has failed, no matter how clever the reasoning behind it was.

This is the mistake worth naming directly: a generic shape animated nicely is still a generic shape. A dot moving in a loop does not read as "your data" just because the surrounding copy says so — a heartbeat-shaped line reads as a heartbeat on its own. The specific *form* of the elements has to recognizably relate to the real thing being represented, not just the composition or the fact that something is moving. If the concept only works with the label attached, go back to Step 2 and pick a more literal, more specific metaphor, even if it feels less clever — obvious-and-good beats subtle-and-missed every time.

Score this formally against the "obviousness" axis in the grading rubric in `SKILL.md` before moving on to Step 4.

### Step 4 — Choose the trigger to match the content, not by default

- **Ambient, looping** — for atmosphere-setting sections. Hero backgrounds, particle fields, a border that's always gently moving.
- **Scroll-triggered reveal** — for narrative or proof moments. Scramble-to-text headlines, count-up numbers, cards scattering into place as the section enters view.
- **Interaction-triggered (hover/tap)** — for exploratory or browsing content. A materials card that opens, a speaker wheel that responds to selection, tabs that swap on click.

Defaulting every section to "fade up on scroll" is the tell that this step got skipped.

### Step 5 — Keep it singular, and never repeat the same signature move twice on one page

One clear idea per section, executed with restraint. Subtle and distinct beats loud and stacked — the goal is a page where each section is quietly, specifically doing its own thing, not a page repeating the same trick eight times. If two sections end up leaning on the same device (two hub-and-spoke diagrams, two scramble reveals), change one of them, even if both look fine in isolation.

### Step 6 — Sanity check before moving on

- Does the section still function with the animation stripped out (accessibility, reduced motion)?
- Does every interactive element have a visible keyboard focus state, not just a mouse hover state?
- Does it cost real performance? Prefer cheap rendering primitives over expensive ones inside anything that runs continuously — simple shapes over emoji or heavy images in a canvas loop, for instance.
- Does it fit the typeface, color system, and headline mechanism already chosen for this project, or does it introduce a one-off style that clashes with everything else on the page?
- Has this exact signature move, or this exact animation primitive, already been used elsewhere on this page, or on the last project logged in `references/build-log.md`? If so, change it.

---

## 4 Standing Taste Rules

*Source: `landing-page-craft/references/taste-rules.md`*


A checklist of patterns confirmed across multiple past builds (Allowance, didii, Revolut Founder Mode, TrashPay, FlutterBytes Conference). Use this during the build pass and especially during the section-by-section quality check.

### The icon-grid feature section is close to mandatory

Every one of the five projects has a compact grid (2x3 or similar) of icon plus short title plus a one-to-two-sentence description, explaining "here's what this does." Never expand these into paragraphs. If a feature needs more explanation than two sentences, it belongs in its own dedicated section, not a bigger card in this grid.

### Always use a real custom icon library — never emojis where an icon belongs

Icons come from a defined, professionally-drawn icon set — Lucide, Phosphor, Heroicons, or Tabler are the defaults — chosen once per project and used consistently, so every icon on the page shares one visual language (stroke weight, corner radius, level of detail). Never drop an emoji into a spot where an icon is meant to go: emojis render inconsistently across platforms, clash with the type and color system, and instantly read as unconsidered. Where an icon can be given a subtle animation (a draw-in on scroll, a gentle state change on hover), prefer that over a static glyph, especially inside a card.

### The top navbar stays visible, with a translucent blurred fill

Unless the brief explicitly says otherwise, the top navigation is always visible as the visitor scrolls (sticky/fixed), with a fill at around **80% opacity plus a background blur** (backdrop-blur) so content scrolling underneath is softly visible through it rather than hidden behind a solid bar. This keeps navigation reachable at every scroll position while staying light and glassy rather than a heavy opaque block. Only drop the always-visible behavior when there's a deliberate reason and it's been stated.

### Headlines never render plain — but the mechanism is a per-project choice

Five projects, five different treatments, each applied consistently across every major headline on that one page (not mixed within a single page):

- **Temporal scramble** — digits or random characters resolve into the real text on scroll into view (Allowance).
- **Selective letter coloring** — specific letters within words get a static accent color, consistent every time that headline appears (didii).
- **Bold-plus-soft two-line contrast** — an assertive white line followed immediately by a softer gray qualifying line underneath (Revolut: "Every screen has a job. / None are decorative.").
- **Per-line color/weight assignment** — each line of a multi-line headline gets its own color (TrashPay: white / brand-accent / gray across three lines).
- **Letters replaced by icons** — a specific double-letter inside a headline word is swapped for a small animated icon (FlutterBytes: the "tt" in "Flutter").

Pick one mechanism early and use it everywhere a headline needs weight on this project. Don't invent a new one per section.

### Big numbers always animate in

Stat numbers (impact metrics, pricing, counts) get a reveal, never a static render: count-up from zero, an outline that sweeps into a solid fill, or a character scramble that resolves. This applies to any number rendered at headline size, not just a dedicated stats section.

### Fixed-dimension containers around anything that cycles or swaps content

Any element that auto-rotates, swaps state, or changes size (tabs, carousels, an image that changes on hover) needs a fixed height and width container around it. Otherwise the surrounding layout jumps every time the content changes, which reads as broken even when the content itself is fine.

### Default to one-thing-expanded, not a static equal-weight grid, for 3+ parallel options

When there are three or more parallel categories, use cases, or steps to explain, default to an auto-cycling or interactive single-focus display — one item expanded or active at a time, the rest visible but collapsed — rather than a flat grid where everything has equal visual weight all the time. This is the single most repeated interaction pattern across all five projects, whether the trigger is auto-cycling, hover, or click.

### On multi-sided products, give each audience its own consistent accent color

If the product serves more than one kind of user (consumers and businesses, for instance), assign each audience a color early and reuse it everywhere that audience is addressed, not just once. Done well, the color becomes a wayfinding device: the visitor learns "this color means the business-facing content" scrolling through the page, without being told explicitly.

### Show before/after concretely, per scenario — never state the benefit once, abstractly

If the pitch is "this used to be hard, now it's easy," don't say that once in the hero and move on. Show the specific old pain next to the specific new resolution, repeated for each real use case, in the product's actual voice. A single abstract claim is much weaker than several small concrete contrasts.

### Small colored status or availability badges on list items

Any list of options, materials, or features that have real status (live vs. coming soon, available vs. pre-order, healthy vs. near-limit) should show that status as a small colored pill directly on the item, not as plain accompanying text.

### Rotate through named layout archetypes, don't default to one

Five structural patterns to choose between per section, tracked so consecutive sections — and, over time, consecutive projects — don't repeat the same one:

- Title and subtitle above, the concept below it
- The concept above, title and subtitle below it
- Title and subtitle on the left, the concept on the right
- Title and subtitle on the right, the concept on the left
- The concept surrounding a centered title and subtitle — works well specifically when the title and subtitle are short

Check `references/build-log.md` for what recent sections and recent whole projects used, and pick something that hasn't just been used.

### Cards are a default to resist, not a neutral container

A bordered, rounded-rectangle box is the single most common container in generic web design, and reaching for it automatically is itself part of the blandness to avoid. Prefer fading divider lines to separate content where that's enough structure on its own. Where grouping genuinely needs a contained shape, look for something more considered than a plain box before settling for one.

**Cap the whole page at one or two sections that use cards at all** — if three or more sections are reaching for cards, most of them should be redesigned around dividers, a scattered/staggered arrangement, or a genuinely different container. Cards are the exception on a page, not the connective tissue.

And a card that does earn its place is never a plain box. It carries at least one deliberate touch of customization:
- a subtle shiny/glossy gradient fill (low-contrast, adds depth without noise — see the gradient rule below),
- a glass-like, semi-transparent border or stroke, or a frosted/backdrop-blur surface,
- an animated icon or other live element inside it,

plus a real hover interaction — a lift, a border glow, a color shift — never a static box that just sits there. A plain flat-fill bordered card with a static emoji and no hover is the exact failure this rule exists to prevent (flagged directly on the Flare build).

### Don't let one animation primitive become the default for everything

A dot or particle traveling along a path is one valid device, not the only one. A line that draws itself from one point to another — a stroke revealing progressively, like Allowance's hero — is an equally strong, visually distinct alternative. Keep a small set of different primitives in rotation, and never reuse the exact same one twice on a single page.

### Keep titles short and subtitles concise

Section titles and hero titles should be as short as they can be while still saying the thing — a few punchy words beats a full sentence. Subtitles should be as concise as possible: one tight line that adds what the title can't carry, not a paragraph restating it. Long titles and rambling subtitles are the default-template tell; sharpen them down before styling them.

### Two-part section titles go on two lines, in Title Case — applied with context

When a section title is naturally two parts — typically split at a `;`, `-`, or `,` ("Six things, one template.") — put the second part on its own line rather than running both together in one sentence, and set every major word with an initial capital, including "The." "Six Things" / "One Template." reads as a considered, designed title; the single run-on sentence reads as an afterthought.

Apply this with judgment, not mechanically: don't break so that a single lonely word sits on one line while the rest drops to the next, and don't force a two-line split on a title that's genuinely short enough to sit comfortably on one. The goal is a balanced, deliberate-looking pair of lines — if the split would look awkward or orphan a word, keep it on one line instead.

### If a title is unavoidably long, de-emphasize its tail rather than shrinking the whole thing

When a hero or section title can't be made short, don't render the whole thing at one big size — pick the less-essential part (preferably the last divisible part) and set it at a smaller size than the main part, while keeping it clearly visible and obviously part of the same title. This preserves a strong focal size for the words that matter and stops a long title from reading as one flat wall of large text. It's a size contrast within the title, not a hierarchy that hides anything — the smaller part still has to be very obvious.

### Generous spacing between sections — about 1.75x whatever feels sufficient

Sections that sit close together read as cramped and undifferentiated regardless of how good any individual section is. Default to roughly 1.75 times the vertical spacing that would otherwise feel like enough. Sections should never feel adjacent to their neighbors.

### Overall side padding is about 4–8% of screen width — default to 4%

The page's left/right gutter should be roughly 4–8% of the viewport width, and **4% most of the time** so there's plenty of horizontal room for content to breathe and stretch. Reach toward 8% only when a section deliberately wants a narrower, more contained measure (a long text passage, a centered focal moment). This is a horizontal container rule and is separate from the generous *vertical* spacing between sections above — set it as a responsive value (a percentage or a clamp), not a fixed pixel margin, so it holds across viewport sizes, and tighten it appropriately on mobile where 4% of a small screen is too little.

### Subtle gradients add depth without adding noise

A flat fill isn't always the right call. A soft gradient — radial or linear, low-contrast — behind a card, inside an icon container, or washing gently across a section background, adds real depth and richness without competing with content the way a busy pattern or a loud color block would. Reserve strong flat color for the moments meant to actually grab attention (a primary button, an active state); let ambient depth come from a gradient that's barely noticeable until you look for it.

### Not every site is dark — pick the theme that actually suits it, and vary section backgrounds

Dark theme is not the default. Choose light or dark based on what genuinely fits the brand, the audience, and the imagery — a bakery, a fashion label, or an airy editorial product often reads far better light; plenty of others suit dark. Decide deliberately as part of the type-and-color step, not by habit.

Whichever base theme is chosen, the whole page should not be one single flat background top to bottom. Give some sections their own distinct background — a value close to white or close to black (a step off the base), or a subtle gradient — so there's rhythm and separation between sections. The rule is just that a differentiated section's background is clearly *not* the same as the surrounding sections; it shouldn't be a jarring loud color block (that stays reserved for genuine attention moments per the gradient rule), but it should be visibly its own surface.

### Ambient background texture stays almost illegible at rest

Decorative background motifs — circuit lines, particle fields, connection lines, watermark wordmarks — should sit at very low opacity and never compete with foreground content for attention. Presence, not prominence.

### Voice and copy are a taste surface too, not just visuals

Word choice, punctuation, and small verbal puns carry brand personality as much as color and type do. Match the copy's actual voice to the audience, and don't be afraid of a genuinely audience-specific metaphor for a whole section's framing, not just its word choice — a team-credit section reframed around "commits" for a developer audience, for instance, rather than a generic "meet the team."

Don't name competitor brands in the copy — direct or indirect — unless the person has specifically asked for it (a case-study/portfolio page reimagining a named company is the obvious exception, and it's stated). Make the point through the value itself ("no more juggling five separate tools") rather than by calling out a rival by name.

### The design-token pattern, if the site needs light/dark theming or is going to production

Define colors as space-separated RGB channel values in CSS custom properties, so Tailwind's opacity-modifier syntax still works on top of them:

```css
:root { --color-navy: 10 20 40; }
html.light { --color-navy: 245 247 250; }
```

```
/* usage */
background: rgb(var(--color-navy) / 0.5);
```

And keep one clean semantic rule for raw color values: a hardcoded `text-white` (or equivalent) only belongs on an element whose background is guaranteed constant regardless of theme, like a button that's always a fixed brand color. Everything else sitting on a background that changes between light and dark needs a theme-aware token instead.

---

## 5 Site Types

*Source: `landing-page-craft/references/site-types.md`*


Seven shapes. The first three are drawn from past builds; the last four (business, hybrid, European, mini-business) are defined categories to build toward. The taste rules and the signature-move framework apply to all of them; what differs is which sections belong and — for the business, European, and mini-business types — how heavily the page leans on real photography and how the hero is treated.

### Product landing page

Examples: Allowance, didii, TrashPay.

Typical section inventory: hero, icon-grid feature overview, how-it-works (often per-audience if the product is multi-sided), pricing (even pre-launch — show real numbers behind a waitlist CTA rather than hiding pricing), social proof / testimonials (matched to different personas if multi-sided), a trust or security section, a final CTA that often echoes the hero's headline verbatim as a closing loop, footer.

Distinguishing traits: usually pre-launch or early-stage, so the primary CTA is a waitlist or "get early access" rather than a direct purchase, but it still shows full product detail rather than a vague "coming soon."

### Portfolio / case-study page

Example: Revolut Founder Mode (a designer's own concept pitch, not a real shipped product).

Typical section inventory: hero framed as "[real company] → concept by [name]," a problem statement (why the current thing falls short), the concept's own feature grid, a detailed screen-by-screen breakdown, a "why this matters" section using real numbers from the actual company being reimagined (to justify the exercise's relevance), a designer bio block, "reach out for more info" instead of a waitlist or purchase CTA.

Distinguishing traits: no pricing, no waitlist — the whole page is a pitch for the designer's thinking and taste, not a product people can use today. The bio block and the "why this matters" stats section are close to mandatory here and don't belong on a product page.

### Event / conference page

Example: FlutterBytes Conference.

Typical section inventory: hero with a ticket CTA and key dates, "how it works" or what to expect, a speaker showcase (works well as an interactive wheel or ring rather than a flat grid), a past-editions history or timeline if this isn't the first edition, organizing-team credit (consider framing this in language native to the audience rather than a generic "meet the team"), sponsors, agenda/schedule, apply-to-speak or apply-to-volunteer links.

Distinguishing traits: strongly benefits from an audience-native vocabulary and metaphor somewhere prominent, not just as flavor text, since the entire premise is a gathering of a specific community rather than a generic consumer sell.

### Business page

Examples: a fashion label, a bakery, a café, a salon, a photographer, an interior studio — an established real-world business selling something that already exists, not a startup pitching a future product.

Typical section inventory: an image-forward hero (the product, the space, or the work itself, not an abstract concept), a signature offering or collection showcase (lookbook, menu, service list, gallery), an about/story section grounded in real photography of the people or place, social proof as real customer photos or reviews rather than logo walls, location/hours/contact, and a booking, order, or enquiry CTA. Pricing is usually shown directly (a menu, a price list) rather than hidden behind a waitlist.

Distinguishing traits — this is the important one: **the business page is image-heavy by design.** Aim for roughly **75% of sections to be built around real photography** — the product, the food, the space, the work, the people. The signature-move framework and the animation rules still fully apply, but here they layer *on top of* strong imagery (a lookbook that scrolls or parallaxes, a menu card that reveals detail on hover, a gallery with a considered reveal) rather than substituting an abstract vector concept for a photo. Because real photos carry so much of the weight, this is the type where asking for actual photography up front (per `SKILL.md`'s photo rule) matters most — an image-heavy page built on faked or stock imagery falls apart. If genuine photos aren't available, say so plainly and treat that as a blocker to resolve, not something to paper over with gradients.

### Hybrid

A deliberate mix of two or three of the other types. Examples: a product launch that's also promoting a launch event (product + event), a design studio that sells a product and shows a portfolio of past work (business + case-study), a conference with a paid product attached (event + product).

How to structure it: pick the **dominant type** first — the one that owns the primary CTA and the overall goal — and use its section inventory and spacing as the backbone. Then borrow only the specific sections the secondary type genuinely needs (an event's dated-agenda and ticket block, a case-study's stats-and-bio pair, a business's image-forward gallery) and weave them in where they fit the narrative, rather than bolting a whole second page on the end. Keep one core concept, one type/color system, and one headline mechanism across the whole thing — the mix is in the sections, not in a split personality. Log in the build entry which types were combined and which was dominant, so the pattern is traceable later.

### European website

A clean, restrained, premium-feeling site in the style of high-end European studio work and the best paid Framer templates — lots of calm space, confident typography, real photography, and quiet motion. It uses all the same foundations as the other types (the signature-move framework, the taste rules, the type/color and theme decisions); what makes it its own category is the hero treatment and an overall restraint.

**The hero is deliberately simple and photo-led:**
- Fetch and **download** one or more suitable real photographs from **Unsplash, Pexels, or Pixabay** (all free to use) and use them as the hero's background image(s) — download them into the project as local assets rather than hot-linking, and pick images that genuinely fit the brand's subject, mood, and palette rather than generic filler. Ask the person first if they'd rather supply their own photography.
- Present the image(s) inside a **rounded rectangular frame about 98% of the viewport width** — the signature premium-Framer look — with **corner radius around 20–32px**. The frame sits centered with a small, even gutter on each side.
- **Keep the hero uncomplicated.** No busy signature-visual concept layered on top, no particle systems, no competing animated overlays — the photograph and the headline carry it. The headline still follows the headline rules (never plain, one mechanism), and quiet, tasteful motion is welcome (a slow subtle zoom/parallax on the image, a soft fade-up on the text), but the hard rule about every hero having one signature idea is satisfied *by the framed-photo treatment itself* here — that restraint is the concept.

Typical section inventory: the framed photo hero, a concise intro/positioning statement, a small feature or offering overview, a photography-forward showcase or gallery, social proof, and a simple contact or enquiry CTA. **No waitlist** — this type is not a pre-launch startup pitch. Keep the whole thing simple, but not boring: the interest comes from beautiful imagery, generous space, confident type, and restrained motion rather than from a dense stack of signature concepts.

Distinguishing traits: restraint is the point. Where a product page earns its keep with a distinct signature move in every section, a European site earns it with taste, spacing, photography, and polish. Fewer loud ideas, executed impeccably.

### Mini-business landing page

Examples of the audience this serves: a machinery dealer, a bulk exporter, a manufacturer, an industrial supplier, a wholesaler — established, often B2B, often traditional businesses that are genuinely operating already but have **no website at all**. The job of this page is unusually specific: it isn't just marketing, it's the first piece of digital credibility this business has ever had, often built *to convince the business itself* that having a real web presence is worth it. Every choice should serve that: would a skeptical buyer, or the business owner themselves, look at this and immediately feel the business just became more serious and more trustworthy?

**Exactly four sections, always — no more, no fewer:**

1. **Hero.** Confident, premium, photo-led. See the five hero iterations below — rotate between them the same way signature concepts rotate elsewhere, and check `references/concept-gallery.md` before defaulting to the same one repeatedly.
2. **Offering.** A tight overview of what the business actually does or sells — product range, service categories, or capability summary. Treat this like a compressed version of the icon-grid feature section: a handful of clear categories (machinery types, export capabilities, service lines), each with a short label and one line of description, not paragraphs. Photography here is welcome and encouraged (real product/facility shots) over abstract icons where photos are available.
3. **Proof.** The section doing the actual convincing. Real trust signals only — years in operation, volume/scale numbers (units shipped, tonnage exported, countries served, clients served), certifications or quality standards, client/partner logos, a short real testimonial if one exists. Numbers here follow the standing rule: they animate in, never render static. This section is not optional filler; for a business with zero prior online presence, this is what makes the rest of the page believable.
4. **Contact us.** Always present, in every build of this type, without exception. Give both a direct-contact block and a branded enquiry form:
   - **Direct contact:** phone number, email, and — since this audience skews trade/export/B2B where it's the norm — WhatsApp where relevant, plus location/address and business hours if applicable. Make these tappable/clickable, not just printed text.
   - **Branded enquiry form:** fields suited to a B2B enquiry (name, company name, email, phone, enquiry/message), styled in the site's own design, forwarding to a Google Form via its pre-fill link per the standing forms rule above in `SKILL.md` — the same ask-early, ask-for-the-pre-fill-link process applies here.
   - A confident CTA framing fits better than a generic "get in touch" — "Request a Quote," "Book a Call," "Talk to Our Team."

**The five hero iterations to rotate between** (reference patterns, not a menu to pick from mechanically — invent a genuine sixth if none fits):

- **Full-bleed overlay hero with a floating nav pill.** A full-bleed premium photo (people, product, or facility), a rounded floating pill navbar sitting on top of the image rather than a full-width bar, the headline overlaid in the lower third in a mixed serif/italic-accent treatment, a short subtitle, a pill-shaped primary CTA with a small circular icon, and one or two floating cards in a corner surfacing a secondary offer or credential.
- **Full-bleed atmospheric photo hero.** A single full-bleed photo with a dark tonal overlay for legibility, a large serif headline anchored to one upper corner, a short subtitle and a single solid-accent-color CTA button anchored to the same side, transparent navbar sitting directly on the image.
- **Circled-keyword hero with a frosted stat card.** A photo hero where one keyword inside the headline gets a circled or pill-outlined accent treatment, a small eyebrow label plus one-line service blurb, a CTA button, and a floating frosted/glass stat card (a real number — revenue, output, delivery volume) overlapping the photo; a client-logo strip sits directly beneath the hero as an immediate trust signal.
- **Split image/text hero with a trust cluster.** Two-column hero: a real photo fills one side edge-to-edge, the other side is calm negative space holding the logo, a small avatar-cluster trust indicator ("50+ businesses trust us" or similar, with real or representative faces), and a bold headline anchored to the bottom of the text column.
- **Text-first hero into an arched photo reveal.** The hero opens with type only — an eyebrow label, a headline with one keyword in an accent color, a short paragraph, and a CTA — then immediately below, a full-width photo masked with a soft arch/curve cutout at the top edge and a "scroll down" indicator centered over it.

**Premium execution, not just premium description:** real, professional photography is non-negotiable here (source and download from Unsplash/Pexels/Pixabay per the European type's method if the business can't supply its own, but always ask first whether real photos of their actual product, machinery, or facility exist — those beat stock every time for this category specifically, since credibility is the whole point). Favor glass-morphism/frosted-blur floating cards for stat callouts, a confident accent CTA color against a mostly neutral photo-driven palette, and generous negative space even inside a four-section page — cramming four sections doesn't mean cramming each section. The floating stat/credential card inside the hero is part of that hero's signature move and doesn't count against the standing one-or-two-sections cards cap elsewhere in `references/taste-rules.md`; a plain bordered card used as a generic container inside the Offering or Proof sections still does.

Distinguishing traits: this is the only type with a hard section-count ceiling, and the only type explicitly built to serve as someone's very first web presence — the bar for "does this look trustworthy and premium" is higher here than almost anywhere else in this skill, precisely because there's no existing brand reputation to lean on.

### If it's none of these

Treat it as closest to a product landing page and adapt — the underlying taste rules and the signature-move framework don't depend on which of these seven it is.

---

## 6 Section Design Bank

*Source: `landing-page-craft/references/section-bank.md` (methodology, style families, category index) and `landing-page-craft/references/section-bank.csv` (the full 194-row dataset, appended below)*


A library of **194 described website sections** (155 unique styles — some are re-listed or minor variants, cross-referenced in the index below) living in `references/section-bank.csv`. Each row is one section design, described in enough detail to actually build from: layout hierarchy, background treatment, typography and spacing specs, and motion/animation mechanics, plus kebab-case tags and sample use cases.

This bank is **raw material, not a template catalog.** The skill's core promise — every section has a signature concept specific to *this* brand — does not change. The bank's job is to make the concept pass richer and faster: instead of inventing every layout, background, and motion idea from a blank page, shortlist real described patterns, then adapt them until they belong to the project.

---

### How to read the CSV

Columns: `Section ID, Category Name, Section Style Name, Description & Layout Hierarchy, Background Elements, Typography & Spacing Specs, Motion & Animation Mechanics, Helpful Tags & Comments, Sample Sections / Use Cases`.

Practical notes:
- **Grep it, don't parse it.** Some rows contain unquoted commas, so strict column splitting mis-aligns on a few rows — read matching rows whole. Find candidates by ID (`^HERO-05`), by tag (`glassmorphism`, `bento`, `brutalist`, `full-bleed-nature`), or by use-case words (`booking`, `pricing`, `lookbook`).
- The **index below** is the fast path: skim the category you need, note 2–3 candidate IDs, then grep the CSV for their full rows.

### How the bank plugs into the build process

1. **During the per-section intake (step 5 in `SKILL.md`):** after naming what the section is about, pull **two or three candidate rows** from the bank — matched by section category first (hero, pricing, FAQ, footer…), then by the project's style direction and mood tags. Weigh them against each other and against an invented-from-scratch option. Sometimes the blank-page idea wins; that's fine — the bank raises the floor, it doesn't cap the ceiling.

2. **Adapt, never transplant.** A bank row arrives with its own palette, typefaces, and pixel specs. Those belong to the row, not to your project:
   - **Colors:** re-map every hex in the row to the project's confirmed palette. The row's lavender/periwinkle/neon-yellow is a description of *contrast roles* (base, accent, glow), not colors to ship.
   - **Type:** the row's px sizes are proportions, not law. Re-express them in the project's type scale and confirmed typefaces.
   - **Copy and imagery:** always the project's own. A "botanical glassmorphic capsule" row used for a machinery exporter becomes frosted capsules over the exporter's own facility photography — the *mechanic* transfers, the skin doesn't.
   - **Motion:** the motion column is the most transferable part — dash-offset draws, odometer count-ups, flex-grow column expansion, staggered entries, parallax float offsets, marquee crawls, mask reveals. Treat it as a motion vocabulary. The standing rule still applies: never repeat the same animation primitive twice on one page.

3. **The two-second test still governs.** A bank row is a layout skeleton, not a concept. After adapting one, the section must still pass the signature-move checks in `references/signature-moves.md` — would a stranger get what this section represents, for this specific brand, without a caption? If the adapted row reads as "nice generic section," push the brand's own metaphor into it or drop it.

4. **Track usage to force variety.** When a build ships, log which bank IDs influenced which sections in that build's `references/build-log.md` entry (e.g. `Bank rows used: HERO-05 (adapted: hero), FAQ-04 (adapted: FAQ), B2B-13 (proof baseline)`). Before starting a new build, check the last one or two entries and **don't lean on the same rows again** — same rule as signature moves and typefaces. With 155 unique styles there is no excuse for two consecutive projects rhyming.

5. **Mix across categories deliberately.** The bank's categories are labeled by *function* (hero, pricing, footer) and by *mood family* (Minimalist, Organic/Clean-Tech, Editorial/Gallery, B2B/Fintech). A coherent page usually draws its rows from one or two mood families that match the project's chosen style direction — cherry-picking a brutalist hero, an aurora-pastel feature deck, and a foggy-forest footer onto one page produces the "split personality" failure. Pick the mood lane first, then shop within it, borrowing outside it only as a deliberate accent.

### Style families the bank teaches

Use these as named style directions when deciding the project's visual direction during the type/color/theme step — one dominant family per project, chosen for brief-specific reasons:

- **Aurora / pastel glow** — soft radial gradient meshes, glassmorphic icon wells, high-key canvases (HERO-01, SEC-11, B2B-08).
- **Neo-glow dark tech** — charcoal/black bases, neon accent glyphs, rotating gradient borders, engineering grid overlays (PRC-02, B2B-15, B2B-45, FAQ-06).
- **Clean-tech organic** — deep greens, nature photography under floating white cards, milestone timelines, lime accents (SEC-04/05/06, ORG-01…05, FT-01).
- **Editorial / brutalist** — giant canvas-filling type, overlapping media frames, marquee crawls, wireline grids, high-contrast color blocks (HERO-05/14, CON-02/03, EDT-01/09, B2B-63/65).
- **Minimalist high-key** — off-white fields, zero decoration, generous space, type-led statements with a single accent color (MIN-01…04, EDT-15, B2B-103).
- **Luxury / premium showcase** — 3D product renders, vertical script watermarks, matte black conversion containers, full-bleed hospitality photography (HERO-13/15/16, B2B-56/67/72, EDT-04…07).
- **Corporate B2B / fintech** — bento capability matrices, dashboard mockups, odometer metric baselines, logo-proof grids (B2B-13/21/33/37/38/48/80).

These families also slot straight into the existing site types: **European website** and **mini-business** builds shop mostly in Luxury/premium showcase + Minimalist high-key; **business pages** in Clean-tech organic + Luxury showcase; **product pages** in Aurora, Neo-glow dark, or Corporate B2B depending on the brand's temperature.

### Growing the bank

The bank is append-only, like the concept gallery:
- Add new rows to `section-bank.csv` with the next free ID in the right category (or continue the B2B numbering for anything that doesn't fit an existing category).
- When a build invents a section good enough to reuse, describe it in the CSV's own column language (layout hierarchy / background / type specs / motion mechanics / tags / use cases) and add it.
- Never delete rows. If a row keeps producing weak results, note that in the build log instead.

---

### Index

#### Hero Sections

- **HERO-01** — Aurora Glow Floating App Hero · `hero-section, aurora-glow, saas-mockup, centered-hero`
- **HERO-02** — Isomorphic Tech Flow Blueprint Hero · `isometric-hero, tech-blueprint, saas-landing, workflow-visualization`
- **HERO-03** — Radiant Gaming Hub Platform Hero · `gaming-hero, glowing-gradient, integrated-icons, community-hub`
- **HERO-04** — Web3 Neo-Glow Metrics Hero · `neo-grid, bento-metrics, input-hero, web3-tech`
- **HERO-05** — Dark Cinematic Typography Hero · `cinematic-hero, dark-mode, editorial-typography, high-contrast`
- **HERO-06** — Organic Clean-Tech Horizon Hero · `clean-tech, curved-frame, environmental-tech, centered-stack`
- **HERO-07** — Fan-Out Tilted Graphic Card Hero · `fanned-cards, tilted-ui, centered-typography, dark-mode-hero`
- **HERO-08** — Editorial Column Vertical Splitting · `vertical-accordion-grid, editorial-columns, input-hero, staggered-typography`
- **HERO-09** — Ultra-Clean Product Showcase Hero · `editorial-layout, asymmetrical, product-showcase, minimalist-tech`
- **HERO-10** — Asymmetrical Organic Split Hero · `organic-split, color-block-wave, vector-illustration, editorial-hero`
- **HERO-11** — Handheld Device Mockup Hero · `handheld-device-mockup, saas-conversion-hero, radial-gradient-wash, medical`
- **HERO-12** — Flagship SaaS Platform Blue-Sky Hero · `blue-sky-hero, integration-umbrella-arch, concentric-logo-bridge, saas`
- **HERO-13** — Luxury Balanced Showcase Hero · `luxury-showcase, 3d-hardware-render, watermark-sidebar, premium-landing`
- **HERO-14** — Brutalist Overlapping Lookbook Hero · `brutalist-grid, overlapping-media, cursive-typography-overlay, brutalist`
- **HERO-15** — Full-Bleed Nature Retreat Hero · `full-bleed-nature, luxury-retreat, forest-cabin, centered-conversion`
- **HERO-16** — Immersive Dark Interior Hero · `dark-interior-hero, brutalist-text-overlay, booking-scheduler-baseline, luxury`

#### 2nd / Feature Sections

- **SEC-01** — Minimalist Split-Header Blog Grid · `minimalist, split-header, card-grid, article-hub`
- **SEC-02** — Tabbed Feature Module Block · `tabbed-interface, solid-background, feature-showcase, two-column-split`
- **SEC-03** — Minimalist Balanced Feature Grid · `services-grid, minimal-icon-box, clean-alignment, symmetrical`
- **SEC-04** — Clean-Tech Asymmetrical Data Grid · `clean-tech, data-visualization, asymmetrical-grid, bento-metrics`
- **SEC-05** — Split-Pane Hybrid Feature Column · `split-feature, interactive-list, clean-tech, media-showcase`
- **SEC-06** — Fluid Organic Field Feature Row · `organic-background, white-bento-cards, clean-tech, nature-tech`
- **SEC-07** — Corporate Creative Portfolio Banner · `editorial-grid, agency-portfolio, mosaic-layout, asymmetrical-text`
- **SEC-08** — Clean-Tech Asymmetrical Accordion Stack · `split-faq, clean-tech-ui, asymmetrical-accordion, modern-minimalist`
- **SEC-09** — Glassmorphic Column Hub · `glassmorphism, glowing-gradient, five-column-grid, feature-hub`
- **SEC-10** — Asymmetrical Interactive Use-Case Split · `split-use-case, interactive-accordion, layered-mockups, b2b-features`
- **SEC-11** — Pastel Aurora Glass Feature Deck · `pastel-aurora, glassmorphism-icons, bento-features, symmetrical-deck`
- **SEC-12** — Inset Workspace Dashboard Split · `dashboard-mockup, text-marker-highlight, checklist-timeline, editorial-feature-split`

#### Pricing Sections

- **PRC-01** — High-Contrast Bento Pricing Grid · `pricing-grid, bento-style, featured-card, saas-conversion`
- **PRC-02** — Dark Neo-Glow Tiered Pricing Matrix · `pricing-grid, neon-border-glow, dark-mode, bento-pricing`
- **PRC-03** — Bi-Color High-Contrast Pricing Matrix · `pricing-matrix, inverted-color-block, mint-green-ui, vertical-stack-pricing`
- **PRC-04** — High-Contrast Bento Subscription Matrix · `pricing-grid, bento-pricing-matrix, color-inversion-block, centered-conversion`

#### FAQs

- **FAQ-01** — Full-Width Centered FAQ Accordion Stack · `accordion-stack, faq-section, interactive-list, clean-ui`
- **FAQ-02** — Split-Layout Minimalist FAQ Grid · `split-accordion, two-column-faq, bento-list, modern-minimalist`
- **FAQ-03** — Editorial Grid Accordion Showcase · `split-faq-grid, studio-media-frame, dark-mode-accordion, clean-alignment`
- **FAQ-04** — Glassmorphic Document Accordion Stack · `glassmorphism, typography-backdrop, sky-gradient, accordion-list`
- **FAQ-05** — Layered Progressive FAQ Dashboard · `faq-dashboard, capsule-conversion-card, interactive-accordion-stack, step`
- **FAQ-06** — Wireframe Matrix Accordion FAQ · `accordion-matrix-faq, wireline-grid-dividers, technical-coordinate, clean`

#### Footers

- **FT-01** — Structured Clean-Tech Subscription Footer · `clean-tech-footer, newsletter-capture, directory-columns, giant-watermark`
- **FT-02** — Luminous Mesh Capsule Footer · `capsule-footer, neon-mesh, brand-watermark, centered-conversion`
- **FT-03** — Minimal Gradient Baseline Utility Footer · `minimal-footer, gradient-wash, directory-columns, clean-alignment`
- **FT-04** — Low-Contrast Minimalist Contact Closure · `minimalist-footer-closure, neon-gradient-bleed, email-capture-form, footer`
- **FT-05** — Technical Coordinates Footer Closure · `technical-coordinate-footer, email-capture-form, minimal-directory, dark-mode-closure`
- **FT-06** — Wide Gradient Tech Directory Footer · `minimalist-footer, giant-watermark-base, email-capture-form, horizontal`

#### Testimonials

- **TEST-01** — Framed Carousel Testimonial Slider · `testimonial-slider, dark-mode, hanging-quotes, asymmetrical-carousel`
- **TEST-02** — Perspective Video Testimonial Slider · `perspective-slider, 3d-carousel, video-testimonials, dark-mode-review`
- **TEST-03** — Supply Chain Bento Testimonial Grid · `bento-testimonials, dark-teal-gradient, profile-portraits, clean-corporate`
- **TEST-04** — Asymmetrical Carousel Review Wall · `testimonial-carousel, high-key-social-proof, clean-corporate, slider`
- **TEST-05** — Inverted Contrast Review Board · `testimonial-board-matrix, inverted-color-split, text-marker-highlight, dark`
- **TEST-06** — Symmetrical Social Proof Slider · `testimonial-slider, high-key-social-proof, clean-corporate, symmetrical-carousel`

#### Contact Sections

- **CON-01** — Atmospheric Application Contact Form · `contact-hero, glass-form, sky-gradient, overlapping-typography`
- **CON-02** — Brutalist Typographic Form Overlap · `brutalist-grid, overlapping-form, giant-typography, high-contrast-brutalist`
- **CON-03** — Brutalist Capture Form Grid Matrix · `brutalist-form-matrix, neon-yellow-accents, benefits-checklist, dark-mode`
- **CON-04** — High-Contrast Split-Pane Contact Closure · `split-color-closure, neon-orange-pane, form-input-matrix, directory-menu`

#### Call-to-Action (CTA) Sections

- **CTA-01** — Scattered Thumbnail Call-to-Action Grid · `scattered-grid, parallax-thumbnails, centered-cta, high-contrast-dark`
- **CTA-02** — Inverted Contrast Dual-Pane Block · `diagonal-cut-portrait, inverted-color-split, large-scale-quote, b2b`
- **CTA-03** — Capsule Closure Conversion Footer · `capsule-conversion-card, geometric-glass-backdrop, directory-link-grid, sub`
- **CTA-04** — Giant Chroma Wordmark Transition Banner · `ribbon-banner, gradient-typography-logo, brutalist-text-cta, sub-footer`

#### Minimalist Design Tiers

- **MIN-01** — Asymmetrical Floating Step Matrix · `staggered-bento, giant-typography, gradient-swatches, process-flow`
- **MIN-02** — Asymmetrical Portrait & Capability Split · `split-capability-layout, mosaic-portrait-cards, clean-alignment, b2b-feat`
- **MIN-03** — Minimal Category Grid Showcase · `category-grid, pastel-cards, minimalist-photography, staggered-alignment`
- **MIN-04** — Minimal Balanced Step Walkthrough Block · `step-walkthrough-grid, minimal-icon-wells, symmetrical-text, clean-alignment`

#### Organic Field / Clean-Tech Tiers

- **ORG-01** — Alternating Industrial Capability Row · `alternating-grid, b2b-minimalist, warehouse-photography, floating-metrics`
- **ORG-02** — Clean Pastel Radial SaaS Hero · `pastel-bento-hero, text-marker-highlight, radial-gradient, saas-dashboard`
- **ORG-03** — Milestone Progress Checklist Row · `milestone-checklist, dashed-timeline, overlapping-badge, educational-ui`
- **ORG-04** — Frosted Glass Capsule Botanical Showcase · `glassmorphic-capsules, botanical-assets, organic-product-ui, interlocking`
- **ORG-05** — Frosted Glass Capsule Botanical Showcase (Var) *(same as ORG-04)* · `glassmorphic-capsules, panoramic-nature-field, organic-product-ui, align`

#### Editorial & Structural Gallery Tiers

- **EDT-01** — Cinematic Dark Strip Ribbon Banner · `ribbon-banner, infinite-text-marquee, centered-art-frame, dark-mode-transition`
- **EDT-02** — Alternating Capsule Portfolio Matrix · `portfolio-gallery-grid, horizontal-carousel, floating-arrow-cta, editorial`
- **EDT-03** — Vertical Ribbon Marquee Showcase · `vertical-accordion-grid, editorial-columns, ribbon-marquee, text-symmetrical`
- **EDT-04** — Asymmetrical Gallery Matrix · `asymmetrical-gallery, multi-scale-cards, luxury-lifestyle, retreat`
- **EDT-05** — Vertical Index Property Switcher · `vertical-index-switcher, property-showcase-frame, architectural-bento, clean`
- **EDT-06** — Property Recommendation Deck Split · `recommendation-deck, landscape-property-cards, symmetrical-alignment, travel`
- **EDT-07** — Editorial Property Description Stack · `split-header-matrix, asymmetrical-gallery-slider, two-column-copy-block, travel`
- **EDT-08** — Multi-Tabbed Category Amenity Grid · `category-filter-bar, amenities-grid, symmetrical-alignment, b2b-corporate`
- **EDT-09** — Editorial Museum Exhibition Banner · `brutalist-text-marquee, overlapping-canvases, vertical-accordion-grid, history`
- **EDT-10** — Fine-Art Chronological Flagship Hero · `fine-art-hero, cursive-typography-overlay, overlapping-media-cards, alignment`
- **EDT-11** — Asymmetrical Property Experience Grid · `asymmetrical-gallery-matrix, multi-scale-cards, luxury-lifestyle, onboarding`
- **EDT-12** — Wireframe Directory Matrix Footer · `wireline-grid-dividers, minimal-directory, brutalist-text-marquee, sub-footer`
- **EDT-13** — Milestone Checklist Accordion Panel · `milestone-checklist, horizontal-accordion-stack, overlapping-badge, travel`
- **EDT-14** — Advanced Booking Scheduler Stage · `booking-scheduler-stage, step-progression-baseline, horizontal-split-pane, checkout`
- **EDT-15** — Minimal Balanced Text Statement Block · `capabilities-statement, copper-accent-type, two-column-copy-block, clean`
- **EDT-16** — Advanced Booking Scheduler Stage (Var) *(same as EDT-14)* · `booking-scheduler-stage, step-progression-baseline, bento-cards-stack, fintech`

#### B2B Corporate & Fintech Overviews

- **B2B-01** — Asymmetrical Interactive Use-Case Split *(same as SEC-10)* · `split-use-case, interactive-accordion, layered-mockups, b2b-features`
- **B2B-02** — Pastel Aurora Glass Feature Deck *(same as SEC-11)* · `pastel-aurora, glassmorphism-icons, bento-features, symmetrical-deck`
- **B2B-03** — Inset Workspace Dashboard Split *(same as SEC-12)* · `dashboard-mockup, text-marker-highlight, checklist-timeline, editorial-feature-split`
- **B2B-04** — Low-Contrast Minimalist Contact Closure *(same as FT-04)* · `minimalist-footer-closure, neon-gradient-bleed, email-capture-form, footer`
- **B2B-05** — Technical Coordinates Footer Closure *(same as FT-05)* · `technical-coordinate-footer, email-capture-form, minimal-directory, dark-mode-closure`
- **B2B-06** — Wide Gradient Tech Directory Footer *(same as FT-06)* · `minimalist-footer, giant-watermark-base, email-capture-form, horizontal`
- **B2B-07** — Supply Chain Bento Testimonial Grid *(same as TEST-03)* · `bento-testimonials, dark-teal-gradient, profile-portraits, clean-corporate`
- **B2B-08** — Frosted Glass Carousel Overview · `frosted-glass-cards, horizontal-carousel, centered-conversion-cta, saas-showcase`
- **B2B-09** — High-Contrast Centered Bento Pricing · `pricing-grid, bento-pricing-matrix, color-inversion-block, centered-conversion`
- **B2B-010** — Technical Coordinates Footer Matrix · `technical-coordinate-footer, email-capture-form, minimal-directory, dark-mode-closure`
- **B2B-11** — Inline Horizontal Capabilities Slider · `capabilities-slider, horizontal-carousel, b2b-minimalist, isometric-illustrations`
- **B2B-12** — Symmetrical Social Proof Slider *(same as TEST-06)* · `testimonial-slider, high-key-social-proof, clean-corporate, symmetrical-carousel`
- **B2B-13** — Trusted Partner Marquee Baseline · `trusted-partner-row, corporate-marquee, metric-grid, social-proof-baseline`
- **B2B-14** — High-Fidelity Split Identity Login Card · `login-card, split-identity-form, social-sign-on, b2b-gateway`
- **B2B-15** — Dark Linear Metric Core Showcase · `dark-mode-grid, neon-blue-glyphs, asymmetrical-header, value-proof`
- **B2B-16** — Centered Isomorphic Supply Chain Hero · `isometric-network-hero, global-reach, b2b-saas, centered-conversion`
- **B2B-17** — Dynamic Fluid Liquid-Core Creative Hero · `3d-liquid-core, watermark-backdrop, capsule-video-tab, capability-marquee`
- **B2B-18** — Editorial Checklist Progression Split · `vertical-checklist, overlapping-analytics, b2b-minimalist, step-progression`
- **B2B-19** — Parallax Whirlpool Loop Footer · `whirlpool-vortex, capsule-conversion-card, directory-link-columns, sub-footer`
- **B2B-20** — Scattered Abstract Division Board · `scattered-gallery-grid, pastel-cards, 3d-geometric-objects, floating-arrow`
- **B2B-21** — Balanced Triple-Pane Production Showcase · `production-showcase, industrial-bento-grid, metric-baseline-panel, social-proof`
- **B2B-22** — Split-Pane Document Resource Grid · `resource-grid, vector-marketing-illustrations, split-feature-layout, minimal`
- **B2B-23** — Wide Wave-Gradient B2B Closure Banner · `wave-gradient-mesh, turquoise-globe-backdrop, directory-link-grid, conversion`
- **B2B-24** — Split-Pane Operational Sign-On Screen · `registration-card, split-pane-form, operator-portrait, step-progression-base`
- **B2B-25** — Biotech Coordinate Mesh Hero · `biotech-mesh-hero, 3d-coordinate-topography, asymmetrical-metrics, conversion`
- **B2B-26** — Split-Pane Visual Chronicle Progress · `split-chronicle, interactive-accordion-stack, media-showcase-frame, vector`
- **B2B-27** — Tabbed Multi-Pane Scenario Interaction · `scenario-simulation, neon-orange-filters, cinematic-media-frame, tabbed-ui`
- **B2B-28** — Cinematic Ambient Spark Media Hero · `cinematic-spark-hero, handheld-device-mockup, dual-tone-typography, live`
- **B2B-29** — Multi-Stage Pipeline Milestone Grid · `milestone-bento-cards, horizontal-pipeline-bar, 3d-molecular-assets, phase`
- **B2B-30** — Symmetrical Linear Team Identity Grid · `team-showcase-grid, wireline-grid-dividers, neon-role-tags, clean-alignment`
- **B2B-31** — Overlapping Presentation Deck Collage · `slide-deck-collage, donut-chart-data, text-marker-highlight, layered-cascade`
- **B2B-32** — Concentric Circle Value Proposition Grid · `concentric-wireframe-circles, brutalist-grid, neon-orange-icons, value-mesh`
- **B2B-33** — Comparative Metric Performance Panel · `comparative-data-bars, inverted-color-tier, oversized-stat-counter, b2b-mesh`
- **B2B-34** — High-Contrast Split-Pane Contact Closure *(same as CON-04)* · `split-color-closure, neon-orange-pane, form-input-matrix, directory-menu`
- **B2B-35** — Split-Screen Profile Showcase Hero · `split-hero-layout, profile-mockup, social-proof-badge, saas-conversion`
- **B2B-36** — Triple-Pane Graphic Feature Grid · `three-column-bento, gradient-wash-cards, clean-alignment, symmetrical-grid`
- **B2B-37** — High-Contrast FinTech Bento Matrix · `bento-capabilities-matrix, 3d-geometric-renders, asymmetrical-text, fintech`
- **B2B-38** — Flagship FinTech App Dashboard Hero · `fintech-hero-dashboard, 3d-mockup-cascade, text-marker-highlight, gradient`
- **B2B-39** — 3D Geometric Solution Bento Grid · `bento-services-grid, 3d-minimalist-assets, asymmetrical-alignment, b2b-corp`
- **B2B-40** — Asymmetrical Carousel Review Wall *(same as TEST-04)* · `testimonial-carousel, high-key-social-proof, clean-corporate, slider`
- **B2B-41** — Symmetrical Pastel Icon Division Board · `division-grid, pastel-cards, 3d-geometric-objects, staggered-alignment`
- **B2B-42** — Layered Progressive FAQ Dashboard *(same as FAQ-05)* · `faq-dashboard, capsule-conversion-card, interactive-accordion-stack, step`
- **B2B-43** — Vertical Milestone Timeline Progression · `milestone-checklist, dashed-timeline, software-mockup-frame, educational`
- **B2B-44** — Capsule Closure Conversion Footer *(same as CTA-03)* · `capsule-conversion-card, geometric-glass-backdrop, directory-link-grid, sub`
- **B2B-45** — Technical Wire-Grid Feature Block · `technical-coordinate, brutalist-neon, bento-capabilities, dark-mode-security`
- **B2B-46** — Immersive Lifestyle Portrait Folds · `lifestyle-portrait, glassmorphic-capsules, radial-gradient-wash, organic`
- **B2B-47** — Asymmetrical Editorial Split-Pane Hero · `editorial-hero-split, diamond-collage, asymmetrical-metrics-base, agency`
- **B2B-48** — Technical Analytics Bento Metrics Row · `bento-metrics-row, brutalist-neon-yellow, dark-mode-dashboard, social-proof`
- **B2B-49** — Handheld Device Mockup Conversion Hero · `handheld-device-mockup, saas-conversion-hero, radial-gradient-wash, medical`
- **B2B-50** — Brutalist Capture Form Grid Matrix *(same as CON-03)* · `brutalist-form-matrix, neon-yellow-accents, benefits-checklist, dark-mode`
- **B2B-51** — Iridescent Torus SaaS Landing Hero · `iridescent-3d-core, liquid-chrome-sphere, b2b-saas-hero, avatar-proof-row`
- **B2B-52** — Alternating Capsule Portfolio Matrix *(same as EDT-02)* · `portfolio-gallery-grid, horizontal-carousel, floating-arrow-cta, editorial`
- **B2B-53** — Vertical Ribbon Marquee Showcase *(same as EDT-03)* · `vertical-accordion-grid, editorial-columns, ribbon-marquee, text-symmetrical`
- **B2B-54** — Flagship SaaS Platform Blue-Sky Hero *(same as HERO-12)* · `blue-sky-hero, integration-umbrella-arch, concentric-logo-bridge, saas`
- **B2B-55** — Interactive Medical Card Carousel · `card-deck, fanned-carousel, bento-metrics, health-tech`
- **B2B-56** — Luxury Balanced Product Showcase Hero · `luxury-showcase, 3d-hardware-render, watermark-sidebar, premium-landing`
- **B2B-57** — Dual-Pane Luxury Presentation Row · `split-media-layout, luxury-branding, product-showcase, clean-corporate`
- **B2B-58** — Interactive Multi-Grid Persona Dashboard · `bento-dashboard-matrix, user-persona, progress-tracking-bars, dark-mode`
- **B2B-59** — Brutalist Overlapping Lookbook Hero *(same as HERO-14)* · `brutalist-grid, overlapping-media, cursive-typography-overlay, brutalist`
- **B2B-60** — Diagonal-Cut Monochrome Testimonial · `diagonal-cut-masks, chevron-imagery, asymmetrical-header, social-proof`
- **B2B-61** — Inverted Contrast Dual-Pane Block *(same as CTA-02)* · `diagonal-cut-portrait, inverted-color-split, large-scale-quote, b2b`
- **B2B-62** — Frosted Glass Capsule Botanical Showcase *(same as ORG-04)* · `glassmorphic-capsules, botanical-assets, organic-product-ui, interlocking`
- **B2B-63** — Kinetic Block Out Lookbook Grid · `brutalist-grid, color-block-panels, expandable-columns, brutalist`
- **B2B-64** — Technical Blueprint Software Showcase · `technical-blueprint, dashboard-mockup, text-marker-highlight, minimalist`
- **B2B-65** — High-Contrast Typographic Product Hero · `high-contrast-typography, streetwear-lookbook, asymmetrical-grid, dark-mode`
- **B2B-66** — Frosted Glass Capsule Botanical Showcase (Var) *(same as ORG-04)* · `glassmorphic-capsules, panoramic-nature-field, organic-product-ui, align`
- **B2B-67** — Premium Tiered Product Catalog Matrix · `product-catalog-grid, luxury-watch-assets, black-bento-cards, saas-cta`
- **B2B-68** — High-Key Grid Catalog Showcase · `product-catalog-grid, supplement-bottle-assets, white-bento-cards, grid-mesh`
- **B2B-69** — Horizontal Product Slider Marquee · `campaign-slider, fintech-cards, progress-tracking-bars, dark-mode-carousel`
- **B2B-70** — Overlapping Translucent Wireframe Hero · `3d-glass-tiles, geometric-parallax, high-contrast-editorial, baseline-status`
- **B2B-71** — Split-Contrast Premium Asset Showcase · `product-showcase, luxury-branding, asymmetrical-alignment, saas-conversion`
- **B2B-72** — Structured Matte Conversion Container · `capsule-conversion-banner, matte-black-card, luxury-product-showcase, cta`
- **B2B-73** — Balanced Multi-Column Industry Portals · `industry-vertical-grid, directory-menu-list, b2b-minimalist, clean-alignment`
- **B2B-74** — Asymmetrical Typographic Conversion Ribbon · `ribbon-banner, brutalist-typography-cta, star-rating-badge, minimalist`
- **B2B-75** — Multi-Pane Descriptive Product Catalog · `product-catalog-dashboard, drop-down-accordion, thumbnail-filters, clean`
- **B2B-76** — Split-Circle Abstract Macro Grid · `brutalist-split, product-handheld-asset, high-contrast-editorial, circles`
- **B2B-77** — Unified Dual-Pane Application Catalog · `tablet-mockup-dashboard, overlapping-widgets, high-key-product-catalog, saas`
- **B2B-78** — Kinetic Micro-Badge Brand Statement · `kinetic-typography, inline-micro-badges, vector-utility-glyphs, statement`
- **B2B-79** — Asymmetrical Circular Product Slider · `oval-bento-cards, horizontal-carousel, supplement-assets, social-proof`
- **B2B-80** — B2B Multi-Client Proof Grid · `wireline-grid-dividers, grayscale-logos, corporate-proof-baseline, symmetrical`
- **B2B-81** — Wide Gradient Tech Directory Footer *(same as FT-06)* · `minimalist-footer, giant-watermark-base, email-capture-form, horizontal`
- **B2B-82** — Giant Chroma Wordmark Transition Banner *(same as CTA-04)* · `ribbon-banner, gradient-typography-logo, brutalist-text-cta, sub-footer`
- **B2B-83** — Fine-Art Overlapping Canvas Hero · `fine-art-hero, overlapping-canvases, brutalist-yellow-type, baroque`
- **B2B-84** — Full-Bleed Nature Retreat Hero (Var) *(same as HERO-15)* · `full-bleed-nature, luxury-retreat, forest-cabin, centered-conversion`
- **B2B-85** — Split Symmetrical Architecture Slider · `property-slider, landscape-media-cards, symmetrical-alignment, travel`
- **B2B-86** — Blurred Instagram Grid Marquee (Var) · `social-proof-feed, polaroid-cards, blurred-nature-backdrop, lifestyle`
- **B2B-87** — Asymmetrical Gallery Matrix (Var) *(same as EDT-04)* · `asymmetrical-gallery, multi-scale-cards, luxury-lifestyle, retreat`
- **B2B-88** — Vertical Index Property Switcher (Var) *(same as EDT-05)* · `vertical-index-switcher, property-showcase-frame, architectural-bento, clean`
- **B2B-89** — Property Recommendation Deck Split (Var) *(same as EDT-06)* · `recommendation-deck, landscape-property-cards, symmetrical-alignment, travel`
- **B2B-90** — Immersive Dark Interior Hero (Var) *(same as HERO-16)* · `dark-interior-hero, brutalist-text-overlay, booking-scheduler-baseline, luxury`
- **B2B-91** — Close-Up Culinary Feature Block · `split-media-layout, culinary-closeup, gourmet-branding, clean-corporate`
- **B2B-92** — Deep Foggy-Forest Closure Banner · `foggy-forest-canvas, panoramic-misty-valley, capsule-conversion-cta, closure`
- **B2B-93** — Editorial Property Description Stack (Var) *(same as EDT-07)* · `split-header-matrix, asymmetrical-gallery-slider, two-column-copy-block, travel`
- **B2B-94** — Multi-Tabbed Category Amenity Grid (Var) *(same as EDT-08)* · `category-filter-bar, amenities-grid, symmetrical-alignment, b2b-corporate`
- **B2B-95** — Editorial Museum Exhibition Banner (Var) *(same as EDT-09)* · `brutalist-text-marquee, overlapping-canvases, vertical-accordion-grid, history`
- **B2B-96** — Fine-Art Chronological Flagship Hero (Var) *(same as EDT-10)* · `fine-art-hero, cursive-typography-overlay, overlapping-media-cards, alignment`
- **B2B-97** — Asymmetrical Property Experience Grid (Var) *(same as EDT-11)* · `asymmetrical-gallery-matrix, multi-scale-cards, luxury-lifestyle, onboarding`
- **B2B-98** — Wireframe Directory Matrix Footer (Var) *(same as EDT-12)* · `wireline-grid-dividers, minimal-directory, brutalist-text-marquee, sub-footer`
- **B2B-99** — Milestone Checklist Accordion Panel (Var) *(same as EDT-13)* · `milestone-checklist, horizontal-accordion-stack, overlapping-badge, travel`
- **B2B-100** — Advanced Booking Scheduler Stage (Var) *(same as EDT-14)* · `booking-scheduler-stage, step-progression-baseline, horizontal-split-pane, checkout`
- **B2B-101** — Minimal Balanced Text Statement Block (Var) *(same as EDT-15)* · `capabilities-statement, copper-accent-type, two-column-copy-block, clean`
- **B2B-102** — Advanced Booking Scheduler Stage (Var 2) *(same as EDT-14)* · `booking-scheduler-stage, step-progression-baseline, bento-cards-stack, fintech`
- **B2B-103** — Minimalist Split-Pane Core Metrics Row · `metrics-panel-row, copper-accent-type, symmetrical-alignment, social-proof`
- **B2B-104** — Dual-Month Interactive Booking Calendar · `vertical-index-switcher, property-showcase-frame, architectural-bento, clean`
- **B2B-105** — Asymmetrical Info-Card Gallery Matrix · `asymmetrical-gallery-matrix, multi-scale-cards, lifestyle-photography, clean`
- **B2B-106** — Deep Misty-Forest Directory Footer · `misty-forest-footer, panoramic-valley-backdrop, directory-link-grid, utility`
- **B2B-107** — Full-Width Centered FAQ Accordion · `accordion-stack-faq, horizontal-rows, clean-alignment, travel-conversion`
- **B2B-108** — Minimal Product Landing Hero (NEURA) · `3d-hardware-render, smart-ring-asset, watermark-backdrop, fintech-metric`
- **B2B-109** — Macro Multi-Scale Hardware Bento Matrix · `division-grid, pastel-cards, 3d-geometric-objects, staggered-alignment`
- **B2B-110** — Technical Cross-Section Dashboard Block · `cross-section-dashboard, floating-metric-tags, smart-ring-specs, data`
- **B2B-111** — 3D Exploded-View Component Assembly Hero · `exploded-view-assembly, 3d-component-cascade, hardware-blueprint, hero`

### Full section bank dataset (194 rows, raw CSV)

The complete, un-summarized bank. Columns: `Section ID, Category Name, Section Style Name, Description & Layout Hierarchy, Background Elements, Typography & Spacing Specs, Motion & Animation Mechanics, Helpful Tags & Comments, Sample Sections / Use Cases`. Kept as raw CSV (rather than a reformatted table) because some rows contain unquoted commas that misalign strict column-splitting — grep this block by ID, tag, or use-case word rather than parsing it top to bottom.

```csv
Section ID,Category Name,Section Style Name,Description & Layout Hierarchy,Background Elements,Typography & Spacing Specs,Motion & Animation Mechanics,Helpful Tags & Comments,Sample Sections / Use Cases
HERO-01,Hero Sections,Aurora Glow Floating App Hero,Centered text stack dropping into an overflowing web application browser mockup frame.,"Radial gradient blend of lavender `#DCD6FF`, violet `#E6E2FF`, and white. Concentrated color density.",Main title 64px extra-bold line-height 1.15. Sub-headline 16px slate max-width 680px. CTA button group gap 16px.,Ambient glow mesh cycles scale/rotation over 20s. Application browser mockup panel floats vertically 8px over 6s loop.,"hero-section, aurora-glow, saas-mockup, centered-hero",SaaS Main Landing Page Heroes, core digital product overviews.
HERO-02,Hero Sections,Isomorphic Tech Flow Blueprint Hero,Technical SaaS landing hero displaying automation logic streams over an engineering blueprint layer.,Clean stark white canvas sheet overlaid with a faint blue isometric micro-dot grid pattern `#E2E8F0`.,Main title H1 text 60px technical sans-serif. Blue phrase tracking highlight layer `#2563EB`. Input placeholder text 15px.,Logic schematic dashed layout paths execute continuous automated SVG dash-offset texturing flow animations.,"isometric-hero, tech-blueprint, saas-landing, workflow-visualization",AI tech landing heroes, automation platform product walk-through overviews.
HERO-03,Hero Sections,Radiant Gaming Hub Platform Hero,Modern gaming landing hero built around a central geometric network connection map and warm peach gradients.,Radial gradient mesh moving peach coral `#FF9F7D` outer parameters into bright white core folds.,Headline text 56px bold tracking. Inline brand circles diameter 32px embedded inside rows.,Concentric logic pipeline paths illuminate neon pulses sequentially outward from center node keys to outer hexagons.,"gaming-hero, glowing-gradient, integrated-icons, community-hub",Web3/Gaming dashboard landing pages, community network hubs.
HERO-04,Hero Sections,Web3 Neo-Glow Metrics Hero,Advanced infrastructure landing hero stacking a search input engine above an analytics dashboard bento.,Light gray sheet canvas `#F3F4F6` layered with infinite technical engineering line grid arrays.,Core title text 54px, email input input widget width 480px. Dashboard internal numbers 28px.,Dashboard trend lines execute automated SVG path stroke stroke-dasharray paint animation sweeps on load visibility.,"neo-grid, bento-metrics, input-hero, web3-tech",Web3 main hero dashboards, technical protocol network analytics platforms.
HERO-05,Hero Sections,Dark Cinematic Typography Hero,Dark atmospheric creative agency hero layering giant center title overlays over absolute corner text lists.,Deep black canvas hosting center portrait artwork scene (cloaked red figure) with blurred texture washes.,Center uppercase display headline text 88px bold. Corner category text blocks inside brackets.,Background cinematic graphic art panel executes scroll parallax speed interpolation while title entry scales upward.,"cinematic-hero, dark-mode, editorial-typography, high-contrast",Creative agency main heroes, premium fashion landings, brand portfolios.
HERO-06,Hero Sections,Organic Clean-Tech Horizon Hero,Inset curved display card hero mapping large environment imagery underneath user bar layers.,Stark white outer canvas frame enclosing an inner display card module built with deep rounded bounds 32px.,Inner headline text 62px bold white text. Paragraph description width constraint 520px. CTA button group row gap 12px.,Background airliner flight photo layer shifts lighting channels via automated gradient map lighting sweep loops.,"clean-tech, curved-frame, environmental-tech, centered-stack",Sustainable enterprise hero landing pages, modern transit corporation interfaces.
HERO-07,Hero Sections,Fan-Out Tilted Graphic Card Hero,High-impact dark studio hero section anchoring a progress fanned-out deck of tilted image cards past the fold.,Pristine uniform matte black sheet canvas framework #0Black bounds.,Main display headline 64px, line-height 1.1. Top capsule navigation bar holds mint green CTA button.,Hovering card deck smoothly reduces individual rotation angles toward 0 while dynamically increasing row layout spacing.,"fanned-cards, tilted-ui, centered-typography, dark-mode-hero",Principal landing heroes for creative digital studios, design portfolios, or tech agency indices.
HERO-08,Hero Sections,Editorial Column Vertical Splitting,Sleek high-key learning hero pathway distributing entry streams across tall, vertically elongated rounded columns.,Solid pristine white sheet layout canvas layer #FFFFFF.,Left display text 64px bold black sans-serif. Inset input field with green action tile.,Hovering vertical column strips smoothly expands width flex-grow: 3, cross-fading vertical text keys into horizontal layout.,"vertical-accordion-grid, editorial-columns, input-hero, staggered-typography",Main educational academy heroes, e-commerce division matrices, platform entry portals.
HERO-09,Hero Sections,Ultra-Clean Product Showcase Hero,High-end editorial showcase layout featuring large central product graphic breaking bottom borders.,Clean off-white canvas sheet #F6F6F6 utilizing an inset border card layer framing configuration.,Main display text 56px-68px sans-serif italic variants. Left block description 15px.,Scroll-driven parallax translations shift the central dark hardware puck icon faster than page canvas rules.,"editorial-layout, asymmetrical, product-showcase, minimalist-tech",E-commerce hardware landing pages, premium consumer tech heroes.
HERO-10,Hero Sections,Asymmetrical Organic Split Hero,Creative landing hero splitting a blue vector line scene from a white text layout via curved wave borders.,Split canvas base: upper 60% electric blue #2B66FF, lower 40% white page sheet canvas matrix.,Blue field display title text 56px white text layers. White field data headers 20px bold.,Illustration character paths trace out vector design rules on load visibility via automated SVG dash-offset sweep loops.,"organic-split, color-block-wave, vector-illustration, editorial-hero",Corporate career main pages, creative agency landing heroes, brand index folds.
HERO-11,Hero Sections,Handheld Device Mockup Hero,Elite landing hero centering a handheld smartphone mockup tracking live video over a blue-sky radial gradient wash.,Soft, light-blue wash gradient backdrop field canvas layer. Mockup smartphone frame absolute.,Main display layout 58px white text layers. Description copy regular regular tracking rules.,Move gestures or page scroll sequences trigger independent horizontal and vertical translation float offsets across handheld.,"handheld-device-mockup, saas-conversion-hero, radial-gradient-wash, medical",Principal landing pages for medical applications, health-tech protocol software.
HERO-12,Hero Sections,Flagship SaaS Platform Blue-Sky Hero,Technology landing hero centering an umbrella arch mockup window over a blue-sky cloud layer base.,High-fidelity photographic canvas displaying bright white cumulus cloud banks fading into blue sky washes.,Main headline 56px, dual-colored linear text gradient fill layer 'Create CustomGPTs'.,On initial viewport visibility, third-party icons animate sequentially outward from apex node down left and right paths.,"blue-sky-hero, integration-umbrella-arch, concentric-logo-bridge, saas",Principal landing heroes for cloud automation tools, software integration hubs.
HERO-13,Hero Sections,Luxury Balanced Showcase Hero,Premium watch landing hero layering a vertical brand marquee behind a giant 3D mechanics skeleton sports watch asset.,Full-bleed clean canvas base layer showing ultra-soft periwinkle radial gradient wash margins.,Main headline 58px bold, vertical script typography design layer 'Hublot' text.,Central 3D skeleton watch asset executes a continuous slow-duration automated rotation animation loop on center axes.,"luxury-showcase, 3d-hardware-render, watermark-sidebar, premium-landing",Flagship luxury product heroes, premium consumer tech landing overviews, catalogs.
HERO-14,Hero Sections,Brutalist Overlapping Lookbook Hero,High-impact brutalist fashion landing hero section that layers massive canvas-filling display typography behind portrait photography frames.,Solid matte light gray background field canvas layer covered with vertical alignment wirelines.,Brutalist background text 110px condensed. Central photo frame vertical portrait.,Cursor tracking coordinates trigger gentle opposite horizontal translation float offsets across background text blocks.,"brutalist-grid, overlapping-media, cursive-typography-overlay, brutalist",Streetwear fashion catalog lookbooks, creative studio collection launches, lookbooks.
HERO-15,Hero Sections,Full-Bleed Nature Retreat Hero,Immersive eco-tourism hero section tracking an open navigation header above a modern A-frame glass cottage lake scene.,Full-bleed photographic background showcasing a luxury modern A-frame glass cottage along a lake reflect pool.,Main display headline 64px white sans-serif text. Description copy regular weight text layouts.,Lake reflection water area incorporates a subtle fluid simulation loop to replicate soft active water ripples continuously.,"full-bleed-nature, luxury-retreat, forest-cabin, centered-conversion",Flagship heroes for boutique hotels, nature retreats, architectural experience landings.
HERO-16,Hero Sections,Immersive Dark Interior Hero,Luxury hospitality hero overlaying a brutalist fireplace text headline onto a full-bleed dark concrete living lounge scene.,Full-bleed photographic background displaying an industrial dark concrete interior lounge fireplace setup.,Fireplace text headline 88px uppercase tracking. Booking scheduler text layers regular weight.,Fireplace mantle area incorporates a highly realistic particle lighting mesh simulation to replicate live flickering flame.,"dark-interior-hero, brutalist-text-overlay, booking-scheduler-baseline, luxury",Principal landing heroes for luxury boutique hotels, luxury villa bookings.
SEC-01,2nd / Feature Sections,Minimalist Split-Header Blog Grid,3-column content grid, asymmetrical split header layout using flex space-between.,Solid white #FFFFFF or off-white #F9F9F9. No layout lines or gradients.,Headline 48px-56px bold, body text 16px. Card title 24px bold, 1px separation lines #EAEAEA.,Card image scales up scale(1.04) on hover over 0.4s clip bound. Arrow icon slides up-right 4px.,"minimalist, split-header, card-grid, article-hub",Blog index rolls, resource centers, case study lists.
SEC-02,2nd / Feature Sections,Tabbed Feature Module Block,Bold 2-column feature walkthrough block using an upper fractional tab selection grid line layout.,Solid vivid periwinkle brand purple canvas sheet layer #8A70FF. Completely flat color.,Fractional column navigation tabs split 1/5 width rows. H3 bold header text 40px white text.,Tab header triggers prompt immediate 0.3s opacity swap crossfade and slight horizontal slide layout shift of mockup assets.,"tabbed-interface, solid-background, feature-showcase, two-column-split",Feature walkthrough modules, interactive product value blocks.
SEC-03,2nd / Feature Sections,Minimalist Balanced Feature Grid,Symmetrical 3-column grid layout pairing isolated top-left headlines with light square icon boxes.,Clean stark white utility canvas sheet background framework #FFFFFF.,Left title display text 42px bold. Inset light gray icon boxes #F1F1F4 rounded 16px.,Hover actions over boxes trigger custom spring translation elasticity on the inner purple vector icon marks.,"services-grid, minimal-icon-box, clean-alignment, symmetrical",Service overviews, corporate core pillar highlights, value propositions.
SEC-04,2nd / Feature Sections,Clean-Tech Asymmetrical Data Grid,3-column clean-tech data feature grid utilizing immersive closeups and data visualization matrices.,Solid bright light-gray canvas wrapper #F4F4F4. Tech modules matte dark-green #041C06.,Section display title 44px. Stat metrics text 54px bright white.,Scroll viewport intersection triggers sequential dot matrix scale loop ripple animation row-by-row over 0.05s steps.,"clean-tech, data-visualization, asymmetrical-grid, bento-metrics",Industrial tech feature overviews, sustainability reports, impact statistics.
SEC-05,2nd / Feature Sections,Split-Pane Hybrid Feature Column,Editorial 2-column split feature row, vertical text flex path left, large rounded media block right.,Solid deep organic dark-green field canvas sheet background layers #031805.,Headline display text 48px pure white. Separation row lines dark-gray #132E16.,Hover actions across horizontal listings swap font weights instantly and slide light green color overlays behind indices.,"split-feature, interactive-list, clean-tech, media-showcase",Product capability breakdowns, environmental process overviews, industrial use cases.
SEC-06,2nd / Feature Sections,Fluid Organic Field Feature Row,4-column service card row overlaying a wide full-bleed nature environment photography layer.,Photographic background of rolling green agricultural hills blending into solid green baseline gradient.,Top row split headline text 40px bold. Floating card modules white #FFFFFF, rounded 20px.,Hovering cards triggers asymmetrical vertical translation lift translateY(-8px) and smooth inner graphic image scaling.,"organic-background, white-bento-cards, clean-tech, nature-tech",Core company values, investment pillars, ecosystem structural models.
SEC-07,2nd / Feature Sections,Corporate Creative Portfolio Banner,Asymmetrical text row stacked directly above a tight multi-pane team lifestyle photo marquee canvas.,Clean flat white upper background transitioning into tinted photography layers via feathered blur masks.,Left description block text 22px medium-light gray text. Inset white call badge text 16px.,Hover actions over photo cells smoothly expand their flex layout weight proportions flex: 2 while shrinking neighbors.,"editorial-grid, agency-portfolio, mosaic-layout, asymmetrical-text",Agency about-pages, creative agency team showcase blocks, culture rolls.
SEC-08,2nd / Feature Sections,Clean-Tech Asymmetrical Accordion Stack,Clean-tech FAQ variation framing left display titles above stacked right accordion channel blocks.,Clean uniform high-key white layout field canvas background paneling #F5F5F5.,Display headline text 52px USA bold. Left wide capsule action button background lime-green.,Accordion expansion triggers smooth max-height interpolation layout transitions while right plus icons cross-rotate.,"split-faq, clean-tech-ui, asymmetrical-accordion, modern-minimalist",Clean-tech corporate FAQs, industrial resource links documentation.
SEC-09,2nd / Feature Sections,Glassmorphic Column Hub,5-column value dashboard distributing frosted glass panel wrappers over intense violet light spots.,Dark texture mesh gradient transitioning blue-violet variants into periwinkle light spotwells.,Header text title 52px bold/thin typography hierarchy tracking. Glass card wrappers 20px.,Glass feature modules shift backdrop opacity filters and execute vertical translation lift translateY(-12px) on hover.,"glassmorphism, glowing-gradient, five-column-grid, feature-hub",Value propositions, strategic capability sheets, "Why Choose Us" sections.
SEC-10,2nd / Feature Sections,Asymmetrical Interactive Use-Case Split,Editorial B2B feature layout split anchoring a vertical accordion panel left and multi-layered visual cards right.,Solid crisp white layout field canvas #FFFFFF. Accordion frames off-white #F5F5F5.,Section title headline 38px bold. Accordion collapsed tiers row gap metrics 16px.,Toggling separate use-case menu rows smoothly executes height text crossfades while instantly swapping right visual cards.,"split-use-case, interactive-accordion, layered-mockups, b2b-features",Industry vertical deep-dives, custom product use-case overviews, target persona walkthroughs.
SEC-11,2nd / Feature Sections,Pastel Aurora Glass Feature Deck,Symmetrical 4-column feature deck row distributing vertical bento cards filled with multi-colored aurora spots.,Pristine uniform white canvas backdrop layer #FFFFFF.,Card headings 22px bold black sans-serif. Inset circular glassmorphic icons well radius 24px.,Hovering over cards prompts underlying color mesh gradients to shift coordinate tracking parameters smoothly over easy curves.,"pastel-aurora, glassmorphism-icons, bento-features, symmetrical-deck",Platform core capability listings, specialized tool features, technical value propositions.
SEC-12,2nd / Feature Sections,Inset Workspace Dashboard Split,Editorial 2-column layout split coordinating structured vertical milestone checklists with an extra-large software mockup.,Clean white sheet layout canvas backdrop layer #FFFFFF. Mockup dashboard frame light gray.,Primary headline 42px bold, text marker highlight box 'Accelerate Growth'.,Viewport intersection visibility prompts inner concentric circular pipeline charts to dynamically paint via path stroke sweep.,"dashboard-mockup, text-marker-highlight, checklist-timeline, editorial-feature-split",Operational capabilities breakdowns, CRM product values overviews, enterprise value walkthroughs.
PRC-01,Pricing Sections,High-Contrast Bento Pricing Grid,Structured 3-column subscription grid where center priority plan uses an inverted color layer.,Pristine uniform light gray canvas sheet layer #F8F9FA. Standard white card backings #FFFFFF.,Header display text 48px, pricing numerical tier strings 52px bold.,Hover actions over cards prompt container elevation change via drop shadow manipulation box-shadow alterations.,"pricing-grid, bento-style, featured-card, saas-conversion",Software Pricing Tiers, Membership Plans modules.
PRC-02,Pricing Sections,Dark Neo-Glow Tiered Pricing Matrix,Premium dark subscription module highlighting the center bento box using multi-colored neon border glow rings.,Solid matte deep charcoal black background field canvas sheets #09090B.,Plan title text 48px, price text layers 54px white. Center card holds crown icon marks.,Premium card border layers execute continuous CSS linear gradient angle rotation sweeps to create moving rainbow outlines.,"pricing-grid, neon-border-glow, dark-mode, bento-pricing",Enterprise SaaS pricing grids, tiered subscription plans, service upgrades blocks.
PRC-03,Pricing Sections,Bi-Color High-Contrast Pricing Matrix,Staggered 2-row subscription column stack inverting the primary plan container using a bright mint backing.,Uniform matte dark charcoal background field canvas sheets #111111. Standout plan block mint #4FE3B2.,Title header display text 54px uppercase. Tier pricing tier values 48px bold.,Hover entries across pricing cards execute drop shadow changes box-shadow alterations and minor scale expansion.,"pricing-matrix, inverted-color-block, mint-green-ui, vertical-stack-pricing",Specialized service tier options, corporate project package sheets.
PRC-04,Pricing Sections,High-Contrast Bento Subscription Matrix,Structured, minimal 3-column pricing grid utilizing a prominent centered "Bento-Box" design layout where the highest-value plan physically pops out.,Pristine uniform light gray layout field canvas background paneling #F9F9FA. White card backings #FFFFFF.,Plan title text 44px bold. Center professional plan card features top absolute capsule badge.,Hover actions over individual pricing bento cards prompt a subtle container elevation change via drop shadow manipulation.,"pricing-grid, bento-pricing-matrix, color-inversion-block, centered-conversion",Tiered subscription plans, software membership plans blocks, service upgrades matrices.
FAQ-01,FAQs,Full-Width Centered FAQ Accordion Stack,Constrained central layout list wrapper handling a vertical row stack of FAQ accordion channels.,Uniform minimal clean flat white surface canvas paneling templates.,Section headline text 48px, question row entries 18px-20px bold.,Toggling row accordion triggers grid-template-rows 0fr to 1fr slide expansion height shift. Chevron icon performs 180 flip.,"accordion-stack, faq-section, interactive-list, clean-ui",FAQ panels, core product feature specifications documentation blocks.
FAQ-02,FAQs,Split-Layout Minimalist FAQ Grid,Asymmetrical 2-column FAQ variation, headline pinned left column, independent white cards right.,Solid off-white layout surface backdrop canvas #F8F9FA. Card canvas blocks solid white #FFFFFF.,Left title text 52px splitting two short rows. Right card wrappers rounded 12px.,Selecting closed cards smoothly expands height boundaries to reveal responses while plus glyphs shift into close crosses.,"split-accordion, two-column-faq, bento-list, modern-minimalist",Asymmetrical FAQ arrays, technical service details matrices.
FAQ-03,FAQs,Editorial Grid Accordion Showcase,Asymmetrical 2-column FAQ grid locking high-fidelity neon media containers left and dark accordion bars right.,Solid matte deep black sheet layout layer background layers #080808. Accordion frames dark-gray #141414.,Uppercase display title text 56px bold white text layers. Accordion option title text 18px.,Accordion row toggle events trigger height layout shifts from 0 to 1fr via data max-height interpolation curves.,"split-faq-grid, studio-media-frame, dark-mode-accordion, clean-alignment",Modern agency FAQs, hardware overview specification sheets.
FAQ-04,FAQs,Glassmorphic Document Accordion Stack,Clean document directory listing stacking elongated frosted glass accordion channels over giant background text.,Soft light sky-blue wash gradient background sheets dropping down behind foreground row frameworks.,Background display title text layout 92px bold. Glass accordion container radius 14px.,Activating individual accordion channel items slides open underlying copy strings while rotating right action cross glyphs.,"glassmorphism, typography-backdrop, sky-gradient, accordion-list",B2B program FAQs, corporate documentation indices.
FAQ-05,FAQs,Layered Progressive FAQ Dashboard,Elite deep-mode informational section nesting an upper capsule conversion card above a vertical accordion stack.,Solid pristine off-white canvas layout background layer #FFFFFF. Accordion frames light gray.,Form capsule headline text 26px white text. Accordion question row titles text 18px.,Toggling an accordion row triggers smooth max-height interpolation layout transitions while right chevron icons cross-rotate.,"faq-dashboard, capsule-conversion-card, interactive-accordion-stack, step",Specialized software product use-case overviews, regulatory phase checklists, walkthroughs.
FAQ-06,FAQs,Wireframe Matrix Accordion FAQ,Structured full-width FAQ interface designed to manage text accordion rows over an engineering coordinate backdrop.,Solid deep charcoal black background field canvas layer overlaid with an infinite high-precision layout matrix.,Section main heading text 44px bold. Accordion question row titles text 18px regular tracking.,Accordion expansion row toggle events trigger height layout shifts from 0 to 1fr via smooth max-height interpolation.,"accordion-matrix-faq, wireline-grid-dividers, technical-coordinate, clean",FAQ panels, core product feature specifications documentation blocks, tutorials.
FT-01,Footers,Structured Clean-Tech Subscription Footer,Deep clean-tech conversion directory footer layering an upper subscription form over a giant text watermark.,Solid deep dark-green canvas background field #031605. Bottom layer hosts dark watermark typography.,Newsletter capture title text 22px. Link categories bold white text 16px.,Lime green social circle button interaction triggers soft radial green drop shadow changes box-shadow alterations.,"clean-tech-footer, newsletter-capture, directory-columns, giant-watermark",Corporate clean-tech base footers, energy sector directory closures.
FT-02,Footers,Luminous Mesh Capsule Footer,Long rounded capsule container footer housing centered action arrays over large brand background text watermarks.,Deep dark slate page canvas hosting an inner capsule box filled with fire coral to electric cyan neon mesh.,Capsule frame corner metrics 32px border-radius. Title text 44px white text layers.,Inner neon gradient mesh fields execute slow-duration transformation coordinate drift loops to simulate moving gas light wells.,"capsule-footer, neon-mesh, brand-watermark, centered-conversion",Closure conversion landing fields, premium SaaS corporate footers.
FT-03,Footers,Minimal Gradient Baseline Utility Footer,Slate-blue gradient wash footer spreading link column paths left, balancing brand scripts right.,Dark slate-blue gradient wash canvas layer moving light slate tops into high-density navy footings.,Upper motto title text 28px bold white text. Directory column headers text 16px.,Right-aligned primary blue contact capsule button executes continuous background radial pulse light cycle loops.,"minimal-footer, gradient-wash, directory-columns, clean-alignment",Baseline corporate footers, utility directory layouts.
FT-04,Footers,Low-Contrast Minimalist Contact Closure,Low-contrast directory footer layout centering a giant email headline below an absolute full-width color bleed.,Solid matte deep charcoal black layout backdrop canvas background layers. Fluid turquoise mesh wash.,Topbar utility navigation links spacing 24px. Directory column link headers bold white text 16px.,Directory link anchors execute immediate font color weight conversion from dark gray to solid white text lines on hover.,"minimalist-footer-closure, neon-gradient-bleed, email-capture-form, footer",Baseline corporate footers, main closing conversion modules, legal directories.
FT-05,Footers,Technical Coordinates Footer Closure,Deep low-contrast directory footer layout focusing an email capture form over an engineering line matrix.,Dark slate-blue to charcoal wash background field overlaid with an infinite high-precision layout matrix.,Main headline 42px miniature white text layers. Baseline directory social icons row gap 16px.,Background technical line wirelines execute slow, ongoing automated keyframe opacity shimmer loop animation patterns.,"technical-coordinate-footer, email-capture-form, minimal-directory, dark-mode-closure",Baseline corporate footers, agency conversion closure folds, contact directory layouts.
FT-06,Footers,Wide Gradient Tech Directory Footer,Clean corporate directory footer closure layout focusing an email capture row and a large left-heavy brand logo mark.,Deep dark slate charcoal page canvas field. Low-contrast script typography design watermark 'VOXA'.,Upper row capture headline text 42px white. Directory menu link filters spacing 24px.,Directory menu link anchors execute immediate font color weight conversion from dark gray to solid white text lines on hover.,"minimalist-footer, giant-watermark-base, email-capture-form, horizontal",Flagship corporate footers, closure conversion landing fields, contact directory panels.
TEST-01,Testimonials,Framed Carousel Testimonial Slider,Social proof slider track centering an active portrait photo block between inward angled text quote cards.,Solid rich matte black canvas background backdrop template lines #000000.,Section header title text 42px. Portrait asset module borders rounded 20px.,Carousel lane stage transition shuffles card matrix horizontally while altering Y-axis rotation filters.,"testimonial-slider, dark-mode, hanging-quotes, asymmetrical-carousel",Customer reviews hubs, case study carousels, social proof grids.
TEST-02,Testimonials,Perspective Video Testimonial Slider,3-column review carousel angling left and right text cards inward toward a flat center portrait video card.,Solid deep charcoal felt canvas background backdrop template lines #121212. Center frame rounded 20px.,Category tag label text 14px green. Main header title text 60px uppercase.,Carousel navigation actions translate cards horizontally while altering Y-axis rotation degrees to flatten incoming items.,"perspective-slider, 3d-carousel, video-testimonials, dark-mode-review",Social proof video hubs, customer success stories, interactive testimonial walls.
TEST-03,Testimonials,Supply Chain Bento Testimonial Grid,Structured clean corporate 4-pane bento-box testimonial system mixing bold statement cards with reviews.,Clean uniform off-white layout canvas sheet layer #F3F7FA.,Card display text 28px bold white. Center profile review photo fields inside light-blue panels.,Bento container blocks prompt subtle elevation changes via drop shadow manipulation and an active scale shift on mouse hover triggers.,"bento-testimonials, dark-teal-gradient, profile-portraits, clean-corporate",Client feedback dashboards, social proof bento matrices, product success stories.
TEST-04,Testimonials,Asymmetrical Carousel Review Wall,Immersive light-mode social proof review module distributing four vertical white cards across a wide horizontal track.,Full-bleed background canvas displaying an ultra-soft radial periwinkle gradient wash.,Card display text 16px regular. Client profile signature text bold black sans-serif text.,Slotted interaction triggers translate the carousel track on X-axis while lifting container wrapper height parameters.,"testimonial-carousel, high-key-social-proof, clean-corporate, slider",Customer reviews hubs, case study carousels, social proof grids.
TEST-05,Testimonials,Inverted Contrast Review Board,Elite dark-mode testimonial matrix balancing three vertical bento cards left with a right text marker highlight block.,Solid deep charcoal black surface canvas backdrop template lines #111112. Content cards dark gray #161618.,Main headline 44px bold white, green marker highlight box text 16px bold tracking.,Horizontal carousel stage swipe controls translate active review cards along X-axis while smoothly expanding shadows.,"testimonial-board-matrix, inverted-color-split, text-marker-highlight, dark",Customer reviews hubs, case study walls, platform social proof carousels.
TEST-06,Testimonials,Symmetrical Social Proof Slider,High-key customer review carousel distributing white options cards above centered circular navigation buttons.,Solid pristine off-white sheet layout canvas layer #FFFFFF. Card wrappers box shadow metrics.,Section main title 42px extra bold. Testimonial copy text regularRegular font weight tracking.,Slotted interaction triggers translate the carousel track on X-axis while lifting container wrapper height parameters.,"testimonial-slider, high-key-social-proof, clean-corporate, symmetrical-carousel",Customer reviews hubs, case study carousels, social proof grids.
CON-01,Contact Sections,Atmospheric Application Contact Form,Ethereal registration hero centering a glassmorphic input panel over giant overlapping background display titles.,Photographic canvas displaying bright white cumulus cloud banks fading upwards into periwinkle sky washes.,Background title text layout 88px bold navy text. Inset input fields inside 2x2 grid.,Mouse click actions into input fields toggle border stroke properties into a glowing electric-blue active state.,"contact-hero, glass-form, sky-gradient, overlapping-typography",Main agency contact forms, partner request screens, registration hubs.
CON-02,Contact Sections,Brutalist Typographic Form Overlap,High-impact brutalist portal section stacking a floating matte black form card container over canvas-filling background typography.,Off-white sheet layout layer background layers #F9F9F9 split down center via 1px vertical wirelines.,Brutalist background text 110px condensed. Floating form container matte black #111111.,Page scroll tracking metrics scissor the background text blocks horizontally in opposite directions behind the fixed card.,"brutalist-grid, overlapping-form, giant-typography, high-contrast-brutalist",Conversion funnel endfolds, creative studio contact portals, registration blocks.
CON-03,Contact Sections,Brutalist Capture Form Grid Matrix,High-impact brutalist split block balancing bulleted benefits lists left with a towering yellow-framed capture form right.,Solid matted deep charcoal black background field canvas layer #0B0B0B. Capture form card panel.,Left title heading text 38px neon yellow. Form card main title text 42px uppercase yellow.,Mouse click entries into individual form input field lines toggle border stroke properties into neon-yellow active states.,"brutalist-form-matrix, neon-yellow-accents, benefits-checklist, dark-mode",Main closing conversion modules, enterprise registration sign-on gates, lead captures.
CON-04,Contact Sections,High-Contrast Split-Pane Contact Closure,Corporate conversion closure footer balancing a solid neon orange link directory left with a dark capture form right.,Split canvas base: left 50% neon orange field canvas, right 50% solid deep black page canvas sheet.,Orange pane headline text 60px extra bold white. Right input fields dark rounded box blocks.,Hovering text anchors inside the orange pane dynamically expands a bold white baseline row underline element on mouse entry.,"split-color-closure, neon-orange-pane, form-input-matrix, directory-menu",Main company contact closures, agency lead capture endfolds, registration form gate panels.
CTA-01,Call-to-Action (CTA) Sections,Scattered Thumbnail Call-to-Action Grid,High-contrast closure fold floating a matrix of vibrant multimedia illustration frames over centered text folds.,Deep charcoal black texture canvas field background textures #111111 with vertical engineering lines.,Title header display text 56px bold uppercase text. Mint-green capsule text 16px.,Cursor movement across the workspace coordinates triggers mouse-responsive parallax translation offsets.,"scattered-grid, parallax-thumbnails, centered-cta, high-contrast-dark",Bottom-of-page CTA funnels, agency conversion folds, creator studio landings.
CTA-02,Call-to-Action (CTA) Sections,Inverted Contrast Dual-Pane Block,Elite social proof section balancing a giant center text quote right with an oversized diagonal-cut portrait card left.,Solid vibrant golden-yellow field canvas, transitioning right into white radial gradient wash mesh spots.,Right headline display text 42px bold. Context sub-link headers regular weight tracking.,Hovering individual anchors inside right pane dynamically expands a bold white baseline row underline element on mouse entry.,"diagonal-cut-portrait, inverted-color-split, large-scale-quote, b2b",High-value client feedback dashboards, bottom-of-island conversion fields.
CTA-03,Call-to-Action (CTA) Sections,Capsule Closure Conversion Footer,Deep corporate directory footer closure layout centering an upper capsule conversion card over a 3-column index.,Clean white upper canvas transitioning down into a solid deep slate navy baseline footing fold track.,Card title text 36px white. Directory column headers bold white text 16px.,Directory link selections execute immediate font color weight conversion from dark gray to solid white text lines on hover.,"capsule-conversion-card, geometric-glass-backdrop, directory-link-grid, sub",Primary main closing conversion modules, enterprise platform baseline footers, legal directories.
CTA-04,Call-to-Action (CTA) Sections,Giant Chroma Wordmark Transition Banner,Ultra-minimalist branding transition banner designing giant gradient text block logos beside vertical resource link lists.,Solid deep dark slate charcoal horizontal strip ribbon background field. Diamond card icon mark.,Ribbon headline text 42px white. Sub-footer legal utility anchors spacing 16px.,Gradient text block logo performs an automated horizontal entry slide translation onto the stage track on load visibility.,"ribbon-banner, gradient-typography-logo, brutalist-text-cta, sub-footer",Bottom-of-page closure ribbons, agency portfolio base rows, creative transitions.
MIN-01,Minimalist Design Tiers,Asymmetrical Floating Step Matrix,Editorial process section layering giant background typography behind staggered matte black feature cards.,Solid off-white canvas layout background #F9F9F9. Background text 120px light gray.,Top index code enclosed in brackets '[1]'. Swatch containers rounded 12px with high padding tracking.,Step cards translate vertically at different ratios over static background text strings on scroll view.,"staggered-bento, giant-typography, gradient-swatches, process-flow",Core methodology overviews, operational roadmap folds, step-by-step corporate execution guides.
MIN-02,Minimalist Design Tiers,Asymmetrical Portrait & Capability Split,Editorial clean agency feature section offsetting stacked portrait mosaics left with a 4-part value listing matrix right,Solid pristine off-white canvas backdrop layer #FFFFFF. Value block heading text layers 20px.,Left mosaic headline text 42px condensed black. Integrated blue icon well radius 24px.,Value card hover coordinates translate text metadata rows upwards while executing a subtle icon well spring lift translation.,"split-capability-layout, mosaic-portrait-cards, clean-alignment, b2b-feat",Main agency about-page values, core corporate pillars summaries, capabilities sheets.
MIN-03,Minimalist Design Tiers,Minimal Category Grid Showcase,Staggered lightweight division row distributing pastel-colored square cards under centered category filters.,Solid clean off-white canvas layout backdrop canvas field background sheets #F9F6F2. Pastel panels white frames.,Top main title text 42px navy. Navigation anchor links spacing 20px.,Hover vectors over card modules trigger an asymmetrical vertical translation lift translateY(-8px) and interior photo scale.,"category-grid, pastel-cards, minimalist-photography, staggered-alignment",Educational category overviews, e-commerce division matrices, portfolio classification selectors.
MIN-04,Minimalist Design Tiers,Minimal Balanced Step Walkthrough Block,Clinical 4-column capabilities section balancing an upper process title block with an info-dense vertical step timeline.,Solid clean off-white canvas layout field paneling with zero structural lines or gradients.,Main section heading text 42px bold. Step timeline text titles 20px bold.,Hovering over horizontal step card frames smoothly expands container drop shadow values and executes vertical translation.,"step-walkthrough-grid, minimal-icon-wells, symmetrical-text, clean-alignment",Corporate service overviews, core capabilities walkthrough overviews, checklists.
ORG-01,Organic Field / Clean-Tech Tiers,Alternating Industrial Capability Row,Clinical alternating 2-row grid format balancing corporate value summaries with architectural industrial imagery.,Pristine uniform white layout canvas backdrop canvas field #FFFFFF.,Left green text label 'SOLUTION'. Card headings 32px bold black sans-serif.,Scrolling individual card frames dynamically lifts the container wrapper and expands drop shadows of inner metric tags.,"alternating-grid, b2b-minimalist, warehouse-photography, floating-metrics",Enterprise capability summaries, supply chain value breakdowns, commercial operations portfolios.
ORG-02,Organic Field / Clean-Tech Tiers,Clean Pastel Radial SaaS Hero,Elite airy SaaS hero layout tracking centered high-key display text above a balanced baseline deck of pastel data cards.,Full-bleed clean canvas base layer showing ultra-soft periwinkle radial gradient wash mesh spotlights.,Main headline 58px, bright neon-lime background marker highlight box 'Charge Sales'.,Baseline deck cards execute automated staggered entry animations, sliding upwards into row layout with a smooth easing curve.,"pastel-bento-hero, text-marker-highlight, radial-gradient, saas-dashboard",Principal landing heroes for sales automation platforms, CRM tools, or AI enterprise dashboards.
ORG-03,Organic Field / Clean-Tech Tiers,Milestone Progress Checklist Row,Educational 2-column feature walkthrough coordinating a vertical checklist timeline with a large workspace photo card.,Solid clean off-white canvas layout field paneling #FDFBF7.,Two-row headline 36px bold. Right landscape photo hosts absolute green block out badge layer.,Milestone circle nodes illuminate sequentially downwards along the vertical dashed tracking wireline track on view entry.,"milestone-checklist, dashed-timeline, overlapping-badge, educational-ui",Training value walkthroughs, company core values charts, platform onboarding lists.
ORG-04,Organic Field / Clean-Tech Tiers,Frosted Glass Capsule Botanical Showcase,Organic product feature grid centering three glassmorphic capsules over full-bleed photographic green branch layers.,Clean uniform off-white layout canvas sheet layer #FFFFFF. Botanical branch asset center axis.,Card heading text 20px bold black. Description copy regular regular Regular weight tracking metrics bounds.,Move gestures across coordinates trigger gentle independent keyframe translation float offsets across glassmorphic shapes.,"glassmorphic-capsules, botanical-assets, organic-product-ui, interlocking",Natural product ingredient lists, e-commerce core walkthrough overviews, wellness.
ORG-05,Organic Field / Clean-Tech Tiers,Frosted Glass Capsule Botanical Showcase (Var),Symmetrical wellness platform overview aligning three vertical frosted glass columns over full-bleed panoramic moss fields.,Full-bleed panoramic photographic portrait of rolling green moss-covered agricultural hills.,Upper headline text 42px. Inset circular card container radius 14px.,Viewport card intersection visibility prompts underlying green moss color pixels to dynamically distort under glass panels.,"glassmorphic-capsules, panoramic-nature-field, organic-product-ui, align",Wellness platform value propositions lists, natural product ingredient lists, overviews.
EDT-01,Editorial & Structural Gallery Tiers,Cinematic Dark Strip Ribbon Banner,Ultra-minimalist dark-mode baseline ribbon marquee centering an isolated art frame box inside scrolling typography.,Solid deep charcoal black horizontal strip ribbon background field #111111.,Background condensed gray lettering 110px. Center portrait art frame rounded 12px.,Giant background text executes slow, infinite horizontal marquee crawl on X-axis right-to-left beneath static center box.,"ribbon-banner, infinite-text-marquee, centered-art-frame, dark-mode-transition",Bottom-of-page closure ribbons, portfolio base rows, minimal contact transitions.
EDT-02,Editorial & Structural Gallery Tiers,Alternating Capsule Portfolio Matrix,Minimalist capabilities slider marquee tracking active portrait containers complete with right-anchored arrow badges.,Solid clean off-white canvas layout backdrop canvas field background sheets #FAF8F5.,Card text titles 20px bold. Photo card text check list tags.,Slide controls shift the service track horizontally along X-axis while cross-fading inner photo frames dynamically on click.,"portfolio-gallery-grid, horizontal-carousel, floating-arrow-cta, editorial",Core agency capabilities showcases, creative studio portfolio carousels, categories.
EDT-03,Editorial & Structural Gallery Tiers,Vertical Ribbon Marquee Showcase,Clinical 7-column service grid balancing an active expanded photo card left with towering vertical ribbon marquee strips right.,Solid clean off-white canvas layout backdrop canvas field #F9F9FA. Row grid dividers vertical lines.,Section title heading text 38px bold black text rows. Active card heading text layers 24px.,Hover actions over narrow column strips smoothly expand horizontal layout width proportions while compressing adjacent fields.,"vertical-accordion-grid, editorial-columns, ribbon-marquee, text-symmetrical",Core agency capabilities lists, software portfolio category overviews, portals.
EDT-04,Editorial & Structural Gallery Tiers,Asymmetrical Gallery Matrix,Advanced information-dense amenities block pairing an extra-large text block left with three multi-scale layout cells right.,Pristine uniform off-white layout canvas layer with zero lines or gradients. Multi-scale cards.,Left title headline text 44px bold. Capsule button text layers 16px copper.,Move gestures across coordinates trigger independent horizontal and vertical translation float offsets across image cells.,"asymmetrical-gallery, multi-scale-cards, luxury-lifestyle, retreat",Boutique hotel amenities showcases, asset catalog overviews, experience designs.
EDT-05,Editorial & Structural Gallery Tiers,Vertical Index Property Switcher,Advanced real estate switcher module balancing vertical text list options left with a large property showcase frame right.,Solid clean off-white canvas layout background layer. Showcase frame landscape portrait.,Main title display text 42px uppercase. Property details progress text layers regular weight.,Toggling vertical index text links instantly clears right-hand media pane and fades incoming property photo asset via sweep.,"vertical-index-switcher, property-showcase-frame, architectural-bento, clean",Vacation rental catalogs, real estate asset overviews, directory switchers.
EDT-06,Editorial & Structural Gallery Tiers,Property Recommendation Deck Split,Structured conversion module splitting a giant uppercase headline above a horizontal row of two property cards.,Solid pristine off-white canvas layout background layer. Photo cards full portrait frames.,Section title heading text 44px uppercase. Property details text layers regular font weights.,Hover actions over individual horizontal card containers prompt a subtle container elevation change via drop shadow manipulation.,"recommendation-deck, landscape-property-cards, symmetrical-alignment, travel",Product recommendation sliders, cross-selling real estate blocks, catalogs.
EDT-07,Editorial & Structural Gallery Tiers,Editorial Property Description Stack,Hospitality process layout splitting vertical text columns left and asymmetrical landscape photo gallery tracks right.,Solid clean off-white canvas layout background #FFFFFF. Gallery cards rounded 16px.,Upper headline text 48px uppercase. Column feature list check metrics.,Gallery row track entry coordinates translate horizontal card panels smoothly along X-axis while cross-fading inner photos.,"split-header-matrix, asymmetrical-gallery-slider, two-column-copy-block, travel",Main property specification walkthrough modules, real estate about-page blocks.
EDT-08,Editorial & Structural Gallery Tiers,Multi-Tabbed Category Amenity Grid,Symmetrical capabilities grid row layout aligning four portrait photo panels below top horizontal filter links.,Solid clean off-white canvas layout backdrop canvas field background sheets #FFFFFF. Photo cards rounded.,Section title heading text 42px uppercase bold. Link filter text layers 20px regular weights.,Toggling separate filter menu headers instantly clears core grid panel and fades incoming amenity photo frames via curves.,"category-filter-bar, amenities-grid, symmetrical-alignment, b2b-corporate",Property amenities showcases, e-commerce catalog main frames, portfolio grids.
EDT-09,Editorial & Structural Gallery Tiers,Editorial Museum Exhibition Banner,High-impact brutalist portal stacking a floating text card over a fanned horizontal marquee row of artwork cards.,Clean solid white background layer layout canvas. Artwork ribbon cards rounded 16px.,Marquee background text 82px bold. Exhibition card sub-caption text layers 14px regular weight.,Hover actions over narrow column strips smoothly expand horizontal layout width proportions while compressing adjacent fields.,"brutalist-text-marquee, overlapping-canvases, vertical-accordion-grid, history",Main heroes for art galleries, exhibition collection launches, timelines.
EDT-10,Editorial & Structural Gallery Tiers,Fine-Art Chronological Flagship Hero,Immersive art museum hero section tracking an open navigation top-bar above a multi-layered cascade of portrait art frames.,Clean white sheet layout canvas backdrop layer. Portrait art cells feature index paths '01'.,Main display headline 64px bold, cursive text script logo overlay 'of' in rich coral tone.,Move gestures or page scroll sequences trigger independent horizontal and vertical translation float offsets across layers.,"fine-art-hero, cursive-typography-overlay, overlapping-media-cards, alignment",Principal landing heroes for art institutions, digital portfolio indices.
EDT-11,Editorial & Structural Gallery Tiers,Asymmetrical Property Experience Grid,Advanced information-dense real estate features listing pairing an asymmetrical uppercase display title left with cards right,Solid pristine off-white canvas layout background layer. Photo cards horizontal card rows.,Section title heading text 42px uppercase. Property details text layers regular font weights.,Hover actions over individual gallery card containers prompt a subtle vertical translation lift alongside an active scale.,"asymmetrical-gallery-matrix, multi-scale-cards, luxury-lifestyle, onboarding",Boutique hotel amenities showcases, asset catalog overviews, experience designs.
EDT-12,Editorial & Structural Gallery Tiers,Wireframe Directory Matrix Footer,Minimalist corporate footer layout managing text row marquee cells over a wireframe grid matrix track.,Pristine uniform white canvas base layer #FFFFFF bordered by gray vertical layout lines.,Module main heading text 42px bold. Cell index tag text layers 14px regular tracking fields.,Hover actions over individual directory anchors prompt an immediate typography color conversion from dark gray to black text.,"wireline-grid-dividers, minimal-directory, brutalist-text-marquee, sub-footer",Baseline corporate footers, agency conversion closure folds, contact layouts.
EDT-13,Editorial & Structural Gallery Tiers,Milestone Checklist Accordion Panel,Educational 2-column feature walkthrough coordinating a vertical checklist timeline left with horizontal options right.,Solid clean off-white canvas layout field paneling with zero structural lines or gradients.,Two-row headline 38px uppercase bold. Active choice card features top absolute green badge.,Checklist circle nodes illuminate sequentially downwards along the vertical dashed tracking wireline track on view entry.,"milestone-checklist, horizontal-accordion-stack, overlapping-badge, travel",Property onboarding lists, tactical feature summary blocks, company charts.
EDT-14,Editorial & Structural Gallery Tiers,Advanced Booking Scheduler Stage,Advanced user booking scheduler stage balancing interactive dropdown fields left with showcase photo frames center.,Pristine uniform off-white layout canvas layer #FFFFFF. Summary conversion card panel white text layers.,Step timeline progress title text 16px. Statistical numeric layout text 44px regular black.,Mouse click entries into individual form dropdown field lines toggle border stroke properties into dark-teal active states.,"booking-scheduler-stage, step-progression-baseline, horizontal-split-pane, checkout",User portal registration sign-on gates, client booking calendars gateways.
EDT-15,Editorial & Structural Gallery Tiers,Minimal Balanced Text Statement Block,Typographic capability statement module featuring large regular gray text strings overlaid with copper accent text nodes.,Solid clean off-white canvas layout field paneling with zero structural lines or gradients.,Main display typography block 38px bold. Statement highlight phrase text layers bold regular.,Hovering individual cursor coordinates over the highlighted statement text triggers an immediate typography font weight shift.,"capabilities-statement, copper-accent-type, two-column-copy-block, clean",Company core mission statements, agency capability overviews, feature summary blocks.
EDT-16,Editorial & Structural Gallery Tiers,Advanced Booking Scheduler Stage (Var),Advanced user booking scheduler stage balancing vertical list options left with horizontal selection bento cards center.,Pristine uniform off-white layout canvas layer #FFFFFF. Summary conversion card panel white text layers.,Step timeline progress title text 16px. Statistical numeric layout text 44px regular black.,Hovering over individual horizontal resource cards smoothly elevates the target container wrapper and expands drop shadow.,"booking-scheduler-stage, step-progression-baseline, bento-cards-stack, fintech",Technical marketing documentation indices, product guide libraries, client booking calendars.
B2B-01,B2B Corporate & Fintech Overviews,Asymmetrical Interactive Use-Case Split,Editorial B2B feature layout split anchoring a vertical accordion panel left and multi-layered visual cards right.,Solid crisp white layout field canvas #FFFFFF. Accordion frames off-white #F5F5F5.,Section title headline 38px bold. Accordion collapsed tiers row gap metrics 16px.,Toggling separate use-case menu rows smoothly executes height text crossfades while instantly swapping right visual cards.,"split-use-case, interactive-accordion, layered-mockups, b2b-features",Industry vertical deep-dives, custom product use-case overviews, target persona walkthroughs.
B2B-02,B2B Corporate & Fintech Overviews,Pastel Aurora Glass Feature Deck,Symmetrical 4-column feature deck row distributing vertical bento cards filled with multi-colored aurora spots.,Pristine uniform white canvas backdrop layer #FFFFFF.,Card headings 22px bold black sans-serif. Inset circular glassmorphic icons well radius 24px.,Hovering over cards prompts underlying color mesh gradients to shift coordinate tracking parameters smoothly over easy curves.,"pastel-aurora, glassmorphism-icons, bento-features, symmetrical-deck",Platform core capability listings, specialized tool features, technical value propositions.
B2B-03,B2B Corporate & Fintech Overviews,Inset Workspace Dashboard Split,Editorial 2-column layout split coordinating structured vertical milestone checklists with an extra-large software mockup.,Clean white sheet layout canvas backdrop layer #FFFFFF. Mockup dashboard frame light gray.,Primary headline 42px bold, text marker highlight box 'Accelerate Growth'.,Viewport intersection visibility prompts inner concentric circular pipeline charts to dynamically paint via path stroke sweep.,"dashboard-mockup, text-marker-highlight, checklist-timeline, editorial-feature-split",Operational capabilities breakdowns, CRM product values overviews, enterprise value walkthroughs.
B2B-04,B2B Corporate & Fintech Overviews,Low-Contrast Minimalist Contact Closure,Low-contrast directory footer layout centering a giant email headline below an absolute full-width color bleed.,Solid matte deep charcoal black layout backdrop canvas background layers. Fluid turquoise mesh wash.,Topbar utility navigation links spacing 24px. Directory column link headers bold white text 16px.,Directory link anchors execute immediate font color weight conversion from dark gray to solid white text lines on hover.,"minimalist-footer-closure, neon-gradient-bleed, email-capture-form, footer",Baseline corporate footers, main closing conversion modules, legal directories.
B2B-05,B2B Corporate & Fintech Overviews,Technical Coordinates Footer Closure,Deep low-contrast directory footer layout focusing an email capture form over an engineering line matrix.,Dark slate-blue to charcoal wash background field overlaid with an infinite high-precision layout matrix.,Main headline 42px miniature white text layers. Baseline directory social icons row gap 16px.,Background technical line wirelines execute slow, ongoing automated keyframe opacity shimmer loop animation patterns.,"technical-coordinate-footer, email-capture-form, minimal-directory, dark-mode-closure",Baseline corporate footers, agency conversion closure folds, contact directory layouts.
B2B-06,B2B Corporate & Fintech Overviews,Wide Gradient Tech Directory Footer,Clean corporate directory footer closure layout focusing an email capture row and a large left-heavy brand logo mark.,Deep dark slate charcoal page canvas field. Low-contrast script typography design watermark 'VOXA'.,Upper row capture headline text 42px white. Directory menu link filters spacing 24px.,Directory menu link anchors execute immediate font color weight conversion from dark gray to solid white text lines on hover.,"minimalist-footer, giant-watermark-base, email-capture-form, horizontal",Flagship corporate footers, closure conversion landing fields, contact directory panels.
B2B-07,B2B Corporate & Fintech Overviews,Supply Chain Bento Testimonial Grid,Structured clean corporate 4-pane bento-box testimonial system mixing bold statement cards with reviews.,Clean uniform off-white layout canvas sheet layer #F3F7FA.,Card display text 28px bold white. Center profile review photo fields inside light-blue panels.,Bento container blocks prompt subtle elevation changes via drop shadow manipulation and an active scale shift on mouse hover triggers.,"bento-testimonials, dark-teal-gradient, profile-portraits, clean-corporate",Client feedback dashboards, social proof bento matrices, product success stories.
B2B-08,B2B Corporate & Fintech Overviews,Frosted Glass Carousel Overview,Open-layout conversion carousel tracking four vertical frosted glass cards below centered display text folds.,Full-bleed clean canvas base layer showing ultra-soft radial periwinkle gradient wash margins.,Uppercase headline category 'SALES ENGAGEMENT'. Main card sub-headers 24px bold text layers.,Horizontal carousel stage swipe translates cards along X-axis while smoothly enhancing backdrop blur filter density.,"frosted-glass-cards, horizontal-carousel, centered-conversion-cta, saas-showcase",Product suite modules list, platform ecosystem overviews, software workflow walkthroughs.
B2B-09,B2B Corporate & Fintech Overviews,High-Contrast Centered Bento Pricing,Structured 3-column pricing grid utilizing a prominent centered "Bento-Box" design layout where the highest-value plan physically pops out.,Pristine uniform light gray canvas background paneling #F9F9FA. White card backings #FFFFFF.,Plan title text 44px bold. Center professional plan card features top absolute capsule badge.,Hover actions over individual pricing bento cards prompt a subtle container elevation change via drop shadow manipulation.,"pricing-grid, bento-pricing-matrix, color-inversion-block, centered-conversion",Tiered subscription plans, software membership plans blocks, service upgrades matrices.
B2B-010,B2B Corporate & Fintech Overviews,Technical Coordinates Footer Matrix,Deep low-contrast directory footer layout focusing an email capture form over an engineering line wireline matrix.,Dark slate-blue to charcoal wash background field overlaid with an infinite high-precision layout matrix.,Main headline 42px crisp white text layers. Baseline directory social icons row gap 16px.,Background technical line wirelines execute slow, ongoing automated keyframe opacity shimmer loop animation patterns.,"technical-coordinate-footer, email-capture-form, minimal-directory, dark-mode-closure",Baseline corporate footers, agency conversion closure folds, contact directory layouts.
B2B-11,B2B Corporate & Fintech Overviews,Inline Horizontal Capabilities Slider,Minimalist capabilities slider marquee tracking dark landscape service cards complete with 3D isometric machinery.,Solid clean off-white canvas layout backdrop canvas field #FFFFFF. Card backing matte teal #0D1F22.,Amount heading text 38px bold white. Center active card features light-blue asset box.,Slider navigation controls shift row panels horizontally along X-axis while cross-fading card background properties.,"capabilities-slider, horizontal-carousel, b2b-minimalist, isometric-illustrations",Core enterprise capabilities showcases, technical service portfolio category overviews.
B2B-12,B2B Corporate & Fintech Overviews,Symmetrical Social Proof Slider,High-key customer review carousel distributing white options cards above centered circular navigation buttons.,Solid pristine off-white sheet layout canvas layer #FFFFFF. Card wrappers box shadow metrics.,Section main title 42px extra bold. Testimonial copy text regularRegular font weight tracking.,Slotted interaction triggers translate the carousel track on X-axis while lifting container wrapper height parameters.,"testimonial-slider, high-key-social-proof, clean-corporate, symmetrical-carousel",Customer reviews hubs, case study carousels, social proof grids.
B2B-13,B2B Corporate & Fintech Overviews,Trusted Partner Marquee Baseline,Sleek educational baseline panel pairing a horizontal partner logo row with a 3-column success metrics table.,Solid pristine off-white sheet layout canvas layer #FFFFFF.,Partner banner headline text 16px. Statistical metrics text 44px regular black tracking.,Viewport intersection triggers automated rapid digital odometer counting loops across percentage digits row-by-row on load.,"trusted-partner-row, corporate-marquee, metric-grid, social-proof-baseline",Core platform success statistics, customer acquisition proofs, partner marquee baselines.
B2B-14,B2B Corporate & Fintech Overviews,High-Fidelity Split Identity Login Card,Elite gateway interface enclosure centering a 2-column entry card built with dark brand badges and white forms.,Soft light sky-blue wash gradient backdrop field canvas layers behind central card layouts.,Form title heading text 22px bold. Input field boxes placeholder typography text regular.,Mouse click entries into individual form input field lines toggle border stroke properties into dark-teal active states.,"login-card, split-identity-form, social-sign-on, b2b-gateway",User portal sign-on screens, client onboarding gateways, entry form dashboards.
B2B-15,B2B Corporate & Fintech Overviews,Dark Linear Metric Core Showcase,High-contrast value grid tracking a vertical 4-column array of matte dark boxes filled with neon blue glyphs.,Solid deep charcoal black surface canvas backdrop #0D0D0D. Content cards matte black #121212.,Main headline display text 52px uppercase white text. Highlight phrase 'EMOTION' in blue text.,Central neon-blue vector icons execute a continuous automated slow-duration radial brightness pulse animation cycle.,"dark-mode-grid, neon-blue-glyphs, asymmetrical-header, value-proof",Platform core capability overviews, product value propositions, strategic pillars charts.
B2B-16,B2B Corporate & Fintech Overviews,Centered Isomorphic Supply Chain Hero,B2B tech landing hero centering an oversized global network blueprint chart above stacked conversion buttons.,Pristine uniform off-white layout canvas layer #FFFFFF. Globe asset turquoise mesh gradients.,Giant headline display layout 56px dark slate blue text layers. Description copy regular weight.,Logic schematic dashed layout paths execute continuous automated SVG dash-offset texturing flow lines across the globe.,"isometric-network-hero, global-reach, b2b-saas, centered-conversion",Flagship landing pages for supply chain platforms, global B2B operations tools, logistics dashboards.
B2B-17,B2B Corporate & Fintech Overviews,Dynamic Fluid Liquid-Core Creative Hero,Ultra-modern agency hero framing a rotating 3D fluid art sculpture behind giant text rows and capability marquees.,Light gray to periwinkle gradient wash backdrop overlaid with giant low-contrast watermark 'DESIGNCY'.,Extra bold headline text 60px black. Integrated dark capsule button arrow badge '↗' in row.,Central 3D fluid chrome sphere executes an automated continuous keyframe mesh transformation loop animation over easy curves.,"3d-liquid-core, watermark-backdrop, capsule-video-tab, capability-marquee",Main landing heroes for creative digital agencies, production studios, brand design portfolios.
B2B-18,B2B Corporate & Fintech Overviews,Editorial Checklist Progression Split,2-column feature split coordinating vertical milestone checklists with an absolute overlapping analytics panel.,Solid pristine off-white canvas layout background layer #FFFFFF. Checklist cards white capsule shapes.,Primary headline 42px bold black sans-serif. Overlapping analytics panel text layers 18px.,Viewport visibility triggers automated rapid digital odometer counting loops across vertical metrics check boxes on load.,"vertical-checklist, overlapping-analytics, b2b-minimalist, step-progression",Operational roadmap walkthroughs, product value charts, corporate onboarding progression modules.
B2B-19,B2B Corporate & Fintech Overviews,Parallax Whirlpool Loop Footer,Corporate directory footer layout centering an upper whirlpool vortex conversion banner over a 4-column index.,Clean white upper canvas transitioning down into a solid deep slate navy baseline footing fold track.,Card title text 36px white. Directory column headers bold white text 16px. Sub-link blue regular.,Full-bleed blue vortex background image layer executes a scroll-driven parallax velocity shift relative to frame bounds.,"whirlpool-vortex, capsule-conversion-card, directory-link-columns, sub-footer",Enterprise platform baseline footers, main closing conversion modules, legal directories.
B2B-20,B2B Corporate & Fintech Overviews,Scattered Abstract Division Board,Editorial portfolio gallery block pairing an extra-large display title with pastel panels and a floating CTA arrow.,Light gray to periwinkle soft gradient canvas base sheet layout canvas layer. Pastel cards rounded 16px.,Upper headline text 46px bold. Scattered capability capsule tags spacing 16px.,Hovering individual gallery cards prompts a subtle vertical translation lift translateY(-4px) and internal asset scale expansion.,"scattered-gallery-grid, pastel-cards, 3d-geometric-objects, floating-arrow",Agency capabilities indices, creative studio division selectors, product classification carousels.
B2B-21,B2B Corporate & Fintech Overviews,Balanced Triple-Pane Production Showcase,Clinical B2B capabilities block aligning a center header block with three rounded industrial photography frames.,Solid clean off-white canvas layout backdrop field canvas line matrix #FFFFFF.,Main title header 42px. Baseline metric counters text 36px regular black tracking.,Viewport intersection visibility prompts the four baseline metric counter digits to count up from 0 to final integers.,"production-showcase, industrial-bento-grid, metric-baseline-panel, social-proof",Enterprise product capabilities lists, industrial workflow overviews, corporate success proofs.
B2B-22,B2B Corporate & Fintech Overviews,Split-Pane Document Resource Grid,2-column resource grid matching primary report cards left with a vertical stack of custom vector illustrations right.,Pristine uniform white canvas backdrop layer #FFFFFF. Horizontal resource cards white #FFFFFF.,Left title header text 42px bold. Resource card text titles 18px bold. Button container capsule 16px.,Hovering over horizontal option boxes smoothly expands container drop shadow values and executes vertical translation lift.,"resource-grid, vector-marketing-illustrations, split-feature-layout, minimal",Technical marketing documentation indices, product guide libraries, corporate resource centers.
B2B-23,B2B Corporate & Fintech Overviews,Wide Wave-Gradient B2B Closure Banner,Corporate closure conversion footer designed around a curved full-bleed wave-gradient turquoise mesh backdrop.,Dark slate-blue to charcoal canvas background field layer. Upper wave banner turquoise-to-teal mesh.,Banner main title text 38px bold white. Directory column headers regular white text 16px.,Directory link selections execute immediate font color weight conversion from dark gray to solid white text lines on hover.,"wave-gradient-mesh, turquoise-globe-backdrop, directory-link-grid, conversion",Enterprise supply chain base footers, primary closing conversion modules, legal directories.
B2B-24,B2B Corporate & Fintech Overviews,Split-Pane Operational Sign-On Screen,High-contrast user registration entry panel balancing operator portraits left with interactive forms and timelines right.,Soft light sky-blue wash gradient backdrop field canvas layers behind central card layouts.,Form title heading text 22px bold. Input field boxes placeholder typography text regular.,Mouse click entries into individual form input field lines toggle border stroke properties into dark-teal active states.,"registration-card, split-pane-form, operator-portrait, step-progression-base",Enterprise registration sign-on gates, client portal gateways, user implementation gates.
B2B-25,B2B Corporate & Fintech Overviews,Biotech Coordinate Mesh Hero,Elite clean corporate landing hero layering an absolute 3D coordinate mesh wave pattern beneath a metrics dashboard.,Deep matter slate-gray background field canvas layer #1C2A2D. Inset wave vector mesh 3D lighting topography.,Main display title H1 text 56px bold. Baseline metrics panels text 24px regular.,Inset 3D vector mesh wave pattern executes an ongoing slow-duration wave distortion loop animation pattern across the page.,"biotech-mesh-hero, 3d-coordinate-topography, asymmetrical-metrics, conversion",Principal landing page heroes for deep-tech medical tools, biotechnical platform services.
B2B-26,B2B Corporate & Fintech Overviews,Split-Pane Visual Chronicle Progress,Editorial 2-column milestone section pairing vertical accordion stacks left with a large play media frame right.,Soft light-blue to lavender gradient wash canvas backdrop sheet layout canvas layer.,Section title headline 42px extra bold black. Left accordion cards off-white #F5F5F5.,Accordion menu row toggle paths smoothly execute vertical height text crossfades while instantly swapping right video tracks.,"split-chronicle, interactive-accordion-stack, media-showcase-frame, vector",Interactive corporate timelines, history benchmarks overviews, company milestone walkthroughs.
B2B-27,B2B Corporate & Fintech Overviews,Tabbed Multi-Pane Scenario Interaction,Advanced media walkthrough section linking active neon orange-red filter cards right with cinematic alert viewports.,Solid pristine matte black page canvas backdrop template lines #000000. Scenario frames landscape.,Filter selector heading text 18px bold uppercase. Inset text block paragraphs regular weight.,Activating alternative filter headers highlights the selected lane and triggers a swift horizontal image layout swap on click.,"scenario-simulation, neon-orange-filters, cinematic-media-frame, tabbed-ui",Specialized software product use-case overviews, real-time alert simulation modules.
B2B-28,B2B Corporate & Fintech Overviews,Cinematic Ambient Spark Media Hero,Bold editorial news landing hero centering a handheld product mockup inside a dual-tone uppercase logo marquee.,Solid deep charcoal black sheet layout canvas layer with vertical red/copper spark tracking ember fields.,Main wordmark text 64px uppercase tracking. Red contact button text 16px bold.,Underlying copper particle layers execute an ongoing automated slow-duration float keyframe loop upward on the Y-axis.,"cinematic-spark-hero, handheld-device-mockup, dual-tone-typography, live",Primary main landing heroes for digital journalism platforms, live-streaming applications.
B2B-29,B2B Corporate & Fintech Overviews,Multi-Stage Pipeline Milestone Grid,Information-dense development tracking row layering 3 horizontal white bento boxes complete with phase progress lines.,Solid deep slate-blue to charcoal wash canvas background field #0E1A1C. Bento cards rounded 12px.,Sub-header title text 24px bold black sans-serif. Column feature list check metrics.,Viewport card visibility triggers automated horizontal fill progression on the baseline milestone line tracker from left.,"milestone-bento-cards, horizontal-pipeline-bar, 3d-molecular-assets, phase",Product roadmap breakdowns, regulatory phase checklists, technical implementation modules.
B2B-30,B2B Corporate & Fintech Overviews,Symmetrical Linear Team Identity Grid,Minimal corporate team showcase grid aligning four square portrait photo cards over thin wireline dividers.,Pristine uniform off-white layout canvas layer #F9F9F9. Photo cards square headshot frames.,Uppercase role title text 14px neon red. Name signature headline 18px bold uppercase text.,Identity card hover coordinates translate text metadata rows upwards while executing a subtle grayscale-to-color image shift.,"team-showcase-grid, wireline-grid-dividers, neon-role-tags, clean-alignment",Corporate team overview grids, leadership bios, company culture showcase blocks.
B2B-31,B2B Corporate & Fintech Overviews,Overlapping Presentation Deck Collage,Abstract conversion module cascading an intricate layout matrix of white and dark landscape sheets over data models.,Clean white sheet layout canvas backdrop layer #FFFFFF. Center active card deep dark teal.,Center dashboard title text 24px white. Statement highlight phrase neon green marker box.,Move gestures or page scroll sequences trigger independent horizontal and vertical translation float offsets across deck layers.,"slide-deck-collage, donut-chart-data, text-marker-highlight, layered-cascade",Company pitch deck previews, investment summary folds, technical data overviews modules.
B2B-32,B2B Corporate & Fintech Overviews,Concentric Circle Value Proposition Grid,Brutalist features summary matrix tracking 6 oversized intersecting circle wireframes filled with neon orange icons.,Solid rich matte black canvas background backdrop template lines #000000. Circle outlines dark gray.,Circle internal text sub-headers 16px bold white text. Icon badges diameter 40px.,Overlapping dark gray wireframe circle outlines execute a slow, continuous automated rotation loop animation on center axes.,"concentric-wireframe-circles, brutalist-grid, neon-orange-icons, value-mesh",Core business value propositions lists, product advantages matrices, key features sheets.
B2B-33,B2B Corporate & Fintech Overviews,Comparative Metric Performance Panel,Diagnostic 3-column data evaluation section pairing comparison titles left with inverted horizontal data bars center.,Clean uniform high-key white layout field canvas backdrop canvas field #FFFFFF.,Section title headline 42px bold. Center traditional method card light gray backing.,Viewport intersection visibility prompts the giant '16x' statistical counter digit to scale rapidly upward from scale(0).,"comparative-data-bars, inverted-color-tier, oversized-stat-counter, b2b-mesh",Platform processing comparisons pages, performance metric benchmarks, service upgrades.
B2B-34,B2B Corporate & Fintech Overviews,High-Contrast Split-Pane Contact Closure,Corporate conversion closure footer balancing a solid neon orange link directory left with a dark capture form right.,Split canvas base: left 50% neon orange field canvas, right 50% solid deep black page canvas sheet.,Orange pane headline text 60px extra bold white. Right input fields dark rounded box blocks.,Hovering text anchors inside the orange pane dynamically expands a bold white baseline row underline element on mouse entry.,"split-color-closure, neon-orange-pane, form-input-matrix, directory-menu",Main company contact closures, agency lead capture endfolds, registration form gate panels.
B2B-35,B2B Corporate & Fintech Overviews,Split-Screen Profile Showcase Hero,Editorial 50/50 split hero page separating an immersive user profile gallery left from a right conversion CTA stack.,Clean solid white background layer layout canvas. Profile card background sky blue.,Headline display text 60px blue tracking text. Social proof badge text 14px regular weight.,Interaction triggers translate the left-hand profile cards horizontally on X-axis while smoothly scaling portrait assets.,"split-hero-layout, profile-mockup, social-proof-badge, saas-conversion",Main heroes for AI networking tools, recruitment platforms, talent matching software.
B2B-36,B2B Corporate & Fintech Overviews,Triple-Pane Graphic Feature Grid,Symmetrical 3-column feature deck row layout layering centered top text folds directly over elongated gradient cards.,Pristine uniform off-white canvas layout sheet featuring organic vector outline curves.,Card heading text 20px bold black. Description copy regular regular Regular weight tracking.,Card hover coordinates smoothly translate container wrappers vertically translateY(-8px) while expanding drop shadow radius.,"three-column-bento, gradient-wash-cards, clean-alignment, symmetrical-grid",Platform core capability walkthrough overviews, product value propositions matrices, features.
B2B-37,B2B Corporate & Fintech Overviews,High-Contrast FinTech Bento Matrix,Asymmetrical corporate capabilities section built around an asymmetrical 3-column bento design filled with 3D models.,Solid clean white canvas configuration field. Priority card panel periwinkle gradient wash.,Left title display text 48px, campaign baseline row text 14px. Data cells regular weights.,Cursor tracking coordinates trigger gentle independent vertical parallax translation offsets across 3D geometric assets.,"bento-capabilities-matrix, 3d-geometric-renders, asymmetrical-text, fintech",Corporate financial features list, bento capability matrices, core platform values charts.
B2B-38,B2B Corporate & Fintech Overviews,Flagship FinTech App Dashboard Hero,Elite financial landing hero combining centered text marker highlights with an extra-large 3D software device mockup.,Clean airy full-bleed canvas base layer showing ultra-soft periwinkle radial gradient wash margins.,Extra bold headline text 58px, periwinkle marker highlight box 'Reliable'. Input form capsule.,Scroll-driven parallax metrics translate the floating dashboard mockup window and adjacent 3D coins at independent velocity ratios.,"fintech-hero-dashboard, 3d-mockup-cascade, text-marker-highlight, gradient",Principal landing heroes for financial tools, enterprise wealth management, B2B SaaS heroes.
B2B-39,B2B Corporate & Fintech Overviews,3D Geometric Solution Bento Grid,Clinical B2B capabilities block tracking an asymmetrical bento grid layout matrix across rounded white container cells.,Solid pristine off-white canvas layout background layer #FFFFFF. Primary card panel light blue.,Section title headline 42px bold. Left wide card features top absolute capsule badge.,Hover actions over individual bento card containers prompt a subtle container elevation change via drop shadow manipulation.,"bento-services-grid, 3d-minimalist-assets, asymmetrical-alignment, b2b-corp",Corporate service overviews, core capabilities indices, product portfolio carousels.
B2B-40,B2B Corporate & Fintech Overviews,Asymmetrical Carousel Review Wall,Immersive light-mode social proof review module distributing four vertical white cards across a wide horizontal track.,Full-bleed background canvas displaying an ultra-soft radial periwinkle gradient wash.,Card display text 16px regular. Client profile signature text bold black sans-serif text.,Slotted interaction triggers translate the carousel track on X-axis while lifting container wrapper height parameters.,"testimonial-carousel, high-key-social-proof, clean-corporate, slider",Customer reviews hubs, case study carousels, social proof grids.
B2B-41,B2B Corporate & Fintech Overviews,Symmetrical Pastel Icon Division Board,Clinical capabilities grid row aligning five vertical rectangle cards filled with pastel panels and 3D objects.,Solid clean off-white canvas layout backdrop canvas field background sheets #FFFFFF. Pastel panels.,Main title heading text 42px bold black. Card subtitle headers 20px. Action capsule button.,Hover vectors over card modules trigger an asymmetrical vertical translation lift translateY(-8px) and interior photo scale.,"division-grid, pastel-cards, 3d-geometric-objects, staggered-alignment",Educational category overviews, e-commerce division matrices, portfolio classification selectors.
B2B-42,B2B Corporate & Fintech Overviews,Layered Progressive FAQ Dashboard,Elite deep-mode informational section nesting an upper capsule conversion card above a vertical accordion stack.,Solid pristine off-white canvas layout background layer #FFFFFF. Accordion frames light gray.,Form capsule headline text 26px white text. Accordion question row titles text 18px.,Toggling an accordion row triggers smooth max-height interpolation layout transitions while right chevron icons cross-rotate.,"faq-dashboard, capsule-conversion-card, interactive-accordion-stack, step",Specialized software product use-case overviews, regulatory phase checklists, walkthroughs.
B2B-43,B2B Corporate & Fintech Overviews,Vertical Milestone Timeline Progression,Educational 2-column onboarding feature split coordinating vertical dashed checklists with a dashboard mockup frame.,Solid clean off-white canvas layout field paneling with zero structural lines or gradients.,Main display title headline 44px bold. Step timeline titles 22px bold.,Milestone circle nodes illuminate sequentially downwards along the vertical dashed tracking wireline track on view entry.,"milestone-checklist, dashed-timeline, software-mockup-frame, educational",Onboarding guides, product setup processes, user implementation steps.
B2B-44,B2B Corporate & Fintech Overviews,Capsule Closure Conversion Footer,Deep corporate directory footer closure layout centering an upper capsule conversion card over a 3-column index.,Clean white upper canvas transitioning down into a solid deep slate navy baseline footing fold track.,Card title text 36px white. Directory column headers bold white text 16px.,Directory link selections execute immediate font color weight conversion from dark gray to solid white text lines on hover.,"capsule-conversion-card, geometric-glass-backdrop, directory-link-grid, sub",Primary main closing conversion modules, enterprise platform baseline footers, legal directories.
B2B-45,B2B Corporate & Fintech Overviews,Technical Wire-Grid Feature Block,Brutalist data feature grid mapping four cards bounded by thin neon yellow wirelines over an engineering pixel-grid matrix.,Solid matte black canvas sheet layer covered with a uniform yellow coordinate tracking grid matrix.,Left title text 44px condensed bold neon yellow. Inset square yellow badge icon check metrics.,Viewport intersection visibility prompts the background pixel-grid lines to execute a slow horizontal and vertical sweep loop.,"technical-coordinate, brutalist-neon, bento-capabilities, dark-mode-security",Core security features list, infrastructure protocol compliance indices.
B2B-46,B2B Corporate & Fintech Overviews,Immersive Lifestyle Portrait Folds,Organic consumer medical section layering four glassmorphic capsules over full-bleed blue radial gradient washes.,Smooth full-bleed canvas base layer showing ultra-soft cobalt blue radial gradient wash margins.,Main display title headline 48px bold. Glass capsule text rows font-size 16px white.,Move gestures across coordinates trigger gentle independent keyframe translation float offsets across glassmorphic capsule cards.,"lifestyle-portrait, glassmorphic-capsules, radial-gradient-wash, organic",Consumer health journey walkthroughs, lifestyle digital product overviews, personas.
B2B-47,B2B Corporate & Fintech Overviews,Asymmetrical Editorial Split-Pane Hero,Editorial split-pane hero separating text lists left from an interlocking diamond photo collage right.,Clean solid white background layer layout canvas. Collage portrait photo headshot frames.,Left title main text 56px bold black sans-serif text. Baseline metric statistics nodes 34px.,Hover actions over individual image cells inside the right-hand collage smoothly expand mask boundaries and scale frames.,"editorial-hero-split, diamond-collage, asymmetrical-metrics-base, agency",Main flagship landing heroes for creative design studios, advertising agencies.
B2B-48,B2B Corporate & Fintech Overviews,Technical Analytics Bento Metrics Row,Structured statistics module distributing five independent dark boxes across an asymmetrical two-row framework.,Solid matte deep black background canvas layer #050505. Bento metrics cards dark gray #121212.,Yellow coordinate path marker index line text '/RESULTS'. Metric numerical values 38px bold.,Viewport box visibility prompts the five baseline data counter text nodes to count up from 0 sequentially on load grid tracks.,"bento-metrics-row, brutalist-neon-yellow, dark-mode-dashboard, social-proof",Core enterprise protocol success statistics, data security growth proof panels.
B2B-49,B2B Corporate & Fintech Overviews,Handheld Device Mockup Conversion Hero,Elite landing hero centering a handheld smartphone mockup tracking live video over a blue-sky radial gradient wash.,Soft, light-blue wash gradient backdrop field canvas layer. Mockup smartphone frame absolute.,Main display layout 58px white text layers. Description copy regular regular tracking rules.,Move gestures or page scroll sequences trigger independent horizontal and vertical translation float offsets across handheld.,"handheld-device-mockup, saas-conversion-hero, radial-gradient-wash, medical",Principal landing heroes for medical applications, health-tech protocol software.
B2B-50,B2B Corporate & Fintech Overviews,Brutalist Capture Form Grid Matrix,High-impact brutalist split block balancing bulleted benefits lists left with a towering yellow-framed capture form right.,Solid matted deep charcoal black background field canvas layer #0B0B0B. Capture form card panel.,Left title heading text 38px neon yellow. Form card main title text 42px uppercase yellow.,Mouse click entries into individual form input field lines toggle border stroke properties into neon-yellow active states.,"brutalist-form-matrix, neon-yellow-accents, benefits-checklist, dark-mode",Main closing conversion modules, enterprise registration sign-on gates, lead captures.
B2B-51,B2B Corporate & Fintech Overviews,Iridescent Torus SaaS Landing Hero,Advanced SaaS hero section layering giant display typography behind an extra-large 3D liquid chrome bubble sphere asset.,Solid deep indigo-to-violet canvas base layer #1C103F. Underlying color mesh gradient spotwells.,Main display title text 54px extra bold. Inset capsule button periwinkle. Avatar proof text.,Central 3D fluid chrome sphere executes an automated continuous keyframe mesh transformation loop animation over easy curves.,"iridescent-3d-core, liquid-chrome-sphere, b2b-saas-hero, avatar-proof-row",Principal landing heroes for developer automation tools, AI code copilots, software walkthroughs.
B2B-52,B2B Corporate & Fintech Overviews,Alternating Capsule Portfolio Matrix,Minimalist capabilities slider marquee tracking active portrait containers complete with right-anchored arrow badges.,Solid clean off-white canvas layout backdrop canvas field background sheets #FAF8F5.,Card text titles 20px bold. Photo card text check list tags.,Slide controls shift the service track horizontally along X-axis while cross-fading inner photo frames dynamically on click.,"portfolio-gallery-grid, horizontal-carousel, floating-arrow-cta, editorial",Core agency capabilities showcases, creative studio portfolio carousels, categories.
B2B-53,B2B Corporate & Fintech Overviews,Vertical Ribbon Marquee Showcase,Clinical 7-column service grid balancing an active expanded photo card left with towering vertical ribbon marquee strips right.,Solid clean off-white canvas layout backdrop canvas field #F9F9FA. Row grid dividers vertical lines.,Section title heading text 38px bold black text rows. Active card heading text layers 24px.,Hover actions over narrow column strips smoothly expand horizontal layout width proportions while compressing adjacent fields.,"vertical-accordion-grid, editorial-columns, ribbon-marquee, text-symmetrical",Core agency capabilities lists, software portfolio category overviews, portals.
B2B-54,B2B Corporate & Fintech Overviews,Flagship SaaS Platform Blue-Sky Hero,Technology landing hero centering an umbrella arch mockup window over a blue-sky cloud panoramic mountain layer base.,High-fidelity photographic canvas displaying bright white cumulus cloud banks fading into blue sky washes.,Main headline 56px, dual-colored linear text gradient fill layer 'Create CustomGPTs'.,On initial viewport visibility, third-party icons animate sequentially outward from apex node down left and right paths.,"blue-sky-hero, integration-umbrella-arch, concentric-logo-bridge, saas",Principal landing heroes for cloud automation tools, software integration hubs.
B2B-55,B2B Corporate & Fintech Overviews,Interactive Medical Card Carousel,User-centric feature walkthrough segmenting an active card choice vertically inside periwinkle horizontal dashboards.,Clean solid white background layer layout canvas #FFFFFF. Active choices grey noise panels.,Card headline text 42px bold. Row checklist text regularRegular weight tracking metrics bounds.,Card deck frames execute automated staggered entry animations, sliding upwards into line row-by-row on load view.,"card-deck, fanned-carousel, bento-metrics, health-tech",Core features lists, medical tool capabilities lists, walkthroughs.
B2B-56,B2B Corporate & Fintech Overviews,Luxury Balanced Product Showcase Hero,Premium watch landing hero layering a vertical brand marquee behind a giant 3D mechanics skeleton sports watch asset.,Full-bleed clean canvas base layer showing ultra-soft periwinkle radial gradient wash margins.,Main headline 58px bold, vertical script script typography design layer 'Hublot' text.,Central 3D skeleton watch asset executes a continuous slow-duration automated rotation animation loop on center axes.,"luxury-showcase, 3d-hardware-render, watermark-sidebar, premium-landing",Flagship luxury product heroes, premium consumer tech landing overviews, catalogs.
B2B-57,B2B Corporate & Fintech Overviews,Dual-Pane Luxury Presentation Row,Balanced 2-column layout split coordinating product division cards left with an absolute full portrait photography frame right.,Pristine uniform white canvas backdrop layer #FFFFFF.,Left title display text 32px bold black text rows. Description copy regularRegular weight tracking.,Hovering over right portrait photo frames triggers a subtle media zoom push inside layout clip boundaries on mouse entry.,"split-media-layout, luxury-branding, product-showcase, clean-corporate",Premium product divisions overviews, specialized catalog highlights, portfolios.
B2B-58,B2B Corporate & Fintech Overviews,Interactive Multi-Grid Persona Dashboard,Advanced metrics summary bento matrix balancing user lifestyle closeups left with 4-quadrant research widgets right.,Solid matte deep charcoal black background field canvas layer #000000. Research cards white #FFFFFF.,Widget title heading text 18px regular tracking. Persona age indicator text 26px bold text.,Viewport card intersection triggers a rapid horizontal slide progress fill translation across metrics tracking lines on load.,"bento-dashboard-matrix, user-persona, progress-tracking-bars, dark-mode",Specialized software case studies, target user persona walkthrough overviews, metrics.
B2B-59,B2B Corporate & Fintech Overviews,Brutalist Overlapping Lookbook Hero,High-impact brutalist fashion landing hero section that layers massive canvas-filling display typography behind a cursive script overlay.,Solid matte light gray background field canvas layer covered with vertical alignment wirelines.,Brutalist background text 110px condensed. Central photo frame vertical portrait.,Cursor tracking coordinates trigger gentle opposite horizontal translation float offsets across background text blocks.,"brutalist-grid, overlapping-media, cursive-typography-overlay, brutalist",Streetwear fashion catalog lookbooks, creative studio collection launches, lookbooks.
B2B-60,B2B Corporate & Fintech Overviews,Diagonal-Cut Monochrome Testimonial,High-contrast review carousel tracking four diagonal-cut masked portrait panels above bulleted indicator text quotes left.,Solid pristine off-white canvas layout background #FFFFFF. Mask backgrounds sky-blue.,Section main title 56px condensed bold. Client name metadata notes font-size 14px text.,Chevron mask elevation coordinates translate portrait frames vertically translateY(-8px) while expanding masks on hover.,"diagonal-cut-masks, chevron-imagery, asymmetrical-header, social-proof",Main corporate testimonials blocks, B2B agency review centers, milestone charts.
B2B-61,B2B Corporate & Fintech Overviews,Inverted Contrast Dual-Pane Block,Elite social proof section balancing a giant center text quote right with an oversized diagonal-cut portrait card left.,Solid vibrant golden-yellow field canvas, transitioning right into white radial gradient wash mesh spots.,Right headline display text 42px bold. Context sub-link headers regular weight tracking.,Hovering individual anchors inside right pane dynamically expands a bold white baseline row underline element on mouse entry.,"diagonal-cut-portrait, inverted-color-split, large-scale-quote, b2b",High-value client feedback dashboards, bottom-of-island conversion fields.
B2B-62,B2B Corporate & Fintech Overviews,Frosted Glass Capsule Botanical Showcase,Organic product feature grid centering three glassmorphic capsules over full-bleed photographic green branch layers.,Clean uniform off-white layout canvas sheet layer #FFFFFF. Botanical branch asset center axis.,Card heading text 20px bold black. Description copy regular regular Regular weight tracking metrics bounds.,Move gestures across coordinates trigger gentle independent keyframe translation float offsets across glassmorphic shapes.,"glassmorphic-capsules, botanical-assets, organic-product-ui, interlocking",Natural product ingredient lists, e-commerce core walkthrough overviews, wellness.
B2B-63,B2B Corporate & Fintech Overviews,Kinetic Block Out Lookbook Grid,Brutalist fashion lookbook lane tracking five vertical color-block cards below an uppercase description block paragraph text.,Solid vibrant neon-red horizontal sheet background field canvas layer. Color panels orange/pink.,Upper headline text 14px regular uppercase text. Content list text regular font weight tracking.,Hovering over baseline photo cells smoothly widens horizontal layout proportions flex: 2.5 while shrinking neighbors.,"brutalist-grid, color-block-panels, expandable-columns, brutalist",Streetwear fashion catalog lookbooks, creative studio collection launches, indices.
B2B-64,B2B Corporate & Fintech Overviews,Technical Blueprint Software Showcase,Technical B2B feature layout split anchoring a software matrix card left and dashboard mockup panels right.,Clean stark white canvas sheet backdrop layer. Mockup browser interface light gray.,Left section headline 54px bold. Right mobile viewports feature top absolute capsule badge.,Logic workflow micro-interaction loop automatically translates target task elements up and down on a continuous loop inside.,"technical-blueprint, dashboard-mockup, text-marker-highlight, minimalist",Main technology landing heroes, B2B workflow software indices, checklists.
B2B-65,B2B Corporate & Fintech Overviews,High-Contrast Typographic Product Hero,Editorial fashion hero centering a giant red text display overlay above a horizontal row of three streetwear image frames.,Solid deep charcoal black surface canvas backdrop template lines #0D0D0D. Card frames rounded 12px.,Main title display layout 72px uppercase red. Card heading text layers 16px bold text.,Inset hover indicators expand the media image asset inside its clip boundary while shifting text colors to solid white text.,"high-contrast-typography, streetwear-lookbook, asymmetrical-grid, dark-mode",Flagship heroes for high-end fashion brands, e-commerce lookbook portals, portfolios.
B2B-66,B2B Corporate & Fintech Overviews,Frosted Glass Capsule Botanical Showcase (Var),Symmetrical wellness platform overview aligning three vertical frosted glass columns over full-bleed panoramic moss fields.,Full-bleed panoramic photographic portrait of rolling green moss-covered agricultural hills.,Upper headline text 42px. Inset circular card container radius 14px.,Viewport card intersection visibility prompts underlying green moss color pixels to dynamically distort under glass panels.,"glassmorphic-capsules, panoramic-nature-field, organic-product-ui, align",Wellness platform value propositions lists, natural product ingredient lists, overviews.
B2B-67,B2B Corporate & Fintech Overviews,Premium Tiered Product Catalog Matrix,Structured product suite lists centering an active black card choice horizontally inside vertical price tiers.,Solid pristine off-white sheet canvas layer #FFFFFF. Card frames rounded 16px.,Plan title text 42px bold. Card subtitle headers 18px bold white text layers.,Hover actions over individual pricing bento cards prompt a subtle container elevation change via drop shadow manipulation.,"product-catalog-grid, luxury-watch-assets, black-bento-cards, saas-cta",Specialized software product suites list, tiered subscription plans, upgrades pages.
B2B-68,B2B Corporate & Fintech Overviews,High-Key Grid Catalog Showcase,Advanced e-commerce product overview section balancing top horizontal filter selectors with a 2-row multi-column card grid.,Pristine uniform white canvas backdrop layer #FFFFFF. White card wrappers round white circle badge.,Card title text 22px bold black. Price indicator tag text layers 16px regular tracking fields.,Staggered card entries execute automated rapid digital odometer counting animations across product bottle digits on load.,"product-catalog-grid, supplement-bottle-assets, white-bento-cards, grid-mesh",Educational category overviews, e-commerce division matrices, classification.
B2B-69,B2B Corporate & Fintech Overviews,Horizontal Product Slider Marquee,Luxury catalog row track centering an expanded watch card horizontally inside an open horizontal carousel line.,Solid pristine matte black page canvas backdrop template lines #050505. Orange text tags.,Split title display text 36px regular white text. Slider selection filters spacing 24px.,Pressing the header navigation keys shifts active campaign card rows horizontally along the horizontal stage track on click.,"campaign-slider, fintech-cards, progress-tracking-bars, dark-mode-carousel",Live crowdfunding investment opportunities, product catalogs trackers, watch lookbooks.
B2B-70,B2B Corporate & Fintech Overviews,Overlapping Translucent Wireframe Hero,Technical B2B hero section layering a full-bleed background matrix of transparent geometric glass tiles below center text.,High-key multi-colored radial gradient wash canvas base layer. Translucent 3D glass tiles.,Main headline display text 64px bold, text tracking phrase regularRegular font weight tracking.,Page scroll actions trigger multi-layered parallax float speed interpolation across overlapping background glass tile layers.,"3d-glass-tiles, geometric-parallax, high-contrast-editorial, baseline-status",Main flagship landing heroes for software houses, technical B2B SaaS heroes.
B2B-71,B2B Corporate & Fintech Overviews,Split-Contrast Premium Asset Showcase,Editorial product showcase split balancing watch portrait assets left with multi-column text customization lists right.,Pristine uniform white canvas backdrop layer #FFFFFF. Product card background sky blue gradient wash.,Left title header text 48px bold. Watch model text node heading 22px bold black sans-serif.,Inset hover indicators expand the left watch asset frame into a glowing wide light bar sweep element inside clip bounds.,"product-showcase, luxury-branding, asymmetrical-alignment, saas-conversion",Specialized product division overviews, premium e-commerce main frames, feature blocks.
B2B-72,B2B Corporate & Fintech Overviews,Structured Matte Conversion Container,High-impact conversion portal nesting a physical device container box inside an oversized matte black card banner layer.,Solid pristine off-white sheet canvas layer #FFFFFF. Conversion card matte black container radius 24px.,Card subtitle headline text 28px white. Description copy lines text 14px.,Capsule hover entries over the black block card execute immediate container elevation changes via drop shadow changes.,"capsule-conversion-banner, matte-black-card, luxury-product-showcase, cta",Primary closing conversion modules, enterprise landing product overviews, catalog frames.
B2B-73,B2B Corporate & Fintech Overviews,Balanced Multi-Column Industry Portals,Symmetrical B2B capabilities block balancing a left-heavy brand logo with a vertical resource link directory.,Clean white sheet layout canvas backdrop layer #FFFFFF.,Left title display text 42px bold. Directory column headers text 16px.,Directory link anchors execute immediate font color weight conversion from dark gray to solid white text lines on hover.,"industry-vertical-grid, directory-menu-list, b2b-minimalist, clean-alignment",Industry vertical deep-dives, corporate service overviews, custom software use-cases.
B2B-74,B2B Corporate & Fintech Overviews,Asymmetrical Typographic Conversion Ribbon,High-impact brutalist portal stacking a top text block over a star review container on light periwinkle gradient layers.,Light gray to periwinkle soft gradient canvas base sheet layout canvas layer. Inset card block.,Brutalist background text 52px uppercase. Inset form container placeholder typography text.,Viewport entry visibility prompts the main layout text rows to slide horizontally onto the screen via an automated sweep.,"ribbon-banner, brutalist-typography-cta, star-rating-badge, minimalist",Bottom-of-page closure ribbons, portfolio base rows, lead capture endfolds.
B2B-75,B2B Corporate & Fintech Overviews,Multi-Pane Descriptive Product Catalog,Product catalog dashboard coordinating a vertical drop-down list matrix left with active white thumbnail filters right.,Pristine uniform white canvas backdrop layer #FFFFFF. Drop-down accordion frames dark.,Plan title heading text 24px bold black. Description copy lines text 14px regular.,Drop-down list toggle events trigger height layout shifts from 0 to 1fr via smooth max-height interpolation curves.,"product-catalog-dashboard, drop-down-accordion, thumbnail-filters, clean",Flagship e-commerce product overviews, software specifications, upgrades sheets.
B2B-76,B2B Corporate & Fintech Overviews,Split-Circle Abstract Macro Grid,Brutalist features summary matrix tracking two intersecting circle wireframe nodes filled with macro product assets.,Solid clean white canvas configuration field. Left circle area black background fill box.,Left circle text 18px white text. Right circle sub-header text layers 22px bold black text rows.,Background capsule and supplement bottle graphics execute scroll-driven parallax translation offsets relative to center axes.,"brutalist-split, product-handheld-asset, high-contrast-editorial, circles",Core company value propositions lists, natural product advantage matrices, features sheets.
B2B-77,B2B Corporate & Fintech Overviews,Unified Dual-Pane Application Catalog,High-key product catalog hero cascading a stack of white software inputs inside an absolute centered tablet mockup.,Pristine uniform off-white layout canvas layer overlaid with an engineering layout grid line matrix.,Extra-large headline text 54px bold white text layers. Input form width constraint 440px.,Page scroll sequences trigger multi-layered parallax float speed interpolation across overlapping widget deck frames on load.,"tablet-mockup-dashboard, overlapping-widgets, high-key-product-catalog, saas",Principal landing heroes for medical tools, e-commerce catalog main frames, product features.
B2B-78,B2B Corporate & Fintech Overviews,Kinetic Micro-Badge Brand Statement,Minimalist capability statement module tracking large regular gray text strings overlaid with highlighted icon badges.,Light gray to periwinkle soft gradient canvas base text layout line. Micro-badges capsule indicators.,Main display typography block 38px medium-light gray. Highlight phrase text regular.,Hovering individual coordinates over highlighted badge text triggers an immediate typography font weight shift and active logo.,"kinetic-typography, inline-micro-badges, vector-utility-glyphs, statement",Company core mission statements, agency capability overviews, feature summary blocks.
B2B-79,B2B Corporate & Fintech Overviews,Asymmetrical Circular Product Slider,Symmetrical platform overview aligning five vertical oval bento cards below a top horizontal navigation group.,Solid clean off-white canvas layout field paneling with zero lines or gradients. Oval card borders radius.,Section title heading text 42px bold. Card subtitle headers 20px bold text layers.,Slotted interaction triggers translate the carousel track on X-axis while smoothly expanding shadows of active focus cards.,"oval-bento-cards, horizontal-carousel, supplement-assets, social-proof",Educational category overviews, e-commerce division matrices, classification overviews.
B2B-80,B2B Corporate & Fintech Overviews,B2B Multi-Client Proof Grid,Pristine 2-row partner logo directory table designing corporate authority across structured white row lines.,Pristine uniform white canvas base. No layout gradients or lighting textures.,Module sub-header line text index copy box headers text 16px. Grayscale logos center.,Brand grid cell coordinates trigger immediate logo flash color property shift from grayscale to high-contrast corporate.,"wireline-grid-dividers, grayscale-logos, corporate-proof-baseline, symmetrical",Mid-page corporate trust banners, client partner marquees lists, enterprise logo rolls.
B2B-81,B2B Corporate & Fintech Overviews,Wide Gradient Tech Directory Footer,Clean corporate directory footer closure layout focusing an email capture row and a large left-heavy brand logo mark.,Deep dark slate charcoal page canvas field. Low-contrast script typography design watermark 'VOXA'.,Upper row capture headline text 42px white. Directory menu link filters spacing 24px.,Directory menu link anchors execute immediate font color weight conversion from dark gray to solid white text lines on hover.,"minimalist-footer, giant-watermark-base, email-capture-form, horizontal",Flagship corporate footers, closure conversion landing fields, contact directory panels.
B2B-82,B2B Corporate & Fintech Overviews,Giant Chroma Wordmark Transition Banner,Ultra-minimalist branding transition banner designing giant gradient text block logos beside vertical resource link lists.,Solid deep dark slate charcoal horizontal strip ribbon background field. Diamond card icon mark.,Ribbon headline text 42px white. Sub-footer legal utility anchors spacing 16px.,Gradient text block logo performs an automated horizontal entry slide translation onto the stage track on load visibility.,"ribbon-banner, gradient-typography-logo, brutalist-text-cta, sub-footer",Bottom-of-page closure ribbons, agency portfolio base rows, creative transitions.
B2B-83,B2B Corporate & Fintech Overviews,Fine-Art Overlapping Canvas Hero,Editorial fine-art hero section layering raw canvas-filling background imagery behind three stacked painting frames.,Full-bleed background layout displaying a photorealistic oil painting of deep red and white roses.,Backdrop typography text 82px bold neon yellow. Classical museum artifact cells text 16px.,Oil painting background layer moves on a slow subtle scroll parallax interpolation while cards execute offsets on hover.,"fine-art-hero, overlapping-canvases, brutalist-yellow-type, baroque",Main heroes for art galleries, exhibition collection launches, portfolios.
B2B-84,B2B Corporate & Fintech Overviews,Full-Bleed Nature Retreat Hero (Var),Immersive eco-tourism hero section tracking an open navigation header above a modern A-frame glass cottage lake scene.,Full-bleed photographic background showcasing a luxury modern A-frame glass cottage along a lake reflect pool.,Main display headline 64px white sans-serif text. Description copy regular weight text layouts.,Lake reflection water area incorporates a subtle fluid simulation loop to replicate soft active water ripples continuously.,"full-bleed-nature, luxury-retreat, forest-cabin, centered-conversion",Flagship heroes for boutique hotels, nature retreats, architectural experience landings.
B2B-85,B2B Corporate & Fintech Overviews,Split Symmetrical Architecture Slider,Symmetrical real estate overview section distributing landscape cottage cards complete with property photo frames.,Solid clean off-white canvas layout backdrop canvas field with zero lines or gradients. White cards panels.,Split headline text 42px bold. Property data line specifications text layers 15px.,Slide controls shift the horizontal card rows smoothly along X-axis while cross-fading property metrics lines on click.,"property-slider, landscape-media-cards, symmetrical-alignment, travel",Vacation rental catalogs, real estate asset overviews, property listings.
B2B-86,B2B Corporate & Fintech Overviews,Blurred Instagram Grid Marquee (Var),Editorial social proof feed row mapping horizontal portrait photo cards above a heavily blurred forest panoramic backdrop.,Full-bleed background layout displaying a photorealistic heavily blurred panoramic texture pool.,Module title text 36px bold. Polaroid card account tag text layers 14px lowercase.,Polaroid card wrappers text lines translate vertically translateY(-8px) while shifting from muted to high-contrast colors.,"social-proof-feed, polaroid-cards, blurred-nature-backdrop, lifestyle",Mid-page social proof ribbons, Instagram integration feeds, culture walls.
B2B-87,B2B Corporate & Fintech Overviews,Asymmetrical Gallery Matrix (Var),Advanced information-dense amenities block pairing an extra-large text block left with three multi-scale layout cells right.,Pristine uniform off-white layout canvas layer with zero lines or gradients. Multi-scale cards.,Left title headline text 44px bold. Capsule button text layers 16px copper.,Move gestures across coordinates trigger independent horizontal and vertical translation float offsets across image cells.,"asymmetrical-gallery, multi-scale-cards, luxury-lifestyle, retreat",Boutique hotel amenities showcases, asset catalog overviews, experience designs.
B2B-88,B2B Corporate & Fintech Overviews,Vertical Index Property Switcher (Var),Advanced real estate switcher module balancing vertical text list options left with a large property showcase frame right.,Solid clean off-white canvas layout background layer. Showcase frame landscape portrait.,Main title display text 42px uppercase. Property details progress text layers regular weight.,Toggling vertical index text links instantly clears right-hand media pane and fades incoming property photo asset via sweep.,"vertical-index-switcher, property-showcase-frame, architectural-bento, clean",Vacation rental catalogs, real estate asset overviews, directory switchers.
B2B-89,B2B Corporate & Fintech Overviews,Property Recommendation Deck Split (Var),Structured conversion module splitting a giant uppercase headline above a horizontal row of two property cards.,Solid pristine off-white canvas layout background layer. Photo cards full portrait frames.,Section title heading text 44px uppercase. Property details text layers regular font weights.,Hover actions over individual horizontal card containers prompt a subtle container elevation change via drop shadow manipulation.,"recommendation-deck, landscape-property-cards, symmetrical-alignment, travel",Product recommendation sliders, cross-selling real estate blocks, catalogs.
B2B-90,B2B Corporate & Fintech Overviews,Immersive Dark Interior Hero (Var),Luxury hospitality hero overlaying a brutalist fireplace text headline onto a full-bleed dark concrete living lounge scene.,Full-bleed photographic background displaying an industrial dark concrete interior lounge fireplace setup.,Fireplace text headline 88px uppercase tracking. Booking scheduler text layers regular weight.,Fireplace mantle area incorporates a highly realistic particle lighting mesh simulation to replicate live flickering flame.,"dark-interior-hero, brutalist-text-overlay, booking-scheduler-baseline, luxury",Principal landing heroes for luxury boutique hotels, luxury villa bookings.
B2B-91,B2B Corporate & Fintech Overviews,Close-Up Culinary Feature Block,Editorial 2-column feature block section pairing culinary plate closeups right with an asymmetrical text summary block left.,Pristine uniform off-white sheet layout canvas layer. Culinary plate closeups portrait frame.,Left title main text 42px uppercase bold text rows. Baseline description copy regular weight.,Inset viewport visibility prompts the handheld chopstick graphic to translate smoothly downwards along the Y-axis onto plate.,"split-media-layout, culinary-closeup, gourmet-branding, clean-corporate",Luxury dining overviews, resort amenities breakdowns, gourmet catalog main frames.
B2B-92,B2B Corporate & Fintech Overviews,Deep Foggy-Forest Closure Banner,Corporate closure conversion footer component designing a capsule conversion card over panoramic misty forest tree lines.,Full-bleed photographic canvas displaying dense green pine valleys covered in thick rolling fog banks.,Banner main title text 54px uppercase dark. Description copy lines text 14px regular.,Panoramic forest background layer incorporates a slow automated horizontal keyframe opacity shimmer loop animation pattern.,"foggy-forest-canvas, panoramic-misty-valley, capsule-conversion-cta, closure",Eco-resort base closures, main closing conversion modules, travel closures.
B2B-93,B2B Corporate & Fintech Overviews,Editorial Property Description Stack (Var),Hospitality process layout splitting vertical text columns left and asymmetrical landscape photo gallery tracks right.,Solid clean off-white canvas layout background #FFFFFF. Gallery cards rounded 16px.,Upper headline text 48px uppercase. Column feature list check metrics.,Gallery row track entry coordinates translate horizontal card panels smoothly along X-axis while cross-fading inner photos.,"split-header-matrix, asymmetrical-gallery-slider, two-column-copy-block, travel",Main property specification walkthrough modules, real estate about-page blocks.
B2B-94,B2B Corporate & Fintech Overviews,Multi-Tabbed Category Amenity Grid (Var),Symmetrical capabilities grid row layout aligning four portrait photo panels below top horizontal filter links.,Solid clean off-white canvas layout backdrop canvas field background sheets #FFFFFF. Photo cards rounded.,Section title heading text 42px uppercase bold. Link filter text layers 20px regular weights.,Toggling separate filter menu headers instantly clears core grid panel and fades incoming amenity photo frames via curves.,"category-filter-bar, amenities-grid, symmetrical-alignment, b2b-corporate",Property amenities showcases, e-commerce catalog main frames, portfolio grids.
B2B-95,B2B Corporate & Fintech Overviews,Editorial Museum Exhibition Banner (Var),High-impact brutalist portal stacking a floating text card over a fanned horizontal marquee row of artwork cards.,Clean solid white background layer layout canvas. Artwork ribbon cards rounded 16px.,Marquee background text 82px bold. Exhibition card sub-caption text layers 14px regular weight.,Hover actions over narrow column strips smoothly expand horizontal layout width proportions while compressing adjacent fields.,"brutalist-text-marquee, overlapping-canvases, vertical-accordion-grid, history",Main heroes for art galleries, exhibition collection launches, timelines.
B2B-96,B2B Corporate & Fintech Overviews,Fine-Art Chronological Flagship Hero (Var),Immersive art museum hero section tracking an open navigation top-bar above a multi-layered cascade of portrait art frames.,Clean white sheet layout canvas backdrop layer. Portrait art cells feature index paths '01'.,Main display headline 64px bold, cursive text script logo overlay 'of' in rich coral tone.,Move gestures or page scroll sequences trigger independent horizontal and vertical translation float offsets across layers.,"fine-art-hero, cursive-typography-overlay, overlapping-media-cards, alignment",Principal landing heroes for art institutions, digital portfolio indices.
B2B-97,B2B Corporate & Fintech Overviews,Asymmetrical Property Experience Grid (Var),Advanced information-dense real estate features listing pairing an asymmetrical uppercase display title left with cards right,Solid pristine off-white canvas layout background layer. Photo cards horizontal card rows.,Section title heading text 42px uppercase. Property details text layers regular font weights.,Hover actions over individual gallery card containers prompt a subtle vertical translation lift alongside an active scale.,"asymmetrical-gallery-matrix, multi-scale-cards, luxury-lifestyle, onboarding",Boutique hotel amenities showcases, asset catalog overviews, experience designs.
B2B-98,B2B Corporate & Fintech Overviews,Wireframe Directory Matrix Footer (Var),Minimalist corporate footer layout managing text row marquee cells over a wireframe grid matrix track.,Pristine uniform white canvas base layer #FFFFFF bordered by gray vertical layout lines.,Module main heading text 42px bold. Cell index tag text layers 14px regular tracking fields.,Hover actions over individual directory anchors prompt an immediate typography color conversion from dark gray to black text.,"wireline-grid-dividers, minimal-directory, brutalist-text-marquee, sub-footer",Baseline corporate footers, agency conversion closure folds, contact layouts.
B2B-99,B2B Corporate & Fintech Overviews,Milestone Checklist Accordion Panel (Var),Educational 2-column feature walkthrough coordinating a vertical checklist timeline left with horizontal options right.,Solid clean off-white canvas layout field paneling with zero structural lines or gradients.,Two-row headline 38px uppercase bold. Active choice card features top absolute green badge.,Checklist circle nodes illuminate sequentially downwards along the vertical dashed tracking wireline track on view entry.,"milestone-checklist, horizontal-accordion-stack, overlapping-badge, travel",Property onboarding lists, tactical feature summary blocks, company charts.
B2B-100,B2B Corporate & Fintech Overviews,Advanced Booking Scheduler Stage (Var),Advanced user booking scheduler stage balancing interactive dropdown fields left with showcase photo frames center.,Pristine uniform off-white layout canvas layer #FFFFFF. Summary conversion card panel white text layers.,Step timeline progress title text 16px. Statistical numeric layout text 44px regular black.,Mouse click entries into individual form dropdown field lines toggle border stroke properties into dark-teal active states.,"booking-scheduler-stage, step-progression-baseline, horizontal-split-pane, checkout",User portal registration sign-on gates, client booking calendars gateways.
B2B-101,B2B Corporate & Fintech Overviews,Minimal Balanced Text Statement Block (Var),Typographic capability statement module featuring large regular gray text strings overlaid with copper accent text nodes.,Solid clean off-white canvas layout field paneling with zero structural lines or gradients.,Main display typography block 38px bold. Statement highlight phrase text layers bold regular.,Hovering individual cursor coordinates over the highlighted statement text triggers an immediate typography font weight shift.,"capabilities-statement, copper-accent-type, two-column-copy-block, clean",Company core mission statements, agency capability overviews, feature summary blocks.
B2B-102,B2B Corporate & Fintech Overviews,Advanced Booking Scheduler Stage (Var 2),Advanced user booking scheduler stage balancing vertical list options left with horizontal selection bento cards center.,Pristine uniform off-white layout canvas layer #FFFFFF. Summary conversion card panel white text layers.,Step timeline progress title text 16px. Statistical numeric layout text 44px regular black.,Hovering over individual horizontal resource cards smoothly elevates the target container wrapper and expands drop shadow.,"booking-scheduler-stage, step-progression-baseline, bento-cards-stack, fintech",Technical marketing documentation indices, product guide libraries, client booking calendars.
B2B-103,B2B Corporate & Fintech Overviews,Minimalist Split-Pane Core Metrics Row,Lightweight metrics section row layout tracking three oversized copper data numbers below left vertical title stacks.,Solid pristine off-white canvas layout backdrop canvas field background sheets #F9F9F9.,Section title headline 42px bold. Card statistical values text 54px regular tracking.,Baseline odometer counters execute automated staggered entry animations, sliding upwards into row layout with a smooth curve.,"metrics-panel-row, copper-accent-type, symmetrical-alignment, social-proof",Core platform success statistics, travel booking summaries, company scale indicators.
B2B-104,B2B Corporate & Fintech Overviews,Dual-Month Interactive Booking Calendar,Advanced real estate switcher module balancing vertical text list options left with a large property showcase frame right.,Solid clean off-white canvas layout background layer. Showcase frame landscape portrait.,Main title display text 42px uppercase. Property details progress text layers regular weight.,Toggling vertical index text links instantly clears right-hand media pane and fades incoming property photo asset via sweep.,"vertical-index-switcher, property-showcase-frame, architectural-bento, clean",Vacation rental catalogs, real estate asset overviews, directory switchers.
B2B-105,B2B Corporate & Fintech Overviews,Asymmetrical Info-Card Gallery Matrix,Asymmetrical 2-column feature split coordinating vertical bento cards with a landscape lifestyle photography frame right.,Solid clean off-white canvas layout backdrop canvas field background textures. Bento cards white box.,Section title main text 42px uppercase bold. Card subtitle headers 22px bold text layers.,Hover actions over individual horizontal text cards smoothly elevate the target container wrapper and expand drop shadows.,"asymmetrical-gallery-matrix, multi-scale-cards, lifestyle-photography, clean",Corporate policy deep-dives, regulatory phase checklists, product guide libraries.
B2B-106,B2B Corporate & Fintech Overviews,Deep Misty-Forest Directory Footer,Corporate directory footer layout managing text row marquee cells over an engineering coordinate backdrop.,Solid deep charcoal black horizontal strip ribbon footer layer. Deep green pine valley tree lines.,Main headline 64px white, directory column link headers bold white text 16px. Sub-link grey.,Directory link anchors execute immediate font color weight conversion from dark gray to solid white text lines on hover.,"misty-forest-footer, panoramic-valley-backdrop, directory-link-grid, utility",Eco-resort base cookies, main closing conversion modules, legal directory baselines.
B2B-107,B2B Corporate & Fintech Overviews,Full-Width Centered FAQ Accordion,Constrained central FAQ interface designing text accordion rows over an engineering coordinate backdrop.,Solid clean off-white canvas layout backdrop canvas field with zero structural lines or gradients.,Section main heading text 44px bold uppercase text. Accordion question row titles text 20px.,Accordion expansion row toggle events trigger height layout shifts from 0 to 1fr via smooth max-height interpolation.,"accordion-stack-faq, horizontal-rows, clean-alignment, travel-conversion",FAQ panels, core product feature specifications documentation blocks, tutorial sheets.
B2B-108,B2B Corporate & Fintech Overviews,Minimal Product Landing Hero (NEURA),Smart ring hero section centering an extra-large 3D ring asset inside a giant background wordmark backdrop.,Crisp white canvas sheet backdrop layer. Left and right margins anchor low-contrast rock cliff textures.,Background typography text 140px condensed. Main title text 56px white text layers.,Central smart ring asset executes an automated continuous keyframe floating layout translation and center axial rotation.,"3d-hardware-render, smart-ring-asset, watermark-backdrop, fintech-metric",Flagship luxury product heroes, premium consumer tech landing overviews, e-commerce.
B2B-109,B2B Corporate & Fintech Overviews,Macro Multi-Scale Hardware Bento Matrix,Clinical capabilities grid row aligning five vertical rectangle cards filled with pastel panels and 3D objects.,Solid clean off-white canvas layout backdrop canvas field background sheets #FFFFFF. Macro focus paths.,Main title heading text 42px bold black. Card subtitle headers 20px. Action capsule button.,Hover vectors over card modules trigger an asymmetrical vertical translation lift translateY(-8px) and interior photo scale.,"division-grid, pastel-cards, 3d-geometric-objects, staggered-alignment",Educational category overviews, e-commerce division matrices, portfolio classification selectors.
B2B-110,B2B Corporate & Fintech Overviews,Technical Cross-Section Dashboard Block,Advanced product presentation layout module matching a top horizontal data matrix with an extra-large 3D ring asset.,Pristine uniform off-width canvas layout sheet bordered by sharp horizontal dividing lines.,Column data list text headers text 16px. Callout window text layers 22px bold white text rows.,Viewport ring asset intersection visibility prompts numerical values inside tags to execute a rapid digital odometer count.,"cross-section-dashboard, floating-metric-tags, smart-ring-specs, data",Technical marketing documentation indices, product guide libraries, features walkthroughs.
B2B-111,B2B Corporate & Fintech Overviews,3D Exploded-View Component Assembly Hero,Technology landing hero centering an exploded-view component assembly mapping out hardware layers across wire points.,Clean, solid white background layer layout canvas #FFFFFF. Component files absolute landscape.,Main section heading text 44px centered. Component list labels text 16px regular weight.,Move gestures or page scroll sequences trigger an automated continuous horizontal expansion transition across component files.,"exploded-view-assembly, 3d-component-cascade, hardware-blueprint, hero",Flagship hardware product heroes, engineering component walkthrough overviews.
```

---

## 7 Concept Gallery

*Source: `landing-page-craft/references/concept-gallery.md`*


A growing catalogue of specific signature-visual-concept *instances* — not the generative method (that's `signature-moves.md`), and not the abstract metaphor families (that's the table in `signature-moves.md` step 2). This is the concrete inventory: real concepts that have actually been built, so a new project can be checked against what already exists before inventing something that turns out to be a repeat.

Check this before Step 2 of the signature-move framework. Add to it after every build, real or test — anything used counts, whether it was invented fresh or pulled from here.

**Never delete an entry.** Retire it instead (see Status below) so the history stays honest.

---

### How to add an entry

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

### Hero concepts

#### Convergence — scattered elements collecting into order
- **Core idea:** disorder becoming order, on command
- **Physical metaphor:** particles/objects literally moving toward a point and assembling
- **Trigger:** ambient, with a scroll- or load-triggered convergence moment
- **Seen in:** TrashPay — hero (scattered waste collecting)
- **Status:** active
- **Image:** none yet
- **Notes:** works because the *form* of the scattered elements matters — waste-shaped fragments, not generic dots. Reuse only if the product has a real "mess becomes order" story.

#### Woven lattice with traveling light
- **Core idea:** an intelligent, continuously active material
- **Physical metaphor:** a woven thread lattice as page background, with light pulses traveling along threads
- **Trigger:** ambient, looping
- **Seen in:** Weft (test build) — hero
- **Status:** active

#### Full-bleed overlay with floating nav pill
- **Core idea:** premium and immediately credible, people-first
- **Physical metaphor:** a full-bleed photo, a rounded floating navbar pill sitting on top of the image, headline overlaid in the lower third in mixed serif/italic accent type, a pill CTA with a small circular icon, one or two floating corner cards surfacing a secondary offer or credential
- **Trigger:** ambient photo, scroll-triggered fade-up for the overlaid text and cards
- **Seen in:** reference example for the mini-business landing page type (provided screenshot, "OPTIMO")
- **Status:** active
- **Image:** none yet
- **Notes:** floating corner cards are doing real trust-signal work here, not just decoration — keep them tied to a real credential or offer, not filler.

#### Full-bleed atmospheric photo hero
- **Core idea:** mood and craft, told through a single strong image
- **Physical metaphor:** one full-bleed photo with a dark tonal overlay for legibility, a large serif headline anchored to one upper corner, subtitle and a single solid-accent CTA anchored below it, transparent navbar directly on the image
- **Trigger:** ambient photo, scroll-triggered fade-up for the text block
- **Seen in:** reference example for the mini-business landing page type (provided screenshot, "Restro")
- **Status:** active
- **Image:** none yet

#### Circled-keyword hero with frosted stat card
- **Core idea:** one idea in the headline made literally impossible to miss, backed by a real number
- **Physical metaphor:** a photo hero where one keyword gets a circled/pill-outlined accent treatment, an eyebrow label plus one-line blurb, a CTA, and a floating frosted/glass stat card overlapping the photo, with a client-logo strip directly beneath the hero
- **Trigger:** interaction/ambient photo, scroll-triggered reveal for the stat card and logo strip
- **Seen in:** reference example for the mini-business landing page type (provided screenshot, "Busininity")
- **Status:** active
- **Image:** none yet
- **Notes:** the client-logo strip immediately under the hero is doing as much trust-building work as the stat card — don't drop it when adapting this pattern.

#### Split image/text hero with trust cluster
- **Core idea:** calm confidence — let the work speak, prove it's already trusted
- **Physical metaphor:** a two-column hero, a real photo filling one side edge-to-edge, the other side calm negative space holding the logo, a small avatar-cluster trust indicator ("50+ founders trust us"), and a bold headline anchored to the bottom of the text column
- **Trigger:** ambient photo, scroll-triggered reveal for headline and trust cluster
- **Seen in:** reference example for the mini-business landing page type (provided screenshot, "Norvex")
- **Status:** active
- **Image:** none yet

#### Text-first hero into arched photo reveal
- **Core idea:** state the value plainly first, then let the image confirm it
- **Physical metaphor:** a type-only opening block (eyebrow label, headline with one accent-colored keyword, short paragraph, CTA), immediately followed by a full-width photo masked with a soft arch/curve cutout at its top edge and a centered "scroll down" indicator
- **Trigger:** scroll-triggered reveal into the arched photo section
- **Seen in:** reference example for the mini-business landing page type (provided screenshot, "Clientix")
- **Status:** active
- **Image:** none yet
- **Image:** none yet
- **Notes:** graded as the strongest section of that build by a clear margin. Only reuse for a product with a genuine textile/weave/network conceit — otherwise it's borrowed rather than earned.

---

### Section / content concepts

#### Speaker Wheel — orbital showcase
- **Core idea:** a community of real people orbiting the thing
- **Physical metaphor:** satellites/avatars arranged in a ring, selectable
- **Trigger:** interaction-triggered (click/hover to bring one to the front)
- **Seen in:** FlutterBytes — speaker showcase
- **Status:** active
- **Image:** none yet
- **Notes:** strong alternative to a flat speaker grid for any "showcase of people" section.

#### Materials card — opens to reveal depth on hover
- **Core idea:** there's more value here than the surface shows
- **Physical metaphor:** a card that physically extends/unfolds on hover to reveal more
- **Trigger:** interaction-triggered (hover)
- **Seen in:** TrashPay — materials section
- **Status:** active
- **Image:** none yet

#### Rotating light border
- **Core idea:** an active, live, continuously-protected process
- **Physical metaphor:** a conic-gradient border that rotates around a card, like light traveling a track
- **Trigger:** ambient, looping
- **Seen in:** Allowance — How It Works cards
- **Status:** active
- **Image:** none yet

#### Hub-and-spoke diagram
- **Core idea:** one thing connects to many, without needing to switch between them
- **Physical metaphor:** a central node with lines radiating to satellite nodes
- **Trigger:** ambient or scroll-triggered draw-in
- **Seen in:** didii — "no switching required"; also FlutterBytes' bank/commit-graph variant
- **Status:** active — used twice already; treat as due for a rest on the next build unless the product's story is unusually well-suited to it
- **Image:** none yet

#### Before/after paired cards
- **Core idea:** the concrete old pain next to the concrete new resolution, per use case
- **Physical metaphor:** two-state card pair, explicit labels, one per scenario
- **Trigger:** scroll-triggered reveal, or click-to-toggle between states
- **Seen in:** didii — "Before Didii / With Didii"
- **Status:** active
- **Image:** none yet

#### Branching result cards
- **Core idea:** one input personalizes into several distinct outputs
- **Physical metaphor:** a single card visually branching into multiple result cards, connected by traveling dots
- **Trigger:** scroll-triggered
- **Seen in:** Flare (test build) — How It Works
- **Status:** active — liked in principle, flagged as under-executed visually. Worth retrying with a stronger, more literal branch/fork visual before reusing as-is.
- **Image:** none yet

#### Regenerating template grid
- **Core idea:** the same system produces endless distinct outputs
- **Physical metaphor:** a grid of near-identical cards, one periodically regenerating its content
- **Trigger:** ambient, looping
- **Seen in:** Flare (test build) — hero
- **Status:** retired for hero use — competed with a separate headline effect on the same hero and diluted both (see build-log.md). Could work as a *section* concept instead of a hero concept, on its own with a quiet headline.
- **Image:** none yet

---

### Retired / cooling-down concepts

Concepts that have been used enough times recently that they should sit out a build or two, tracked here so it's a quick glance instead of re-reading every build-log entry:

- **Traveling dot/pulse along a path** — used on both test builds so far (Weft, Flare) as the default animation primitive. Not retired as an idea, but explicitly flagged in `build-log.md` to avoid defaulting to it a third time. Try a line-draw reveal or an expand/contract shape instead.
- **Hub-and-spoke diagram** — used twice (didii, FlutterBytes). See above.

---

### Typeface library

A separate, growing list of distinctive display/body typefaces — used ones and untested candidates — lives in `references/typeface-library.md`. Check it during the type-and-color step alongside this file.

---

## 8 Typeface Library

*Source: `landing-page-craft/references/typeface-library.md`*


A growing list of distinctive typefaces to draw from during the type-and-color step in `SKILL.md`, so the three candidates proposed to the person are never a cold guess. Check this before proposing candidates. It is not a menu to pick from mechanically — the rule in `SKILL.md` still applies: propose three distinctive, non-obvious candidates and actually render the product's name in each one.

**Never delete an entry.** Retire it instead once it's been used enough recently that it needs a rest (mirrors the concept gallery's retirement rule) — a typeface can come off the retired list once enough builds have passed.

The agent may also propose a genuinely new typeface not yet in this list — that's expected and encouraged, not a deviation from the process. If the person picks it, add it here afterward so it's available next time.

---

### How to add an entry

```md
### [Typeface name] — [category]
- **Mood / character:** what it feels like, in a phrase
- **Pairs well with:** other typefaces from this list, or "untested"
- **Used in:** project — role (display / labels / body), or "candidate, not yet used"
- **Status:** active / retired (reason)
```

---

### Display typefaces

#### Instrument Serif — modern display serif
- **Mood / character:** editorial, confident, a little literary — high-contrast strokes without feeling stuffy
- **Pairs well with:** IBM Plex Mono, Karla
- **Used in:** Weft (test build) — display
- **Status:** active

#### Bricolage Grotesque — expressive grotesque
- **Mood / character:** playful but structured; irregular details keep a sans from reading generic
- **Pairs well with:** Space Mono, Manrope
- **Used in:** Flare (test build) — display
- **Status:** active

---

### Label / data / mono typefaces

#### IBM Plex Mono — technical monospace
- **Mood / character:** precise, systems-oriented, good for data labels and small caps
- **Pairs well with:** Instrument Serif, Karla
- **Used in:** Weft (test build) — data labels
- **Status:** active

#### Space Mono — quirky monospace
- **Mood / character:** slightly retro-futurist, more personality than a pure technical mono
- **Pairs well with:** Bricolage Grotesque, Manrope
- **Used in:** Flare (test build) — labels
- **Status:** active

---

### Body typefaces

#### Karla — humanist grotesque
- **Mood / character:** warm, easy, unremarkable in the best way — doesn't compete with a loud display face
- **Pairs well with:** Instrument Serif, IBM Plex Mono
- **Used in:** Weft (test build) — body
- **Status:** active

#### Manrope — geometric grotesque
- **Mood / character:** clean, contemporary, slightly cooler than Karla
- **Pairs well with:** Bricolage Grotesque, Space Mono
- **Used in:** Flare (test build) — body
- **Status:** active

---

### Candidates — not yet used, worth proposing

Add typefaces here as they're discovered or suggested, before they've ever been chosen on a real build. Once one gets picked, move it up into the appropriate section above with its "Used in" filled in.

*(empty — first candidates get added after the next build or the next time the agent proposes something new)*

---

### Retired / cooling down

*(empty so far — a typeface moves here once it's shown up on two or three consecutive builds, mirroring the concept gallery's rule)*

---

## 9 Grading Rubric

*Source: `landing-page-craft/references/grading-rubric.md`*


A structured scorecard for a *finished* build — this runs after the page exists, on the real render (live preview, deployed URL, or screenshots), as distinct from the concept-grading in `SKILL.md` step 5, which runs before any code is written. Where step 5 grades concepts on paper, this grades the actual result.

### How grading works here

1. **Claude drafts first.** After a build (real or test) is finished and viewable, Claude fills out the scorecard below honestly, against the real render — not against its memory of what it intended to build. Lean skeptical: a pass needs a concrete reason, not the absence of an obvious problem.
2. **The person corrects it.** Claude's draft is a first pass, not the record. Go line by line and override anything that reads wrong — taste calls are the actual point of this exercise, and the person's correction is more authoritative than Claude's draft by design.
3. **The corrected version is what gets logged.** Once corrected, append the final scorecard to that build's entry in `references/build-log.md`, plus a short "carry-forward actions" list — the two or three most important things the next build should do differently. Also update `references/concept-gallery.md` and `references/typeface-library.md` with anything new that showed up, and mark anything that should now be retired from overuse.

Do this for every build, not just the ones that felt shaky — a build that seemed to go well can still surface something worth carrying forward, and a consistent record only works if it's consistent.

---

### Scorecard

Copy this block into the build's entry in `build-log.md` and fill it in. Use **Pass / Fail / Partial** plus one concrete sentence of evidence per line — not a number score. A line with no evidence sentence isn't graded yet.

```md
### Grade — [project name], [date]

**Hero**
- [ ] Built around exactly one signature idea, everything else quiet by comparison — evidence:

**Per-section concept quality** (repeat per section, or summarize if uniform)
- [ ] Concept visibly traces back to the page's one core idea, not just its own feature in isolation — evidence:
- [ ] Passes the two-second stranger test with no caption — evidence:
- [ ] Not a repeat of a signature move already used elsewhere on this page, or on the last logged build — evidence:

**Two-column sections**
- [ ] Every non-text side is genuinely alive — an animated mini-interface, screen snippet, or self-contained concept, not a flat image or static decoration — evidence:

**Cards and containers**
- [ ] No default plain bordered-card grid where a divider or more considered container would serve better — evidence:
- [ ] The whole page uses cards in at most one or two sections, not as the default container everywhere — evidence:
- [ ] Every card that is used has a customization touch (glossy gradient fill, glass-like border, animated icon) AND a real hover interaction — evidence:

**Icons**
- [ ] All icons come from one chosen custom library (Lucide/Phosphor/Heroicons/Tabler), consistent throughout — evidence:
- [ ] No emojis used where an icon belongs — evidence:

**Motion**
- [ ] Every section has some animation or interaction, including body copy animating in, not just appearing — evidence:
- [ ] Big numbers animate in rather than render static — evidence:
- [ ] No single animation primitive (e.g. traveling dot) repeated across the whole page — evidence:

**Type and headlines**
- [ ] Display type is memorable and specific, not a system/default face — evidence:
- [ ] One deliberate headline mechanism, applied consistently everywhere a major headline appears — evidence:
- [ ] Titles are short and subtitles concise, not full-sentence template filler — evidence:
- [ ] Two-part titles split across two lines sensibly (no orphaned single word, no forced split on a short title) — evidence:
- [ ] Any unavoidably long title de-emphasizes its tail at a smaller-but-still-obvious size rather than one flat wall of large text — N/A if no long title — evidence:

**Layout and theme**
- [ ] Top navbar stays visible while scrolling with a ~80% translucent, background-blurred fill — N/A if the brief opted out — evidence:
- [ ] Theme (light vs dark) was chosen to suit the brand, not defaulted to dark — evidence:
- [ ] Section backgrounds vary (near-white/near-black steps or subtle gradients), not one flat background top to bottom — evidence:
- [ ] One coherent style direction across the page (per `section-bank.md` families), not a split personality of mood families — evidence:

**Section bank usage**
- [ ] Bank rows that influenced sections were adapted (project's own palette, type scale, copy, imagery), not transplanted with the row's stock colors and specs — N/A if no rows used — evidence:
- [ ] Rows used are logged in the build-log entry and aren't repeats from the last build's `Bank rows used:` line — N/A if no rows used — evidence:

**Process**
- [ ] Type and color were actually checked in with the person before being finalized, not decided alone — evidence:
- [ ] Spacing between sections feels generous (~1.75x), sections don't feel adjacent to neighbors — evidence:
- [ ] Side padding sits around 4–8% of viewport width (4% most sections), responsive not fixed-pixel — evidence:
- [ ] Copy sounds like this brand specifically, not a generic template voice — evidence:
- [ ] Copy names no competitor brands, direct or indirect (unless explicitly asked for) — evidence:
- [ ] The person was asked for concepts/visuals they'd want to include, especially for the hero, before one was invented — evidence:
- [ ] Any form is branded in the site's own design and submits to a Google Form via pre-fill link (or is clearly stubbed pending the link) — N/A if no form — evidence:
- [ ] If this is a business page: ~75% of sections are built around real photography, not abstract vector concepts — N/A otherwise — evidence:
- [ ] If this is a European website: hero uses downloaded real photography (Unsplash/Pexels/Pixabay or supplied) in a ~98%-width rounded frame (20–32px radius), kept simple with no busy overlay, no waitlist — N/A otherwise — evidence:
- [ ] If this is a mini-business landing page: exactly four sections (hero, offering, proof, contact), a Contact Us section is present with both direct contact info and a branded form forwarding to a Google Form, the hero uses real/premium photography, and the proof section has real trust signals (stats, logos, certifications) rather than filler — N/A otherwise — evidence:
- [ ] If this is a mini-business landing page: the hero pattern isn't a repeat of the last mini-business build logged — check `references/concept-gallery.md` — N/A otherwise — evidence:

**Mobile and hardening** (skip hardening items for a quick test build not headed to production)
- [ ] Headlines and fixed-dimension containers hold up at small viewports — evidence:
- [ ] Light/dark tokens used correctly, if applicable — evidence:
- [ ] Visible keyboard focus states, not just hover — evidence:

**Overall verdict**
One paragraph, plain language: what's the strongest section, what's the weakest, would a stranger say this page has a real point of view?

**Carry-forward actions for the next build**
1.
2.
3.
```

---

### What "Fail" actually means here

A Fail on any hard-rule line (hero single-idea, two-column aliveness, per-section signature concept, animation-on-everything, non-system display type, non-plain headlines) is worth naming plainly rather than softening — these are the six rules `SKILL.md` calls non-negotiable, and a scorecard that never fails one of them across several builds is more likely under-grading than describing a run of perfect builds.

A **Partial** is for anything that technically satisfies the rule but not in its spirit — a hover interaction that's just a slight opacity change on a card, for instance, technically not "static" but not really doing anything either.

---

## 10 Build Log

*Source: `landing-page-craft/references/build-log.md`*


A running record of what's been used on past builds with this skill, so a new project can deliberately avoid repeating a recent one's section styles, signature concepts, or animation primitives — not just within a page, but across projects. Check this before starting a new build. Add an entry after finishing one, real or test.

Going forward, every new entry should end with the corrected scorecard from `references/grading-rubric.md` (Claude drafts it against the real render, the person corrects it) instead of just a prose verdict — the Weft and Flare entries below predate the rubric and keep their original prose-verdict format. Also cross-check `references/concept-gallery.md` and `references/typeface-library.md` when logging a new entry: log anything new there too, and retire anything that's now been used enough times to need a rest.

Each new entry should also record the project's **style direction** (the family chosen from `references/section-bank.md`) and a **`Bank rows used:`** line listing which section-bank IDs influenced which sections (e.g. `HERO-05 (adapted: hero), FAQ-04 (FAQ), B2B-13 (proof baseline)`), so the next build can avoid leaning on the same rows.

### Weft (test build) — intelligent clothing & sensors

- Type: Instrument Serif (display), IBM Plex Mono (data labels), Karla (body)
- Palette: espresso base, copper/bronze + mint duotone
- Hero signature: ambient woven thread lattice with traveling light pulses across the whole background; stitch-draw headline reveal
- Section signatures used: circular Sense/Think/Respond loop with a traveling pulse; scattered flat-lay product cards with tag-flip-on-hover; particles contained inside a clipped organic blob shape
- Layout archetypes used: mostly centered/stacked; one loose scattered flat-lay
- Animation primitive: traveling dot/pulse, used repeatedly across sections
- Verdict: the hero was the strongest section by a clear margin. Other sections read as decent illustrations of their own feature but didn't obviously connect to one shared idea, and needed explanation to land.

### Flare (test build) — AI event campaign template generator

- Type: Bricolage Grotesque (display), Space Mono (labels), Manrope (body)
- Palette: indigo-black base, coral/flare-orange primary with gold + cyan as "variety" accents
- Hero signature: a grid of near-identical template cards periodically regenerating one card's content, plus a separate color-echo headline effect
- Section signatures used: one template card branching into three personalized results with traveling dots; plain bordered cards for a feature grid and a gallery section; dot-row pricing tiers
- Layout archetypes used: mostly stacked/centered; plain card grids for two sections in a row
- Animation primitive: traveling dot/pulse again, used repeatedly, including in How It Works and the pricing dots
- Verdict: hero regressed relative to Weft — two competing loud ideas (the headline effect and the card grid) instead of one clear signature, diluting both. The gallery and feature sections leaned on plain bordered cards, flagged directly as bland. The branching concept in How It Works was liked in principle but under-executed visually.

### Notes for the next build

- Don't default to "traveling dot/pulse" again — it's been the primitive on both builds so far. Try a line-draw reveal, a shape that expands/contracts, or something not yet used.
- Don't default to a plain bordered-card grid for a feature or gallery section — try dividers, a scattered/staggered arrangement, or a genuinely different container.
- Hero: pick exactly one signature idea. If a headline treatment is doing real work, keep the surrounding visual concept quieter, and vice versa — don't run both at full volume.
- Neither test build so far has done the type/color check-in with the person before committing — worth doing on the next one now that it's part of the process.
- Neither test build has a formal graded scorecard — the next build should be the first to go through `references/grading-rubric.md` end to end.

---

## 11 Source Files

This document is a flattened, single-file export. The living skill — the version that actually gets edited, appended to, and loaded by Claude Code as a skill — is the multi-file structure below:

```
landing-page-craft/
  SKILL.md                        the skill itself: process, hard rules, when to use it
  references/
    signature-moves.md            the method for inventing a section's signature visual concept
    taste-rules.md                the standing checklist (layout archetypes, cards, spacing, etc.)
    site-types.md                 section inventories for product / case-study / event pages
    section-bank.md                how to use the section design bank + category index
    section-bank.csv               the bank: 194 described sections (layout, background, type, motion)
    concept-gallery.md             growing catalogue of specific visual concepts, with optional images
    typeface-library.md            growing list of typefaces, used and candidate
    grading-rubric.md              post-build scorecard: draft first, person corrects
    build-log.md                   what past builds used and how they graded
  assets/
    concepts/                      images/screenshots referenced from concept-gallery.md
```

| Section in this file | Original source |
|---|---|
| 2 The Skill and Process | `landing-page-craft/SKILL.md` |
| 3 The Signature Move Framework | `landing-page-craft/references/signature-moves.md` |
| 4 Standing Taste Rules | `landing-page-craft/references/taste-rules.md` |
| 5 Site Types | `landing-page-craft/references/site-types.md` |
| 6 Section Design Bank | `landing-page-craft/references/section-bank.md` + `section-bank.csv` |
| 7 Concept Gallery | `landing-page-craft/references/concept-gallery.md` |
| 8 Typeface Library | `landing-page-craft/references/typeface-library.md` |
| 9 Grading Rubric | `landing-page-craft/references/grading-rubric.md` |
| 10 Build Log | `landing-page-craft/references/build-log.md` |

**Keeping this current:** after finishing a real build, check whether anything genuinely new happened — a signature-move metaphor not yet logged, a pattern that belongs in the taste rules, a concept worth adding to the gallery, a typeface worth adding to the library, a section design worth appending to the bank, or a process step that needed adjusting. Propose the specific addition, with the concrete example it came from, grade the build against the rubric with the person's corrections, and record it in the build log regardless of how the build went. Make those edits in the multi-file source under `landing-page-craft/`, then regenerate this file from it — this skill, and this export, are only as good as what keeps getting fed back in.
