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

## headfavour.com — personal portfolio / shipped-projects catalog

- Site type: Portfolio / case-study page, adapted — a personal one-pager catalog of five shipped products rather than a single reimagined company. No waitlist, no form, no fake stats; the "why this matters" slot became a short first-person bio instead of company numbers, per the brief.
- Style direction: closest to Neo-glow dark tech, but grounded throughout in a literal ink-stamp/shipping-manifest concept rather than generic dark+accent decoration.
- Type: Bricolage Grotesque (display), IBM Plex Mono (labels/eyebrows/status tags), Manrope (body).
- Palette: near-black ink base (#08090C) stepped against two raised tones (#111219, #16171F) for section separation, warm paper off-white (#F2EEE4) for text, one accent — ink-stamp red-orange (#FF4522) — used everywhere something needed emphasis (headline stamps, status dots, primary CTA, focus rings). Reasoning: dark like a workspace at 2am, warm paper-white text like a page under a desk lamp, one stamp-ink accent standing for "shipped/live," not decorative dark-mode-by-default.
- Hero signature: a single rotated, outline-only ink-stamp badge slams onto the word "SHIPPED" inside the headline on load (spring overshoot + radial ink-bleed glow), everything else in the hero (corner byline tag, subtitle, CTAs, scroll cue) stays quiet by comparison.
- Headline mechanism: the ink-stamp badge (new — added to `taste-rules.md`'s list), reused smaller on every section title ("SHORT", "CONNECT").
- Section signatures used: shipping-manifest numbered list replacing a card grid for the project catalog (new — logged as SEC-13); clip-path left-to-right text wipe for the bio paragraph; stamp-badge icon row with a hover press+de-rotate interaction for socials.
- Layout archetypes used: hero = stacked/left-aligned; bio = concept surrounding a centered title (short copy); shipping log = title/subtitle above, content below; socials = title/subtitle left, concept right. Four different archetypes, no repeats.
- Animation primitives used: spring impact-drop (hero + all headline stamps), clip-path wipe (bio paragraph), staggered slide-up entry (manifest rows on scroll), dash-offset underline draw (manifest row hover, verified via computed-style check in a real browser), press + de-rotate + color-shift (social badge hover/tap, also verified via computed style). Five distinct primitives, no repeats — and deliberately did not reach for "traveling dot/pulse," which the two prior test builds had over-used.
- Bank rows consulted (comparison only, none transplanted — invented-from-scratch won the intake comparison for the manifest list): HERO-05, B2B-15, B2B-30, B2B-73, B2B-80, FT-01, EDT-12. New row contributed: SEC-13 (Stamped Shipping Manifest List).
- Built and verified in a real environment: Next.js dev server run locally, scroll-triggered animations confirmed via scripted Playwright capture (not just predicted), hover/press interactions confirmed via computed-style assertions (`:hover` match, resolved border-color, transform matrix) rather than eyeballing screenshots alone, keyboard focus-visible ring confirmed visually, mobile viewport (390×844) checked section by section, production `next build` passed clean.

### Grade — headfavour.com, 2026-08-18

**Hero**
- [x] Built around exactly one signature idea, everything else quiet by comparison — evidence: only the rotated "SHIPPED" stamp badge is loud; byline tag, subtitle, and CTAs are small and muted in the same screenshot.

**Per-section concept quality**
- [x] Concept visibly traces back to the page's one core idea — evidence: hero's stamp, bio's "SHORT" stamp, the manifest list, and the stamp-badge socials all extend the same "proof, already shipped/marked" idea rather than each illustrating an isolated feature.
- [~] Passes the two-second stranger test with no caption — evidence: hero and shipping-log pass outright (stamp + numbered "LIVE" rows read instantly); the socials stamp-badges are Partial on their own — they read as "social links" instantly but the *stamp* metaphor specifically only lands because the hero already established it earlier on the same page.
- [x] Not a repeat of a signature move already used elsewhere on this page, or on the last logged build — evidence: five distinct animation primitives (see above), no prior build used the stamp/manifest concepts.

**Two-column sections**
- [x] Every non-text side is genuinely alive — evidence: the only two-column section (socials) has an animated, interactive stamp-badge cluster on the non-text side, not a static image.

**Cards and containers**
- [x] No default plain bordered-card grid where a divider or more considered container would serve better — evidence: the project catalog is a divided manifest list, not cards.
- [x] Cards used in at most one or two sections — evidence: zero sections use a plain card; category/status pills and circular badges are the only "contained" shapes.

**Icons**
- [x] All icons from one chosen custom library, consistent throughout — evidence: Lucide (ArrowDown, ArrowUpRight, ArrowUp, Mail) for UI icons; five brand marks (LinkedIn/GitHub/X/Instagram/Facebook) hand-rolled as consistent single-color SVGs since lucide-react ships no brand logos.
- [x] No emojis used where an icon belongs — evidence: none used anywhere on the page.

**Motion**
- [x] Every section has some animation or interaction, body copy animates in — evidence: bio paragraph uses a clip-path wipe, not a plain appear.
- [ ] N/A — no stat numbers on this page (portfolio catalog, not a metrics page).
- [x] No single animation primitive repeated across the whole page — evidence: verified list of five distinct primitives above; explicitly avoided "traveling dot/pulse," which both prior test builds over-used.

**Type and headlines**
- [x] Display type is memorable and specific — evidence: Bricolage Grotesque, clearly distinctive in screenshots, not a system face.
- [x] One deliberate headline mechanism, applied consistently — evidence: the ink-stamp badge appears on the hero headline and all three section titles.
- [x] Titles short, subtitles concise — evidence: "Actually SHIPPED.", "The SHORT version.", "Let's CONNECT." plus one-line subtitles throughout.
- [ ] N/A — no two-part titles needed splitting.
- [ ] N/A — no unavoidably long titles.

**Layout and theme**
- [x] Top navbar stays visible while scrolling, ~80% translucent with background blur — evidence: `bg-ink/80 backdrop-blur-md`, confirmed in screenshots.
- [~] Theme chosen to suit the brand, not defaulted to dark — evidence: dark was a deliberate, reasoned choice (workspace-at-night / stamp-under-lamplight framing tied to the concept), but Partial because the type/color check-in with the person happened as a stated design decision in the final write-up rather than as a live back-and-forth before building (see Process below).
- [x] Section backgrounds vary — evidence: ink → ink-raised → ink → ink-raised → ink-raised-2 across the five sections, confirmed in screenshots.
- [x] One coherent style direction — evidence: every section stays within the ink-stamp/manifest language; no split-personality mixing of mood families.

**Section bank usage**
- [x] Bank rows adapted, not transplanted — N/A in the transplant sense (rows were consulted for comparison, not adapted) — evidence: intake compared HERO-05/B2B-15/B2B-30/B2B-73/B2B-80/FT-01/EDT-12 against an invented-from-scratch manifest-list concept; the invented concept won and was logged fresh as SEC-13 rather than derived from an existing row.
- [x] Rows used are logged and aren't repeats from the last build — evidence: see "Bank rows consulted" above; none overlap with Weft/Flare's (informal) usage.

**Process**
- [ ] Type and color were checked in with the person before being finalized — **Fail, honestly.** Decided solo under this session's explicit bias-to-act instruction rather than pausing for a live typeface/palette confirmation, continuing the pattern both prior test builds also skipped. Flagged plainly in the summary given to the person rather than silently marked Pass.
- [x] Spacing between sections feels generous — evidence: `py-28 md:py-40` section padding, clearly separated in full-page screenshots.
- [x] Side padding sits around 4% — evidence: `px-[4%]` used consistently.
- [x] Copy sounds like this brand specifically — evidence: first-person, specific phrasing ("I'd rather launch than talk about launching," "breaking it by dinner"-style voice trimmed down) rather than template copy.
- [x] Copy names no competitor brands — evidence: none named.
- [ ] The person was asked for concepts/visuals they'd want, especially for the hero, before one was invented — **Fail, honestly.** Not asked live; inferred from an already-directive brief ("beautiful/creative style… develop this further") under the same bias-to-act instruction. Worth asking explicitly next time even when the brief feels sufficient.
- [ ] N/A — no form on this page.

**Mobile and hardening**
- [x] Headlines and fixed-dimension containers hold up at small viewports — evidence: 390×844 screenshots checked section by section, no overflow or broken stacking.
- [x] Light/dark tokens used correctly — evidence: dark-only by deliberate choice, tokens defined via Tailwind v4 `@theme`.
- [x] Visible keyboard focus states, not just hover — evidence: screenshot of Tab-focused social badge shows a clear accent-colored outline ring via a global `:focus-visible` rule.

**Overall verdict**
Strongest section is the hero — the stamp lands in under two seconds and states the page's whole thesis in one gesture, with real restraint around it. The shipping-log manifest list is the second-strongest and the most structurally novel: it does real information-scannability work a card grid wouldn't, and it's the first build to log a genuinely new section-bank row rather than only adapting existing ones. The weakest link is the socials section — solid execution, but the stamp-badge idea leans on the hero having already taught the visual language rather than reading as its own concept in isolation. A stranger scrolling this page would say it has a specific point of view (a builder who ships constantly, literally stamped as proof) rather than a generic portfolio template with the name swapped in.

**Carry-forward actions for the next build**
1. Do the type/color/style-direction check-in with the person live, before building — this is now three builds in a row (Weft, Flare, headfavour.com) that skipped it, twice under an explicit bias-to-act instruction rather than by oversight; worth explicitly flagging the tension between that instruction and this standing process step at the start of the next build rather than defaulting to solo decisions again.
2. The shipping-manifest list is strong, specific, and freshly logged (`section-bank.csv` SEC-13) — available for reuse on a future builder/founder-facing brief. The headline mechanism actually shipped is the highlighter-marker sweep (see revision below), not the ink-stamp badge — check `concept-gallery.md`'s current status on each before reusing either.
3. If headfavour.com grows past five projects, extend `src/lib/data.ts` rather than hand-editing the manifest markup — the section was built data-driven specifically so it scales.

### Revision — headfavour.com, same day, post-launch feedback

The person's very first piece of feedback after seeing the build: the ink-stamp headline badge (rotated bordered box around slanted text) was already used on a different one of their own sites, and needed to be a genuinely different treatment. Two real changes followed, both pushed the same day:

1. **Headline mechanism replaced.** The rotated stamp badge is retired (see `concept-gallery.md`) and replaced everywhere it appeared — hero, bio, shipping log, connect — with a highlighter-marker sweep: a skewed solid color block scales in behind the word, text switches to a dark ink color rather than sitting inside a border. Same core idea (a claim made real/official), different physical object, so the page's overall concept didn't need to change, just this one mechanism. `taste-rules.md`'s headline-mechanism list and `concept-gallery.md` are both updated to reflect what's actually live, not what the first pass shipped.
2. **Social badge rotation dropped.** The circular social-link badges had been given the same tilt/rotation as the stamp badges, framed as an extension of that visual language. Once the headline stamp was gone, the rotation had no remaining justification, so it was removed — badges kept their vertical stagger and hover states, just lost the tilt. Logged as a retirement in `concept-gallery.md` rather than silently edited.

**A real bug surfaced while doing this**, worth its own carry-forward line since it's a general implementation trap, not specific to this project: the highlighter block's first implementation used a negative `z-index` to sit behind the text. That resolved correctly in some sections and rendered completely invisible in others (dark text, no visible highlight, section background showing through) — same component, same props, different result — because the nearest ancestor that actually establishes a stacking context varies by section (an animated `motion.*` ancestor nearby changes the answer), so the negative z-index was occasionally escaping much further up the tree than intended and painting behind the section's own background. Screenshots taken via fast scripted scrolling were themselves unreliable for catching this (see below), and a `getComputedStyle`/`getBoundingClientRect` check can show fully correct values while the element still paints invisibly, so neither of the usual checks caught it on their own — what actually confirmed it was screenshotting immediately after a real `scrollIntoViewIfNeeded()` + fixed wait, in the same script as the computed-style check, and comparing the two. Fixed by dropping z-index entirely and relying on DOM order (background element first, text second) — the general-purpose fix for this class of bug. Full note added to `taste-rules.md` under the headline-mechanism entry so it's checked before the next build reaches for a similar layered-text effect.

**Also worth carrying forward on testing method, not just the design:** verifying scroll-triggered (`whileInView`) animations by scripting `window.scrollTo` jumps with short fixed waits is unreliable on a page that also sets `scroll-behavior: smooth` globally (which this project does, for anchor-link nav) — the CSS applies to *all* scroll calls including programmatic ones, so a jump can still be mid-animation when the screenshot fires, producing a false "broken" read (this happened here, on a mobile hero screenshot that looked cut off and wrong, then rendered perfectly on a plain fresh page load with no scripted scrolling involved). When a scroll-triggered screenshot looks wrong, check with `scrollIntoViewIfNeeded()` (or a fresh unscrolled load, for above-the-fold content) plus a real computed-style read before concluding the component itself is broken — cheap scripted scrolling produces both false negatives (this note) and, separately, real bugs can still hide behind values that read as correct (the z-index note above) — neither check alone is sufficient, both together are.

## Notes for the next build

- Don't default to "traveling dot/pulse" again — it's been the primitive on both builds so far. Try a line-draw reveal, a shape that expands/contracts, or something not yet used.
- Don't default to a plain bordered-card grid for a feature or gallery section — try dividers, a scattered/staggered arrangement, or a genuinely different container.
- Hero: pick exactly one signature idea. If a headline treatment is doing real work, keep the surrounding visual concept quieter, and vice versa — don't run both at full volume.
- Neither test build so far has done the type/color check-in with the person before committing — worth doing on the next one now that it's part of the process.
- Neither test build has a formal graded scorecard — the next build should be the first to go through `references/grading-rubric.md` end to end.
