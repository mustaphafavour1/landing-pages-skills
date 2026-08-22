# Section Design Bank

A library of **194 described website sections** (155 unique styles — some are re-listed or minor variants, cross-referenced in the index below) living in `references/section-bank.csv`. Each row is one section design, described in enough detail to actually build from: layout hierarchy, background treatment, typography and spacing specs, and motion/animation mechanics, plus kebab-case tags and sample use cases.

This bank is **raw material, not a template catalog.** The skill's core promise — every section has a signature concept specific to *this* brand — does not change. The bank's job is to make the concept pass richer and faster: instead of inventing every layout, background, and motion idea from a blank page, shortlist real described patterns, then adapt them until they belong to the project.

---

## How to read the CSV

Columns: `Section ID, Category Name, Section Style Name, Description & Layout Hierarchy, Background Elements, Typography & Spacing Specs, Motion & Animation Mechanics, Helpful Tags & Comments, Sample Sections / Use Cases`.

Practical notes:
- **Grep it, don't parse it.** Some rows contain unquoted commas, so strict column splitting mis-aligns on a few rows — read matching rows whole. Find candidates by ID (`^HERO-05`), by tag (`glassmorphism`, `bento`, `brutalist`, `full-bleed-nature`), or by use-case words (`booking`, `pricing`, `lookbook`).
- The **index below** is the fast path: skim the category you need, note 2–3 candidate IDs, then grep the CSV for their full rows.

## How the bank plugs into the build process

1. **During the per-section intake (step 5 in `SKILL.md`):** after naming what the section is about, pull **two or three candidate rows** from the bank — matched by section category first (hero, pricing, FAQ, footer…), then by the project's style direction and mood tags. Weigh them against each other and against an invented-from-scratch option. Sometimes the blank-page idea wins; that's fine — the bank raises the floor, it doesn't cap the ceiling.

2. **Adapt, never transplant.** A bank row arrives with its own palette, typefaces, and pixel specs. Those belong to the row, not to your project:
   - **Colors:** re-map every hex in the row to the project's confirmed palette. The row's lavender/periwinkle/neon-yellow is a description of *contrast roles* (base, accent, glow), not colors to ship.
   - **Type:** the row's px sizes are proportions, not law. Re-express them in the project's type scale and confirmed typefaces.
   - **Copy and imagery:** always the project's own. A "botanical glassmorphic capsule" row used for a machinery exporter becomes frosted capsules over the exporter's own facility photography — the *mechanic* transfers, the skin doesn't.
   - **Motion:** the motion column is the most transferable part — dash-offset draws, odometer count-ups, flex-grow column expansion, staggered entries, parallax float offsets, marquee crawls, mask reveals. Treat it as a motion vocabulary. The standing rule still applies: never repeat the same animation primitive twice on one page.

3. **The two-second test still governs.** A bank row is a layout skeleton, not a concept. After adapting one, the section must still pass the signature-move checks in `references/signature-moves.md` — would a stranger get what this section represents, for this specific brand, without a caption? If the adapted row reads as "nice generic section," push the brand's own metaphor into it or drop it.

4. **Track usage to force variety.** When a build ships, log which bank IDs influenced which sections in that build's `references/build-log.md` entry (e.g. `Bank rows used: HERO-05 (adapted: hero), FAQ-04 (adapted: FAQ), B2B-13 (proof baseline)`). Before starting a new build, check the last one or two entries and **don't lean on the same rows again** — same rule as signature moves and typefaces. With 155 unique styles there is no excuse for two consecutive projects rhyming.

5. **Mix across categories deliberately.** The bank's categories are labeled by *function* (hero, pricing, footer) and by *mood family* (Minimalist, Organic/Clean-Tech, Editorial/Gallery, B2B/Fintech). A coherent page usually draws its rows from one or two mood families that match the project's chosen style direction — cherry-picking a brutalist hero, an aurora-pastel feature deck, and a foggy-forest footer onto one page produces the "split personality" failure. Pick the mood lane first, then shop within it, borrowing outside it only as a deliberate accent.

## Style families the bank teaches

Use these as named style directions when deciding the project's visual direction during the type/color/theme step — one dominant family per project, chosen for brief-specific reasons:

