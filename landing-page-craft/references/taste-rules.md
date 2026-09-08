# Standing Taste Rules

A checklist of patterns confirmed across multiple past builds (Allowance, didii, Revolut Founder Mode, TrashPay, FlutterBytes Conference). Use this during the build pass and especially during the section-by-section quality check.

## The icon-grid feature section is close to mandatory

Every one of the five projects has a compact grid (2x3 or similar) of icon plus short title plus a one-to-two-sentence description, explaining "here's what this does." Never expand these into paragraphs. If a feature needs more explanation than two sentences, it belongs in its own dedicated section, not a bigger card in this grid.

## Always use a real custom icon library — never emojis where an icon belongs

Icons come from a defined, professionally-drawn icon set — Lucide, Phosphor, Heroicons, or Tabler are the defaults — chosen once per project and used consistently, so every icon on the page shares one visual language (stroke weight, corner radius, level of detail). Never drop an emoji into a spot where an icon is meant to go: emojis render inconsistently across platforms, clash with the type and color system, and instantly read as unconsidered. Where an icon can be given a subtle animation (a draw-in on scroll, a gentle state change on hover), prefer that over a static glyph, especially inside a card.

## The top navbar stays visible, with a translucent blurred fill

Unless the brief explicitly says otherwise, the top navigation is always visible as the visitor scrolls (sticky/fixed), with a fill at around **80% opacity plus a background blur** (backdrop-blur) so content scrolling underneath is softly visible through it rather than hidden behind a solid bar. This keeps navigation reachable at every scroll position while staying light and glassy rather than a heavy opaque block. Only drop the always-visible behavior when there's a deliberate reason and it's been stated.

## Headlines never render plain — but the mechanism is a per-project choice

Five projects, five different treatments, each applied consistently across every major headline on that one page (not mixed within a single page):

- **Temporal scramble** — digits or random characters resolve into the real text on scroll into view (Allowance).
- **Selective letter coloring** — specific letters within words get a static accent color, consistent every time that headline appears (didii).
- **Bold-plus-soft two-line contrast** — an assertive white line followed immediately by a softer gray qualifying line underneath (Revolut: "Every screen has a job. / None are decorative.").
- **Per-line color/weight assignment** — each line of a multi-line headline gets its own color (TrashPay: white / brand-accent / gray across three lines).
- **Letters replaced by icons** — a specific double-letter inside a headline word is swapped for a small animated icon (FlutterBytes: the "tt" in "Flutter").
- **Highlighter-marker sweep on one word** — one word per headline sits on a solid, slightly skewed color block that sweeps in behind it (scaleX 0→1 from the left), text switching to a dark ink color for contrast against the bright fill (headfavour.com: "shipped" / "short" / "connect").

Pick one mechanism early and use it everywhere a headline needs weight on this project. Don't invent a new one per section. If a mechanism reads as visually close to something already shipped on one of the person's other sites (a rotated bordered badge, a specific color-block shape), treat that as a reason to pick a different one even if it would otherwise fit well — check with the person if unsure rather than assuming a mechanism is fair game just because it isn't logged yet.

**Implementation gotcha worth knowing:** for any two-layer word-marking effect (a color block behind text, an underline, anything using `position: absolute` plus a z-index to sit one layer behind sibling content), don't reach for a negative z-index to send it backward. Its stacking context resolves against the *nearest ancestor that actually establishes one* — which, depending on unrelated things like whether a nearby parent happens to be an animated `motion.*` element, can be much further up the tree than it looks, occasionally landing the "behind" layer behind the *section's own background* instead of just behind the text (this happened for real on headfavour.com's second build: the mark was invisible — dark text with no visible highlight — in some sections but not others, using the identical component, purely because of which ancestor nearby did or didn't establish a stacking context). Simplest fix, and the default to reach for first: skip z-index entirely and let plain DOM order do the work — put the background layer first in markup and the text second; normal painting order already puts later siblings on top with no ambiguity. Reserve explicit z-index for when DOM order genuinely can't express the stacking you need, and then verify the rendered result with a real computed-style/rect check (`getComputedStyle` + `getBoundingClientRect` on the actual element), not just a visual screenshot glance — this exact bug produced correct-looking `opacity`/`transform` values on inspection while still painting invisibly.

## Big numbers always animate in

Stat numbers (impact metrics, pricing, counts) get a reveal, never a static render: count-up from zero, an outline that sweeps into a solid fill, or a character scramble that resolves. This applies to any number rendered at headline size, not just a dedicated stats section.

## Fixed-dimension containers around anything that cycles or swaps content

Any element that auto-rotates, swaps state, or changes size (tabs, carousels, an image that changes on hover) needs a fixed height and width container around it. Otherwise the surrounding layout jumps every time the content changes, which reads as broken even when the content itself is fine.

## Default to one-thing-expanded, not a static equal-weight grid, for 3+ parallel options

