# Build Log

A running record of what's been used on past builds with this skill, so a new project can deliberately avoid repeating a recent one's section styles, signature concepts, or animation primitives — not just within a page, but across projects. Check this before starting a new build. Add an entry after finishing one, real or test.

Going forward, every new entry should end with the corrected scorecard from `references/grading-rubric.md` (Claude drafts it against the real render, the person corrects it) instead of just a prose verdict — the Weft and Flare entries below predate the rubric and keep their original prose-verdict format. Also cross-check `references/concept-gallery.md` and `references/typeface-library.md` when logging a new entry: log anything new there too, and retire anything that's now been used enough times to need a rest.

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

## Kronikl (real build) — magazine maker landing page / rebrand

- Site type: **product landing page** (a tool whose CTA is "Create Magazine", not a waitlist). Rebrand of an existing site (MagzineMaker → Kronikl).
- Stack: Next.js 14 + TypeScript + Tailwind + Framer Motion + Lucide. Built and screenshotted live in Claude Code (real renders, desktop + mobile).
- Type: **Syne** (display/headings/UI), **Inter** (body). Client-specified, not proposed.
- Palette: very dark blue base (`#080B16`) + surfaces (`#0E1323` / `#141B30`), **danfo yellow** (`#F7B500`) primary, warm cream (`#F5F0E6`) text. Client-specified.
- Core concept: *your ordinary photos become newsstand-quality magazines.* Every section expresses "photo → real magazine."
- Headline mechanism: one accent word per headline in danfo yellow with an animated marker-highlight sweep (scaleX from left). Used on every major headline.
- Hero signature: photo composing into a magazine cover (masthead/cover-lines/tab/barcode fade+rise onto a portrait) + a filename→issue-label chip. One idea; headline stays quiet.
- Section signatures used: stats count-up strip; auto-cycling one-expanded templates showcase (index rail + fixed-frame featured cover, incl. one type-driven newspaper cover for variety); spread-assembling How It Works (clip-wipe photos + line-draw text + export stamp); divider-separated icon feature grid (not boxed cards); contents-index folio tips; left-edge-indicator FAQ accordion; cover-fanned final CTA echoing the hero.
- Layout archetypes used: title-above/concept-below (hero, features), title-left/concept-right (how-it-works, faq), header-row + two-column showcase (templates), two-column contents index (tips). Deliberately rotated, no two consecutive the same.
- Animation primitives: clip-path wipe, scaleX line-draw, staggered fade-rise, count-up, crossfade, marker sweep. **Deliberately avoided the traveling-dot/pulse primitive** flagged on both prior builds.
- Reused from gallery: none directly; invented four new concepts (logged in concept-gallery.md).

### Grade — Kronikl, 2026-07-07 (Claude's draft, for the person to correct)

**Hero**
- [x] One signature idea, everything else quiet — Pass: the photo→cover compose is the only loud move; headline uses the standard quiet marker mechanism, background is near-illegible glow + column rules.

**Per-section concept quality**
- [x] Traces back to the one core idea — Pass: every section is literally about magazines (covers, spreads, contents pages, issues), not generic feature illustration.
- [x] Two-second stranger test — Pass: hero reads "photo becomes a cover"; How It Works reads "empty spread fills with my stuff"; both legible without caption.
- [x] Not a repeat of a move used elsewhere / last build — Pass: four distinct concepts on-page; avoided the traveling-dot primitive that defined Weft and Flare.

**Two-column sections**
- [x] Non-text side genuinely alive — Pass: How It Works right side is an animated assembling spread (not a flat image); templates showcase pairs a live index rail with a crossfading cover; FAQ's non-text side is the interactive accordion itself.

**Cards and containers**
- [x] No default plain-card grid where a divider serves — Pass: feature grid uses hairline gap-px dividers; tips use a bordered contents index with folio numbers, not stacked cards.
- [x] Cards used in ≤2 sections — Partial: the magazine covers are card-like and appear in several sections, but they're the product artifact itself, not generic containers; genuine bordered-box cards only appear in How It Works step rows.
- [x] Each card has a customization touch + real hover — Pass: feature tiles get a top gradient-glow + icon ring shift on hover; step rows get a border/fill state change.

**Icons**
- [x] One library throughout — Pass: Lucide everywhere (plus one hand-drawn TikTok SVG that Lucide lacks).
- [x] No emojis where an icon belongs — Pass.