- **Aurora / pastel glow** — soft radial gradient meshes, glassmorphic icon wells, high-key canvases (HERO-01, SEC-11, B2B-08).
- **Neo-glow dark tech** — charcoal/black bases, neon accent glyphs, rotating gradient borders, engineering grid overlays (PRC-02, B2B-15, B2B-45, FAQ-06).
- **Clean-tech organic** — deep greens, nature photography under floating white cards, milestone timelines, lime accents (SEC-04/05/06, ORG-01…05, FT-01).
- **Editorial / brutalist** — giant canvas-filling type, overlapping media frames, marquee crawls, wireline grids, high-contrast color blocks (HERO-05/14, CON-02/03, EDT-01/09, B2B-63/65).
- **Minimalist high-key** — off-white fields, zero decoration, generous space, type-led statements with a single accent color (MIN-01…04, EDT-15, B2B-103).
- **Luxury / premium showcase** — 3D product renders, vertical script watermarks, matte black conversion containers, full-bleed hospitality photography (HERO-13/15/16, B2B-56/67/72, EDT-04…07).
- **Corporate B2B / fintech** — bento capability matrices, dashboard mockups, odometer metric baselines, logo-proof grids (B2B-13/21/33/37/38/48/80).

These families also slot straight into the existing site types: **European website** and **mini-business** builds shop mostly in Luxury/premium showcase + Minimalist high-key; **business pages** in Clean-tech organic + Luxury showcase; **product pages** in Aurora, Neo-glow dark, or Corporate B2B depending on the brand's temperature.

## Growing the bank

