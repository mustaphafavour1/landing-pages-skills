# Site Types

Seven shapes. The first three are drawn from past builds; the last four (business, hybrid, European, mini-business) are defined categories to build toward. The taste rules and the signature-move framework apply to all of them; what differs is which sections belong and — for the business, European, and mini-business types — how heavily the page leans on real photography and how the hero is treated.

## Product landing page

Examples: Allowance, didii, TrashPay.

Typical section inventory: hero, icon-grid feature overview, how-it-works (often per-audience if the product is multi-sided), pricing (even pre-launch — show real numbers behind a waitlist CTA rather than hiding pricing), social proof / testimonials (matched to different personas if multi-sided), a trust or security section, a final CTA that often echoes the hero's headline verbatim as a closing loop, footer.

Distinguishing traits: usually pre-launch or early-stage, so the primary CTA is a waitlist or "get early access" rather than a direct purchase, but it still shows full product detail rather than a vague "coming soon."

## Portfolio / case-study page

Example: Revolut Founder Mode (a designer's own concept pitch, not a real shipped product).

Typical section inventory: hero framed as "[real company] → concept by [name]," a problem statement (why the current thing falls short), the concept's own feature grid, a detailed screen-by-screen breakdown, a "why this matters" section using real numbers from the actual company being reimagined (to justify the exercise's relevance), a designer bio block, "reach out for more info" instead of a waitlist or purchase CTA.

Distinguishing traits: no pricing, no waitlist — the whole page is a pitch for the designer's thinking and taste, not a product people can use today. The bio block and the "why this matters" stats section are close to mandatory here and don't belong on a product page.

## Event / conference page

Example: FlutterBytes Conference.

Typical section inventory: hero with a ticket CTA and key dates, "how it works" or what to expect, a speaker showcase (works well as an interactive wheel or ring rather than a flat grid), a past-editions history or timeline if this isn't the first edition, organizing-team credit (consider framing this in language native to the audience rather than a generic "meet the team"), sponsors, agenda/schedule, apply-to-speak or apply-to-volunteer links.

Distinguishing traits: strongly benefits from an audience-native vocabulary and metaphor somewhere prominent, not just as flavor text, since the entire premise is a gathering of a specific community rather than a generic consumer sell.

## Business page

Examples: a fashion label, a bakery, a café, a salon, a photographer, an interior studio — an established real-world business selling something that already exists, not a startup pitching a future product.

Typical section inventory: an image-forward hero (the product, the space, or the work itself, not an abstract concept), a signature offering or collection showcase (lookbook, menu, service list, gallery), an about/story section grounded in real photography of the people or place, social proof as real customer photos or reviews rather than logo walls, location/hours/contact, and a booking, order, or enquiry CTA. Pricing is usually shown directly (a menu, a price list) rather than hidden behind a waitlist.

Distinguishing traits — this is the important one: **the business page is image-heavy by design.** Aim for roughly **75% of sections to be built around real photography** — the product, the food, the space, the work, the people. The signature-move framework and the animation rules still fully apply, but here they layer *on top of* strong imagery (a lookbook that scrolls or parallaxes, a menu card that reveals detail on hover, a gallery with a considered reveal) rather than substituting an abstract vector concept for a photo. Because real photos carry so much of the weight, this is the type where asking for actual photography up front (per `SKILL.md`'s photo rule) matters most — an image-heavy page built on faked or stock imagery falls apart. If genuine photos aren't available, say so plainly and treat that as a blocker to resolve, not something to paper over with gradients.

## Hybrid

A deliberate mix of two or three of the other types. Examples: a product launch that's also promoting a launch event (product + event), a design studio that sells a product and shows a portfolio of past work (business + case-study), a conference with a paid product attached (event + product).

How to structure it: pick the **dominant type** first — the one that owns the primary CTA and the overall goal — and use its section inventory and spacing as the backbone. Then borrow only the specific sections the secondary type genuinely needs (an event's dated-agenda and ticket block, a case-study's stats-and-bio pair, a business's image-forward gallery) and weave them in where they fit the narrative, rather than bolting a whole second page on the end. Keep one core concept, one type/color system, and one headline mechanism across the whole thing — the mix is in the sections, not in a split personality. Log in the build entry which types were combined and which was dominant, so the pattern is traceable later.

## European website

A clean, restrained, premium-feeling site in the style of high-end European studio work and the best paid Framer templates — lots of calm space, confident typography, real photography, and quiet motion. It uses all the same foundations as the other types (the signature-move framework, the taste rules, the type/color and theme decisions); what makes it its own category is the hero treatment and an overall restraint.

**The hero is deliberately simple and photo-led:**
- Fetch and **download** one or more suitable real photographs from **Unsplash, Pexels, or Pixabay** (all free to use) and use them as the hero's background image(s) — download them into the project as local assets rather than hot-linking, and pick images that genuinely fit the brand's subject, mood, and palette rather than generic filler. Ask the person first if they'd rather supply their own photography.
- Present the image(s) inside a **rounded rectangular frame about 98% of the viewport width** — the signature premium-Framer look — with **corner radius around 20–32px**. The frame sits centered with a small, even gutter on each side.
- **Keep the hero uncomplicated.** No busy signature-visual concept layered on top, no particle systems, no competing animated overlays — the photograph and the headline carry it. The headline still follows the headline rules (never plain, one mechanism), and quiet, tasteful motion is welcome (a slow subtle zoom/parallax on the image, a soft fade-up on the text), but the hard rule about every hero having one signature idea is satisfied *by the framed-photo treatment itself* here — that restraint is the concept.

Typical section inventory: the framed photo hero, a concise intro/positioning statement, a small feature or offering overview, a photography-forward showcase or gallery, social proof, and a simple contact or enquiry CTA. **No waitlist** — this type is not a pre-launch startup pitch. Keep the whole thing simple, but not boring: the interest comes from beautiful imagery, generous space, confident type, and restrained motion rather than from a dense stack of signature concepts.

Distinguishing traits: restraint is the point. Where a product page earns its keep with a distinct signature move in every section, a European site earns it with taste, spacing, photography, and polish. Fewer loud ideas, executed impeccably.

## Mini-business landing page

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

## If it's none of these

Treat it as closest to a product landing page and adapt — the underlying taste rules and the signature-move framework don't depend on which of these seven it is.