**Motion**
- [x] Every section animates incl. body copy — Pass: shared Reveal wraps body text with fade-rise; no section renders fully static.
- [x] Big numbers animate in — Pass: stats use a spring count-up.
- [x] No single primitive repeated everywhere — Pass: six different primitives; traveling-dot deliberately absent.

**Type and headlines**
- [x] Display type memorable/specific — Pass: Syne at 800 weight, distinctly editorial.
- [x] One headline mechanism applied consistently — Pass: accent-word + marker sweep on hero, templates, how-it-works, features, tips, faq, final CTA.
- [x] Titles short, subtitles concise — Pass: "Featured templates", "Three steps, one magazine", "Six ways to a sharper issue".
- [x] Two-part titles split sensibly — Pass: two-line splits are balanced, no orphans.
- [ ] Long-title tail de-emphasis — N/A: no unavoidably long title.

**Layout and theme**
- [x] Sticky translucent blurred navbar — Pass: fixed pill nav, `bg-navy/70` + backdrop-blur once scrolled.
- [x] Theme chosen to suit brand — Pass: dark was client-specified and suits a premium editorial magazine tool.
- [x] Section backgrounds vary — Pass: base navy alternates with `navy-2` on stats, features, and FAQ; hero and final CTA carry danfo radial washes.

**Process**
- [ ] Type/color checked in with the person — N/A / by-proxy: the client pre-specified Syne + danfo yellow + dark blue in the brief, so no separate proposal was run (the step's intent — not deciding alone — was satisfied by their explicit direction). Worth noting the candidate-rendering step was skipped because the decision was already made.
- [x] Generous section spacing — Pass: ~8–9.5rem vertical padding per section.
- [x] Side padding ~4% responsive — Pass: `px-[4vw]` throughout, tightened containers where needed.
- [x] Copy sounds brand-specific — Pass: "minus the print shop", "made for people with a story to print", issue/masthead/spread vocabulary.
- [x] No competitor names — Pass.
- [ ] Asked person for hero concepts first — Partial: proceeded on a complete brief without a separate "any visuals you'd want?" question; the screenshots served as the reference input.
- [ ] Form → Google Form — N/A: landing page has no form yet (footer Contact/Request-a-Template are stubs).
- [ ] Business-page photography ratio — N/A: product page.
- [ ] European-website hero — N/A.

**Mobile and hardening**
- [x] Headlines / fixed containers hold at small viewports — Pass: verified at 390px; headline line-breaks clean, showcase/spread stack, cover uses container-query units so it scales intact.
- [ ] Light/dark tokens — Partial: tokens defined as RGB channels and used throughout, but only a dark theme is shipped (no light mode toggle built).
- [ ] Visible keyboard focus states — Partial: relies largely on default focus; explicit focus-visible rings not yet added. **Carry-forward.**

**Overall verdict**
Strongest sections are the hero (photo→cover compose) and How It Works (the assembling spread) — both pass the two-second test and are unmistakably about this product. The type-driven "People's Press" newspaper cover among the photo covers adds real editorial variety. Weakest area is hardening: no explicit keyboard focus states and no light mode. A stranger would say this page has a clear, specific point of view — it could not be swapped onto a non-magazine product without rewriting every section's visual.

**Carry-forward actions for the next build**
1. Add explicit `focus-visible` states on interactive elements as part of the build pass, not the harden pass — it keeps slipping to "Partial".
2. When a client pre-specifies type/color, still render the name in the chosen face early as a confirmation image, rather than treating the decision as fully closed.
3. Container-query units (`cqw`) for self-contained mockups (like the covers) worked well for intact scaling — but every root using them needs `container-type: inline-size` on itself; a missing one silently falls back to viewport sizing. Worth a standing note.

## Notes for the next build

- Don't default to "traveling dot/pulse" again — it's been the primitive on both builds so far. Try a line-draw reveal, a shape that expands/contracts, or something not yet used.
- Don't default to a plain bordered-card grid for a feature or gallery section — try dividers, a scattered/staggered arrangement, or a genuinely different container.
- Hero: pick exactly one signature idea. If a headline treatment is doing real work, keep the surrounding visual concept quieter, and vice versa — don't run both at full volume.
- Neither test build so far has done the type/color check-in with the person before committing — worth doing on the next one now that it's part of the process.
- Neither test build has a formal graded scorecard — the next build should be the first to go through `references/grading-rubric.md` end to end.