The bank is append-only, like the concept gallery:
- Add new rows to `section-bank.csv` with the next free ID in the right category (or continue the B2B numbering for anything that doesn't fit an existing category).
- When a build invents a section good enough to reuse, describe it in the CSV's own column language (layout hierarchy / background / type specs / motion mechanics / tags / use cases) and add it.
- Never delete rows. If a row keeps producing weak results, note that in the build log instead.

---

## Index

### Hero Sections

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

### 2nd / Feature Sections

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

### Pricing Sections

- **PRC-01** — High-Contrast Bento Pricing Grid · `pricing-grid, bento-style, featured-card, saas-conversion`
- **PRC-02** — Dark Neo-Glow Tiered Pricing Matrix · `pricing-grid, neon-border-glow, dark-mode, bento-pricing`
- **PRC-03** — Bi-Color High-Contrast Pricing Matrix · `pricing-matrix, inverted-color-block, mint-green-ui, vertical-stack-pricing`
- **PRC-04** — High-Contrast Bento Subscription Matrix · `pricing-grid, bento-pricing-matrix, color-inversion-block, centered-conversion`

### FAQs

- **FAQ-01** — Full-Width Centered FAQ Accordion Stack · `accordion-stack, faq-section, interactive-list, clean-ui`
- **FAQ-02** — Split-Layout Minimalist FAQ Grid · `split-accordion, two-column-faq, bento-list, modern-minimalist`
- **FAQ-03** — Editorial Grid Accordion Showcase · `split-faq-grid, studio-media-frame, dark-mode-accordion, clean-alignment`
- **FAQ-04** — Glassmorphic Document Accordion Stack · `glassmorphism, typography-backdrop, sky-gradient, accordion-list`
- **FAQ-05** — Layered Progressive FAQ Dashboard · `faq-dashboard, capsule-conversion-card, interactive-accordion-stack, step`
- **FAQ-06** — Wireframe Matrix Accordion FAQ · `accordion-matrix-faq, wireline-grid-dividers, technical-coordinate, clean`

### Footers

- **FT-01** — Structured Clean-Tech Subscription Footer · `clean-tech-footer, newsletter-capture, directory-columns, giant-watermark`
- **FT-02** — Luminous Mesh Capsule Footer · `capsule-footer, neon-mesh, brand-watermark, centered-conversion`
- **FT-03** — Minimal Gradient Baseline Utility Footer · `minimal-footer, gradient-wash, directory-columns, clean-alignment`
- **FT-04** — Low-Contrast Minimalist Contact Closure · `minimalist-footer-closure, neon-gradient-bleed, email-capture-form, footer`
- **FT-05** — Technical Coordinates Footer Closure · `technical-coordinate-footer, email-capture-form, minimal-directory, dark-mode-closure`
- **FT-06** — Wide Gradient Tech Directory Footer · `minimalist-footer, giant-watermark-base, email-capture-form, horizontal`

### Testimonials

- **TEST-01** — Framed Carousel Testimonial Slider · `testimonial-slider, dark-mode, hanging-quotes, asymmetrical-carousel`
- **TEST-02** — Perspective Video Testimonial Slider · `perspective-slider, 3d-carousel, video-testimonials, dark-mode-review`
- **TEST-03** — Supply Chain Bento Testimonial Grid · `bento-testimonials, dark-teal-gradient, profile-portraits, clean-corporate`
- **TEST-04** — Asymmetrical Carousel Review Wall · `testimonial-carousel, high-key-social-proof, clean-corporate, slider`
- **TEST-05** — Inverted Contrast Review Board · `testimonial-board-matrix, inverted-color-split, text-marker-highlight, dark`
- **TEST-06** — Symmetrical Social Proof Slider · `testimonial-slider, high-key-social-proof, clean-corporate, symmetrical-carousel`

### Contact Sections

- **CON-01** — Atmospheric Application Contact Form · `contact-hero, glass-form, sky-gradient, overlapping-typography`
- **CON-02** — Brutalist Typographic Form Overlap · `brutalist-grid, overlapping-form, giant-typography, high-contrast-brutalist`
- **CON-03** — Brutalist Capture Form Grid Matrix · `brutalist-form-matrix, neon-yellow-accents, benefits-checklist, dark-mode`
- **CON-04** — High-Contrast Split-Pane Contact Closure · `split-color-closure, neon-orange-pane, form-input-matrix, directory-menu`

### Call-to-Action (CTA) Sections

- **CTA-01** — Scattered Thumbnail Call-to-Action Grid · `scattered-grid, parallax-thumbnails, centered-cta, high-contrast-dark`
- **CTA-02** — Inverted Contrast Dual-Pane Block · `diagonal-cut-portrait, inverted-color-split, large-scale-quote, b2b`
- **CTA-03** — Capsule Closure Conversion Footer · `capsule-conversion-card, geometric-glass-backdrop, directory-link-grid, sub`
- **CTA-04** — Giant Chroma Wordmark Transition Banner · `ribbon-banner, gradient-typography-logo, brutalist-text-cta, sub-footer`

### Minimalist Design Tiers

- **MIN-01** — Asymmetrical Floating Step Matrix · `staggered-bento, giant-typography, gradient-swatches, process-flow`
- **MIN-02** — Asymmetrical Portrait & Capability Split · `split-capability-layout, mosaic-portrait-cards, clean-alignment, b2b-feat`
- **MIN-03** — Minimal Category Grid Showcase · `category-grid, pastel-cards, minimalist-photography, staggered-alignment`
- **MIN-04** — Minimal Balanced Step Walkthrough Block · `step-walkthrough-grid, minimal-icon-wells, symmetrical-text, clean-alignment`

### Organic Field / Clean-Tech Tiers

- **ORG-01** — Alternating Industrial Capability Row · `alternating-grid, b2b-minimalist, warehouse-photography, floating-metrics`
- **ORG-02** — Clean Pastel Radial SaaS Hero · `pastel-bento-hero, text-marker-highlight, radial-gradient, saas-dashboard`
- **ORG-03** — Milestone Progress Checklist Row · `milestone-checklist, dashed-timeline, overlapping-badge, educational-ui`
- **ORG-04** — Frosted Glass Capsule Botanical Showcase · `glassmorphic-capsules, botanical-assets, organic-product-ui, interlocking`
- **ORG-05** — Frosted Glass Capsule Botanical Showcase (Var) *(same as ORG-04)* · `glassmorphic-capsules, panoramic-nature-field, organic-product-ui, align`

### Editorial & Structural Gallery Tiers

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

### B2B Corporate & Fintech Overviews

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
- **B2B-112** — Progressive Path-Morph Transform Rig · `path-morph-rig, dual-state-svg, progress-driven, transformation-story, step-walkthrough-stage`