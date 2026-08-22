# Build Log

A running record of what's been used on past builds with this skill, so a new project can deliberately avoid repeating a recent one's section styles, signature concepts, or animation primitives — not just within a page, but across projects. Check this before starting a new build. Add an entry after finishing one, real or test.

Going forward, every new entry should end with the corrected scorecard from `references/grading-rubric.md` (Claude drafts it against the real render, the person corrects it) instead of just a prose verdict — the Weft and Flare entries below predate the rubric and keep their original prose-verdict format. Also cross-check `references/concept-gallery.md` and `references/typeface-library.md` when logging a new entry: log anything new there too, and retire anything that's now been used enough times to need a rest.

Each new entry should also record the project's **style direction** (the family chosen from `references/section-bank.md`) and a **`Bank rows used:`** line listing which section-bank IDs influenced which sections (e.g. `HERO-05 (adapted: hero), FAQ-04 (FAQ), B2B-13 (proof baseline)`), so the next build can avoid leaning on the same rows.

## Weft (test build) — intelligent clothing & sensors

- Type: Instrument Serif (display), IBM Plex Mono (data labels), Karla (body)
- Palette: espresso base, copper/bronze + mint duotone
- Hero signature: ambient woven thread lattice with traveling light pulses across the whole background; stitch-draw headline reveal
- Section signatures used: circular Sense/Think/Respond loop with a traveling pulse; scattered flat-lay product cards with tag-flip-on-hover; particles contained inside a clipped organic blob shape
- Layout archetypes used: mostly centered/stacked; one loose scattered flat-lay
- Animation primitive: traveling dot/pulse, used repeatedly across sections
- Verdict: the hero was the strongest section by a clear margin. Other sections read as decent illustrations of their own feature but didn't obviously connect to one shared idea, and needed explanation to land.

## Flare (test build) — AI event campaign template generator

- Type: Bricolage Grotesque (display), Space Mono (labels), Manrope (body)
- Palette: indigo-black base, coral/flare-orange primary with gold + cyan as "variety" accents
- Hero signature: a grid of near-identical template cards periodically regenerating one card's content, plus a separate color-echo headline effect
- Section signatures used: one template card branching into three personalized results with traveling dots; plain bordered cards for a feature grid and a gallery section; dot-row pricing tiers
- Layout archetypes used: mostly stacked/centered; plain card grids for two sections in a row
- Animation primitive: traveling dot/pulse again, used repeatedly, including in How It Works and the pricing dots
- Verdict: hero regressed relative to Weft — two competing loud ideas (the headline effect and the card grid) instead of one clear signature, diluting both. The gallery and feature sections leaned on plain bordered cards, flagged directly as bland. The branching concept in How It Works was liked in principle but under-executed visually.

## HeadFavour — wearable charging cable bracelets