When there are three or more parallel categories, use cases, or steps to explain, default to an auto-cycling or interactive single-focus display — one item expanded or active at a time, the rest visible but collapsed — rather than a flat grid where everything has equal visual weight all the time. This is the single most repeated interaction pattern across all five projects, whether the trigger is auto-cycling, hover, or click.

## On multi-sided products, give each audience its own consistent accent color

If the product serves more than one kind of user (consumers and businesses, for instance), assign each audience a color early and reuse it everywhere that audience is addressed, not just once. Done well, the color becomes a wayfinding device: the visitor learns "this color means the business-facing content" scrolling through the page, without being told explicitly.

## Show before/after concretely, per scenario — never state the benefit once, abstractly

If the pitch is "this used to be hard, now it's easy," don't say that once in the hero and move on. Show the specific old pain next to the specific new resolution, repeated for each real use case, in the product's actual voice. A single abstract claim is much weaker than several small concrete contrasts.

## Small colored status or availability badges on list items

Any list of options, materials, or features that have real status (live vs. coming soon, available vs. pre-order, healthy vs. near-limit) should show that status as a small colored pill directly on the item, not as plain accompanying text.

## Rotate through named layout archetypes, don't default to one

Five structural patterns to choose between per section, tracked so consecutive sections — and, over time, consecutive projects — don't repeat the same one:

- Title and subtitle above, the concept below it
- The concept above, title and subtitle below it
- Title and subtitle on the left, the concept on the right
- Title and subtitle on the right, the concept on the left
- The concept surrounding a centered title and subtitle — works well specifically when the title and subtitle are short

Check `references/build-log.md` for what recent sections and recent whole projects used, and pick something that hasn't just been used.

## Cards are a default to resist, not a neutral container

A bordered, rounded-rectangle box is the single most common container in generic web design, and reaching for it automatically is itself part of the blandness to avoid. Prefer fading divider lines to separate content where that's enough structure on its own. Where grouping genuinely needs a contained shape, look for something more considered than a plain box before settling for one.

**Cap the whole page at one or two sections that use cards at all** — if three or more sections are reaching for cards, most of them should be redesigned around dividers, a scattered/staggered arrangement, or a genuinely different container. Cards are the exception on a page, not the connective tissue.

And a card that does earn its place is never a plain box. It carries at least one deliberate touch of customization:
- a subtle shiny/glossy gradient fill (low-contrast, adds depth without noise — see the gradient rule below),
- a glass-like, semi-transparent border or stroke, or a frosted/backdrop-blur surface,
- an animated icon or other live element inside it,

plus a real hover interaction — a lift, a border glow, a color shift — never a static box that just sits there. A plain flat-fill bordered card with a static emoji and no hover is the exact failure this rule exists to prevent (flagged directly on the Flare build).

## Don't let one animation primitive become the default for everything

A dot or particle traveling along a path is one valid device, not the only one. A line that draws itself from one point to another — a stroke revealing progressively, like Allowance's hero — is an equally strong, visually distinct alternative. Keep a small set of different primitives in rotation, and never reuse the exact same one twice on a single page.

## Keep titles short and subtitles concise

Section titles and hero titles should be as short as they can be while still saying the thing — a few punchy words beats a full sentence. Subtitles should be as concise as possible: one tight line that adds what the title can't carry, not a paragraph restating it. Long titles and rambling subtitles are the default-template tell; sharpen them down before styling them.

## Two-part section titles go on two lines, in Title Case — applied with context

When a section title is naturally two parts — typically split at a `;`, `-`, or `,` ("Six things, one template.") — put the second part on its own line rather than running both together in one sentence, and set every major word with an initial capital, including "The." "Six Things" / "One Template." reads as a considered, designed title; the single run-on sentence reads as an afterthought.

Apply this with judgment, not mechanically: don't break so that a single lonely word sits on one line while the rest drops to the next, and don't force a two-line split on a title that's genuinely short enough to sit comfortably on one. The goal is a balanced, deliberate-looking pair of lines — if the split would look awkward or orphan a word, keep it on one line instead.

## If a title is unavoidably long, de-emphasize its tail rather than shrinking the whole thing

When a hero or section title can't be made short, don't render the whole thing at one big size — pick the less-essential part (preferably the last divisible part) and set it at a smaller size than the main part, while keeping it clearly visible and obviously part of the same title. This preserves a strong focal size for the words that matter and stops a long title from reading as one flat wall of large text. It's a size contrast within the title, not a hierarchy that hides anything — the smaller part still has to be very obvious.

## Generous spacing between sections — about 1.75x whatever feels sufficient

Sections that sit close together read as cramped and undifferentiated regardless of how good any individual section is. Default to roughly 1.75 times the vertical spacing that would otherwise feel like enough. Sections should never feel adjacent to their neighbors.

## Overall side padding is about 4–8% of screen width — default to 4%

