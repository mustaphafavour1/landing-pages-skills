# Landing Page Craft — Skill

A Claude Code / Claude Agent skill for building landing pages, marketing sites, portfolio/case-study pages, and event pages with a genuine point of view — not generic template output. This repo is the dedicated home for developing and sharpening that skill over time.

## What's here

```
landing-page-craft/
  SKILL.md                        the skill itself: process, hard rules, when to use it
  references/
    signature-moves.md            the method for inventing a section's signature visual concept
    taste-rules.md                 the standing checklist (layout archetypes, cards, spacing, etc.)
    site-types.md                  section inventories for product / case-study / event pages
    concept-gallery.md             growing catalogue of specific visual concepts, with optional images
    typeface-library.md            growing list of typefaces, used and candidate
    grading-rubric.md              post-build scorecard: Claude drafts, you correct
    build-log.md                   what past builds used and how they graded
  assets/
    concepts/                      images/screenshots referenced from concept-gallery.md
```

## Using it

Point Claude Code at the `landing-page-craft/` folder as a skill (e.g. copy or symlink it into your skills directory, or reference this repo directly in a session that has it checked out). Once loaded, it activates automatically for landing-page and marketing-site work — see the `description` field in `SKILL.md` for the exact triggers.

## The two feedback loops this repo is built around

**1. The concept gallery (`references/concept-gallery.md`)**
Every signature visual concept that gets invented or reused — hero concepts and section concepts alike — gets logged here: what it is, the core idea it represents, the physical metaphor, where it's been used, and whether it's active or "cooling down" from overuse. Entries can be text-only or include an image in `assets/concepts/`. Check it before inventing a new concept; append to it after every build.

**2. Grading (`references/grading-rubric.md` + `references/build-log.md`)**
After a build is actually viewable — live preview, deployed link, or screenshots — Claude fills out the scorecard in `grading-rubric.md` against the real render, honestly and skeptically. You then go through it and correct anything that reads wrong; your correction is the actual record, not Claude's first pass. The corrected scorecard, plus a short list of carry-forward actions, gets appended to that build's entry in `build-log.md`, so the next build starts by reading what the last one got right and wrong.

There's also `references/typeface-library.md` for the same kind of running list, specific to typefaces — check it before proposing display type candidates, and add to it whenever a new typeface gets picked.

## Keeping it sharp

This skill is only as good as what gets fed back into it. After any real build:
1. Grade it (see above).
2. Log anything new in the concept gallery and typeface library; retire anything overused.
3. If a genuinely new pattern, rule, or process step showed up, propose adding it to `taste-rules.md`, `signature-moves.md`, or `SKILL.md` itself, with the concrete example it came from.