- Type: Fraunces (display), IBM Plex Mono (mono/labels), Manrope (body)
- Palette: near-black `ink` base with a `graphite` step-up surface, `bone` off-white text, and a gold/rose-gold/silver accent trio lifted directly from the product's three metal finishes (plus a matte white/steel 4th) — style direction: **Luxury / premium showcase**
- Site type: Product landing page (physical, made-to-order accessory), adapted — no real product photography was available as files, so the whole page is illustrated in original SVG/line-art rather than faked stock photography, per the skill's photo-unavailable fallback
- Hero signature: **Cord Unravel** (new concept, logged in `concept-gallery.md`) — a custom multi-strand SVG rig ambiently looping between a coiled wrist-loop bracelet and a straight full-length cable, behind a giant low-opacity mono wordmark watermark. Headline mechanism: bold assertive line + soft italic line, used on every major heading site-wide.
- Section signatures used: the Cord Unravel rig reused twice more with different triggers — interaction-triggered 4-step click-through in the disassembly walkthrough (spring-to-target, numbered waypoint timeline), and held-static per-finish in the catalog picker (crossfade + diagonal shimmer-sweep on swap, one-expanded-at-a-time). Icon-grid feature strip uses a shared hairline-divider grid instead of individual bordered cards. Matte gradient card holds the branded order form. Dark wireline-grid FAQ accordion.
- Layout archetypes used: centered stack (hero), title-left/concept-right (finishes), centered stack with a below-content step timeline (disassemble), text-left/form-right (reserve), centered stack (FAQ) — none repeated back-to-back
- Animation primitive: per-point SVG path lerp driven by one progress value — a new primitive, deliberately not another traveling-dot/pulse per the standing note below. Not reused elsewhere on the page: spring icon hover-tilt (value grid), diagonal shimmer-sweep + crossfade (finishes swap), accordion max-height (FAQ), looping opacity shimmer (footer wireline).
- Bank rows used: HERO-13 / B2B-56 (adapted: hero backdrop-wordmark + centered-asset), B2B-108 (adapted: hero giant-wordmark-behind-asset), B2B-67 (adapted: finishes active-tile catalog), B2B-110 (adapted: disassemble's spec-strip-under-asset), B2B-72 (adapted: reserve matte card), MIN-04 (adapted: disassemble step-timeline), SEC-03 (adapted: value-grid icon wells — swapped bordered cards for hairline dividers), FAQ-06 (adapted: dark wireline accordion), FT-05 (adapted: wireline footer). New row appended: B2B-112, describing the rig mechanic itself for future reuse.

### Grade — HeadFavour, 2026-08-22

Drafted by Claude against the real render (Playwright screenshots, desktop + mobile), not against intent. **Not yet corrected by Favour** — this is the first-pass draft the process calls for; his correction is the real record.

**Hero**
- [x] Built around exactly one signature idea, everything else quiet by comparison — evidence: only the CordRig morph animates/decorates; headline uses the site-wide plain mechanism; finish dots are tiny and static.

**Per-section concept quality**
- [~] Concept visibly traces back to the page's one core idea — evidence: hero/finishes/disassemble carry it visually; value-grid and FAQ support it through copy only, with no invented visual metaphor of their own (fair for those categories, but worth naming rather than hiding).
- [x] Passes the two-second stranger test — evidence: the disassemble screenshot shows a closed loop next to a straight cable with nothing else changed; unmistakable without a caption.
- [~] Not a repeat of a signature move already used elsewhere — evidence: the CordRig mechanic appears three times (hero ambient, disassemble interactive, finishes static-swap). Judged as justified (different trigger + narrative job each time, and the walkthrough must show the same object the hero promised) but this is a deliberate exception to the rule, not a clean pass — flagged in `concept-gallery.md` too.

**Two-column sections**
- [x] Every non-text side is genuinely alive — evidence: Finishes' right side is the animated/crossfading rig; Reserve's right side is a live interactive form, not a static image.

**Cards and containers**
- [x] No default plain bordered-card grid — evidence: value grid uses one shared hairline-divider surface, not per-item cards.
- [ ] Whole page uses cards in at most 1–2 sections — evidence: Finishes, Disassemble, and Reserve all use a bordered rounded container — three, not the stated cap of two. Named as a carry-forward action below rather than papered over.
- [x] Every card used has a customization touch and a real hover interaction — evidence: wireline texture + ambient glow + live content in the two stage cards; gradient wash + top hairline in the Reserve card; inputs have real focus states.

**Icons**
- [x] All icons from one library (Lucide), consistent throughout — evidence: Zap/Hand/Ruler/Backpack/Menu/X/ArrowDown/Check/Minus/Plus/ChevronDown, no other set mixed in.
- [x] No emojis where an icon belongs — evidence: none used anywhere on the page.

**Motion**
- [~] Every section has animation including body copy animating in — evidence: value grid, finishes, disassemble, FAQ, and footer all animate content in; the hero's own text block (badge/headline/subtitle/CTAs) does not — only the illustration animates on load. Named as a carry-forward action.
- [ ] Big numbers animate in — N/A: no stat numbers appear anywhere on the page (deliberately — no real sales/production numbers were available to show honestly).
- [~] No single animation primitive repeated across the page — evidence: same caveat as the per-section repeat note above; the rig's path-lerp appears three times, everything else is single-use.

**Type and headlines**
- [x] Display type memorable and specific — evidence: Fraunces, a new addition to `typeface-library.md`.
- [x] One deliberate headline mechanism, applied consistently — evidence: bold-line/soft-italic-line on every major heading (hero, finishes, disassemble, reserve, FAQ).
- [x] Titles short, subtitles concise — evidence: e.g. "Four finishes. / One cord underneath.", one-line subtitles throughout.
- [ ] Two-part titles split Title Case — N/A: this project's headline mechanism is full-sentence bold/soft pairs (the Revolut-style pattern), not a single title split at a comma/semicolon, so the Title Case rule doesn't apply here.
- [ ] Long title de-emphasized tail — N/A: no unavoidably long titles.

**Layout and theme**
- [x] Navbar stays visible, ~80% translucent + blurred — evidence: `bg-ink/80 backdrop-blur-md`, fixed, confirmed in every scroll-position screenshot.
- [x] Theme chosen to suit the brand, not defaulted — evidence: dark chosen deliberately for the metallic-finish/premium-studio-photography mood; see process note below on how this was decided.
- [x] Section backgrounds vary — evidence: ink → ink → ink-with-graphite-card → full graphite → ink-2-with-wireline → graphite footer.
- [x] One coherent style direction — evidence: luxury/premium showcase throughout, no split personality.

**Section bank usage**
- [x] Bank rows adapted, not transplanted — evidence: every borrowed row's 3D renders/photography were replaced with the project's own SVG illustration, palette, and copy.
- [x] Rows not repeats of the last build — N/A/pass: first build logged since the bank-usage-tracking discipline started (Weft/Flare predate it).

**Process**
- [ ] Type and color checked in with the person before finalizing — **Fail, plainly.** This arrived as a single async build request with no live back-and-forth available; type, palette, and style direction were all decided unilaterally and only explained after the fact in the handoff message. Treat every choice in this build as provisional pending Favour's actual sign-off.
- [x] Spacing between sections feels generous — evidence: `py-24`/`py-32` sections with `mt-14`–`mt-16` internal gaps.
- [x] Side padding ~4–8%, responsive — evidence: shared `Container` uses `px-[6%] sm:px-[5%] lg:px-[4%]`.
- [x] Copy sounds like this brand — evidence: cord/wire/knot vocabulary throughout ("unravel," "braid," "keeper," "worn length"), not generic template copy.
- [x] No competitor names — evidence: none appear.
- [ ] Person asked for hero concepts/visuals before one was invented — **Fail, same root cause as the type/color line.** The hero concept was inferred from the four product photos included in the request rather than confirmed with Favour beforehand.
- [x] Form branded and Google-Form-or-clearly-stubbed — evidence: `Reserve` is fully built and validated, `FORM_ENDPOINT` is an explicit `null` with a code comment plus a README section explaining exactly what Favour needs to supply.
- [ ] Business-page 75% photography — N/A, not a business-type page.
- [ ] European-website hero rules — N/A.
- [ ] Mini-business four-section rules — N/A.

**Mobile and hardening**
- [x] Headlines and fixed-dimension containers hold up at small viewports — evidence: 390px-wide screenshots of every section, no overflow or jump.
- [ ] Light/dark tokens used correctly — N/A: single fixed dark theme by deliberate choice, no light variant built.
- [x] Visible keyboard focus states, not just hover — evidence: gold focus ring confirmed via keyboard-tab screenshot.

**Overall verdict**
Strongest section is the disassembly walkthrough — the exact section the brief asked for by name, and the one where the page's whole premise (a bracelet that is honestly, physically a cable) is most legible in a single still frame. Weakest area is process discipline rather than visual execution: the required type/color and hero-concept check-ins with Favour were both skipped because the task arrived as a one-shot async build, and the hero's text block doesn't animate in even though its illustration does. A stranger would likely say the page has a real point of view — one recognizable object, used for a real narrative reason in three different registers — but that three-times reuse is a genuine trade-off for Favour to weigh in on, not a clean pass.

**Carry-forward actions for the next build**
1. Do the type/color/typeface proposal and the hero-concept check-in with the person *before* committing, even under time pressure — both were skipped here and should be treated as the default failure mode to design around, not a one-off.
2. Give the hero's text block (badge, headline, subtitle, CTAs) a staggered fade/slide-up entrance — right now only the illustration animates on load.
3. Get back under the 1–2 card cap: of Finishes/Disassemble/Reserve's three bordered stage containers, let at least one (Disassemble is the best candidate) sit borderless against its own section background instead.

## Notes for the next build

- Don't default to "traveling dot/pulse" again — it's been the primitive on both builds so far. Try a line-draw reveal, a shape that expands/contracts, or something not yet used.
- Don't default to a plain bordered-card grid for a feature or gallery section — try dividers, a scattered/staggered arrangement, or a genuinely different container.
- Hero: pick exactly one signature idea. If a headline treatment is doing real work, keep the surrounding visual concept quieter, and vice versa — don't run both at full volume.
- Neither test build so far has done the type/color check-in with the person before committing — worth doing on the next one now that it's part of the process.
- Neither test build has a formal graded scorecard — the next build should be the first to go through `references/grading-rubric.md` end to end.
- **Update after HeadFavour:** that's now three consecutive builds (Weft, Flare, HeadFavour) that skipped the type/color and hero-concept check-ins — on HeadFavour specifically because the request arrived as a single async task with no live back-and-forth channel available, not by oversight mid-conversation. If a future build is genuinely one-shot/async like this one, say so plainly in the handoff and mark every type/color/hero-concept decision as provisional, the way HeadFavour's build-log entry does — don't silently treat a unilateral call as a confirmed one.
- HeadFavour did complete the first full `grading-rubric.md` scorecard end to end (see its entry above) — use its format as the template going forward instead of a prose verdict.
- HeadFavour's rig-reused-three-times-on-one-page call (see its `concept-gallery.md` entry) is a live open question, not a settled pattern — if a future product has a similarly literal two-state physical story, decide fresh whether reusing one illustration across a hero/walkthrough/picker earns its keep or just reads as the page's only trick, rather than assuming HeadFavour's answer.
