# Standing Taste Rules

A checklist of patterns confirmed across multiple past builds (Allowance, didii, Revolut Founder Mode, TrashPay, FlutterBytes Conference). Use this during the build pass and especially during the section-by-section quality check.

## The icon-grid feature section is close to mandatory

Every one of the five projects has a compact grid (2x3 or similar) of icon plus short title plus a one-to-two-sentence description, explaining "here's what this does." Never expand these into paragraphs. If a feature needs more explanation than two sentences, it belongs in its own dedicated section, not a bigger card in this grid.

## Headlines never render plain — but the mechanism is a per-project choice

Five projects, five different treatments, each applied consistently across every major headline on that one page (not mixed within a single page):

- **Temporal scramble** — digits or random characters resolve into the real text on scroll into view (Allowance).
- **Selective letter coloring** — specific letters within words get a static accent color, consistent every time that headline appears (didii).
- **Bold-plus-soft two-line contrast** — an assertive white line followed immediately by a softer gray qualifying line underneath (Revolut: "Every screen has a job. / None are decorative.").
- **Per-line color/weight assignment** — each line of a multi-line headline gets its own color (TrashPay: white / brand-accent / gray across three lines).
- **Letters replaced by icons** — a specific double-letter inside a headline word is swapped for a small animated icon (FlutterBytes: the "tt" in "Flutter").

Pick one mechanism early and use it everywhere a headline needs weight on this project. Don't invent a new one per section.

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

A bordered, rounded-rectangle box is the single most common container in generic web design, and reaching for it automatically is itself part of the blandness to avoid. Prefer fading divider lines to separate content where that's enough structure on its own. Where grouping genuinely needs a contained shape, look for something more considered than a plain box before settling for one. Any card-like container that does get used needs a real hover interaction — a lift, a border glow, a color shift — never a static box that just sits there.

## Don't let one animation primitive become the default for everything

A dot or particle traveling along a path is one valid device, not the only one. A line that draws itself from one point to another — a stroke revealing progressively, like Allowance's hero — is an equally strong, visually distinct alternative. Keep a small set of different primitives in rotation, and never reuse the exact same one twice on a single page.

## Two-part short section titles go on two lines, in Title Case

When a section title is naturally two short parts ("Six things, one template."), split them onto separate lines rather than running them together in one sentence, and set every major word with an initial capital, including "The." "Six Things" / "One Template." reads as a considered, designed title; the single run-on sentence reads as an afterthought.

## Generous spacing between sections — about 1.75x whatever feels sufficient

Sections that sit close together read as cramped and undifferentiated regardless of how good any individual section is. Default to roughly 1.75 times the vertical spacing that would otherwise feel like enough. Sections should never feel adjacent to their neighbors.

## Subtle gradients add depth without adding noise

A flat fill isn't always the right call. A soft gradient — radial or linear, low-contrast — behind a card, inside an icon container, or washing gently across a section background, adds real depth and richness without competing with content the way a busy pattern or a loud color block would. Reserve strong flat color for the moments meant to actually grab attention (a primary button, an active state); let ambient depth come from a gradient that's barely noticeable until you look for it.

## Ambient background texture stays almost illegible at rest

Decorative background motifs — circuit lines, particle fields, connection lines, watermark wordmarks — should sit at very low opacity and never compete with foreground content for attention. Presence, not prominence.

## Voice and copy are a taste surface too, not just visuals

Word choice, punctuation, and small verbal puns carry brand personality as much as color and type do. Match the copy's actual voice to the audience, and don't be afraid of a genuinely audience-specific metaphor for a whole section's framing, not just its word choice — a team-credit section reframed around "commits" for a developer audience, for instance, rather than a generic "meet the team."

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