The page's left/right gutter should be roughly 4–8% of the viewport width, and **4% most of the time** so there's plenty of horizontal room for content to breathe and stretch. Reach toward 8% only when a section deliberately wants a narrower, more contained measure (a long text passage, a centered focal moment). This is a horizontal container rule and is separate from the generous *vertical* spacing between sections above — set it as a responsive value (a percentage or a clamp), not a fixed pixel margin, so it holds across viewport sizes, and tighten it appropriately on mobile where 4% of a small screen is too little.

## A no-scroll, single-viewport page is a different layout problem, not a compressed version of a scrolling one

Occasionally the brief is explicitly "one screen, nothing scrolls" (a digital business card, a title/splash page, a kiosk display) rather than a scrolling one-pager. Treat this as its own layout mode, not the normal scrolling rules turned down:

- The "generous ~1.75x spacing between sections" and "4–8% side padding" rules above assume a page tall enough to breathe *because* the visitor scrolls through it over time. On a fixed viewport there's a hard, literal budget — actual available pixels — not a feeling to calibrate by eye, so those rules don't transfer directly.
- Scroll-triggered reveals (`whileInView`) stop making sense — everything is already in view at load, for every visitor, every time. Use mount-triggered animation (`initial` + `animate`) instead; it's simpler, and sidesteps IntersectionObserver-related edge cases entirely.
- Build every container in the chain from the root down as a **fill, not a stack**: `height: 100dvh` (not `100vh`, which misbehaves with mobile browser chrome) plus `overflow: hidden` on the root, then `flex-1` / `min-height: 0` at every nested level that needs to consume the remaining space rather than size to its own content. Skipping `min-h-0` on any flex child in that chain is the single most common way this silently breaks — the child reverts to its content's natural height and quietly overflows the fixed viewport instead of respecting it.
- For a list of N similar items that must always exactly fill whatever vertical space is left (a project list, a set of stats) — rather than guessing a row height that happens to fit — make each row `flex-1` inside a `flex flex-col` list container. The rows then always exactly share whatever space remains, self-adjusting to any viewport height with no manual tuning, and structurally cannot overflow their container.
- Scale type and spacing off viewport *height*, not just width — `clamp(1.5rem, 4vh, 3rem)` instead of a `vw`-only clamp — so the composition compresses gracefully on short viewports (a small laptop, a landscape phone) instead of overflowing. Test the shortest realistic viewport height deliberately, not just narrow width.
- **Verify the actual requirement, not a visual impression of it:** screenshot a few sizes and it can *look* fine while still technically scrolling by a few pixels. Check `document.documentElement.scrollHeight <= document.documentElement.clientHeight` (or equivalent) at several real viewport sizes — a wide desktop, a small laptop, a short laptop, portrait and landscape mobile — and treat that boolean as the actual pass/fail, not a screenshot glance. This is cheap to script and removes all doubt.

## Subtle gradients add depth without adding noise

A flat fill isn't always the right call. A soft gradient — radial or linear, low-contrast — behind a card, inside an icon container, or washing gently across a section background, adds real depth and richness without competing with content the way a busy pattern or a loud color block would. Reserve strong flat color for the moments meant to actually grab attention (a primary button, an active state); let ambient depth come from a gradient that's barely noticeable until you look for it.

## Not every site is dark — pick the theme that actually suits it, and vary section backgrounds

Dark theme is not the default. Choose light or dark based on what genuinely fits the brand, the audience, and the imagery — a bakery, a fashion label, or an airy editorial product often reads far better light; plenty of others suit dark. Decide deliberately as part of the type-and-color step, not by habit.

Whichever base theme is chosen, the whole page should not be one single flat background top to bottom. Give some sections their own distinct background — a value close to white or close to black (a step off the base), or a subtle gradient — so there's rhythm and separation between sections. The rule is just that a differentiated section's background is clearly *not* the same as the surrounding sections; it shouldn't be a jarring loud color block (that stays reserved for genuine attention moments per the gradient rule), but it should be visibly its own surface.

## Ambient background texture stays almost illegible at rest

Decorative background motifs — circuit lines, particle fields, connection lines, watermark wordmarks — should sit at very low opacity and never compete with foreground content for attention. Presence, not prominence.

## Voice and copy are a taste surface too, not just visuals

Word choice, punctuation, and small verbal puns carry brand personality as much as color and type do. Match the copy's actual voice to the audience, and don't be afraid of a genuinely audience-specific metaphor for a whole section's framing, not just its word choice — a team-credit section reframed around "commits" for a developer audience, for instance, rather than a generic "meet the team."

Don't name competitor brands in the copy — direct or indirect — unless the person has specifically asked for it (a case-study/portfolio page reimagining a named company is the obvious exception, and it's stated). Make the point through the value itself ("no more juggling five separate tools") rather than by calling out a rival by name.

## The design-token pattern, if the site needs light/dark theming or is going to production

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
