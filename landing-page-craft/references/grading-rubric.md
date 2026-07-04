# Grading Rubric

A structured scorecard for a *finished* build — this runs after the page exists, on the real render (live preview, deployed URL, or screenshots), as distinct from the concept-grading in `SKILL.md` step 5, which runs before any code is written. Where step 5 grades concepts on paper, this grades the actual result.

## How grading works here

1. **Claude drafts first.** After a build (real or test) is finished and viewable, Claude fills out the scorecard below honestly, against the real render — not against its memory of what it intended to build. Lean skeptical: a pass needs a concrete reason, not the absence of an obvious problem.
2. **The person corrects it.** Claude's draft is a first pass, not the record. Go line by line and override anything that reads wrong — taste calls are the actual point of this exercise, and the person's correction is more authoritative than Claude's draft by design.
3. **The corrected version is what gets logged.** Once corrected, append the final scorecard to that build's entry in `references/build-log.md`, plus a short "carry-forward actions" list — the two or three most important things the next build should do differently. Also update `references/concept-gallery.md` and `references/typeface-library.md` with anything new that showed up, and mark anything that should now be retired from overuse.

Do this for every build, not just the ones that felt shaky — a build that seemed to go well can still surface something worth carrying forward, and a consistent record only works if it's consistent.

---

## Scorecard

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
- [ ] Every non-text side is genuinely alive, not a flat image or static decoration — evidence:

**Cards and containers**
- [ ] No default plain bordered-card grid where a divider or more considered container would serve better — evidence:
- [ ] Every card-like container that is used has a real hover interaction — evidence:

**Motion**
- [ ] Every section has some animation or interaction, including body copy animating in, not just appearing — evidence:
- [ ] Big numbers animate in rather than render static — evidence:
- [ ] No single animation primitive (e.g. traveling dot) repeated across the whole page — evidence:

**Type and headlines**
- [ ] Display type is memorable and specific, not a system/default face — evidence:
- [ ] One deliberate headline mechanism, applied consistently everywhere a major headline appears — evidence:

**Process**
- [ ] Type and color were actually checked in with the person before being finalized, not decided alone — evidence:
- [ ] Spacing between sections feels generous (~1.75x), sections don't feel adjacent to neighbors — evidence:
- [ ] Copy sounds like this brand specifically, not a generic template voice — evidence:

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

## What "Fail" actually means here

A Fail on any hard-rule line (hero single-idea, two-column aliveness, per-section signature concept, animation-on-everything, non-system display type, non-plain headlines) is worth naming plainly rather than softening — these are the six rules `SKILL.md` calls non-negotiable, and a scorecard that never fails one of them across several builds is more likely under-grading than describing a run of perfect builds.

A **Partial** is for anything that technically satisfies the rule but not in its spirit — a hover interaction that's just a slight opacity change on a card, for instance, technically not "static" but not really doing anything either.
