---
name: AF Design UI Craft
description: Component-level craft for AF layouts. Apply when making design decisions about cards, labels, dividers, callouts, and information density. Translates UI thinking into slide and document design.
document_id: af-design-ui-craft
version: 2026
last_reviewed: 2026-Q1
review_cadence: biannual
skill_type: primitive
layer: both
tier: 1
scope: >
  Twelve UI component patterns applied to slide and document design. Covers
  cards, labels, dividers, callouts, badges, and information density decisions.
  The bridge between UI craft and AF presentation execution.
does_not_cover: >
  Chart design or data visualisation decisions — those are in AF_Design_Charts.
  PPT-specific grid placement is in AF_Slide_Canvas.
load_order: 4
load_with: []
dependencies:
  - af-design-principles
children: []
conflict_resolution:
  - Where this file and AF_Slide_Style conflict on a PPT component rule,
    AF_Slide_Style takes precedence.
---

# AF Design — UI Craft
**Scope:** Translates UI component thinking into slide and document craft. The goal is not to make slides look like interfaces — it is to borrow the information-structuring logic UI design has already refined.

---

## How to use this file

For each design decision, ask: what information problem am I solving? The patterns below map common problems to the UI thinking that solved them. Use the logic, not the literal form.

The universal failure mode: borrowing the visual without the job. A chip that isn't labelling category membership is cargo-culting. A card border that isn't grouping a bounded unit is decoration. Test: what would be lost if this element were removed?

---

## 01 / The Chip — category membership without noise

**Problem:** Label something as belonging to a category without the label competing with primary content.

**AF application:** The eyebrow / section label. Small (10pt), monospace, uppercase, loose tracking. Categorically different in appearance from the headline — that difference is how the reader knows they are different kinds of information.

**Failure mode:** Eyebrow that competes with the headline — wrong weight, wrong size, too much colour.

---

## 02 / The Card — bounded units of parallel information

**Problem:** Present multiple items with internal structure (title, description, value) without the whole thing reading as noise.

**AF application:** Any parallel item set — three phases, four personas, six attributes. Card logic: consistent internal spacing, consistent element order, equal visual weight. The reader learns the grammar on the first card and applies it automatically — cognitive load drops to near zero.

**The border question.** A visible border is justified only when the background doesn't provide sufficient separation. Pure white ground with generous spacing: proximity and alignment suffice, no border. Dark background with items close together: a hairline (0.25pt) may be necessary. Earn the border.

**Failure mode:** Cards with inconsistent internal structure. The grammar breaks and the reader has to relearn each card individually.

---

## 03 / The Divider — hierarchy between zones

**Problem:** Create a categorical break between two zones of different kinds of content, at minimum visual cost.

**AF application:** Horizontal rule as structural joint. Top of numbered columns, between section label and headline, between metadata zone and content zone. 0.25–0.5pt. Never thicker. Never coloured for emphasis.

Front cover accent line (6pt, Primary Blue) is not a divider — it is a structural anchor and brand element. Its weight is intentional: the heaviest non-typographic element on the slide, giving the eye a resting point before it reads the metadata below.

**Failure mode:** A divider between every element. When everything is divided, nothing is differentiated.

---

## 04 / The Alert / Callout — categorical difference, not emphasis

**Problem:** Flag information that is a different kind of thing, not just more important.

**AF application:** The split panel evidence block. Stat, key figure, warning, critical caveat in its own contained zone, visually unlike the narrative text. The signal: the rules changed here. This is data, not prose.

**Failure mode:** Using alert-style treatment for emphasis. If everything important gets a coloured background, the signal is lost. Reserve contained high-contrast treatment for genuinely different content.

---

## 05 / The Label / Value Pair — structured metadata

**Problem:** Present multiple pieces of metadata without requiring the reader to parse which label belongs to which value.

**AF application:** Front cover project descriptor and date. "TIMEFRAME / 3–5 WEEKS" and "INVESTMENT / US $99,250" on phased approach slides. Label is small, uppercase, monospace, muted — the key. Value is the content. The asymmetry is the information structure made visible.

**Failure mode:** Label and value at the same visual weight. The reader has to read both to determine which is which. The efficiency is lost.

---

## 06 / Progressive Disclosure — reveal depth without overwhelming

**Problem:** Present content with a summary layer and a detail layer without forcing both at once.

**AF application:** Two-speed reading, applied architecturally. Headline/anchor pair is the summary — argument in under two seconds. Body copy and detail are the disclosure layer — present for readers who want it, not required for those who don't.

At the deck level: section openers are summary slides. A reader who only saw the openers would understand the argument. A reader who read everything would understand it in greater depth. Both are valid.

**Failure mode:** Body copy that restates the headline. The disclosure layer adds no depth — just the summary repeated.

---

## 07 / The Badge — identity at a glance

**Problem:** Give an object an identity marker (number, status, category) legible without reading full text.

**AF application:** Leading-zero chapter numbers (01, 02, 03) on section openers. Numbered anchors on three-column layouts. The number is not the content — it is the identity marker. Its job is to be found, not read.

**Failure mode:** Badge that competes with the content it labels. If chapter number and title are the same size, one will dominate — and it won't always be the right one.

---

## 08 / The Empty State — intentional absence

**Problem:** Handle a state with no content to show without the layout reading as broken.

**AF application:** Whitespace as a design decision. A sparse slide is not unfinished — it is a slide that lets one thing breathe. The absence is the design.

When a visual area has no asset, go full-width and let the text own the slide. Empty space in the visual area signals the text is strong enough alone. That is a positive signal.

**Failure mode:** Filling the visual area with decorative icons or generic stock to avoid the appearance of emptiness. This draws attention to the absence rather than making it feel intentional.

---

## 09 / The Tooltip / Annotation — contextual detail without interruption

**Problem:** Provide additional context for a specific element without cluttering the primary view.

**AF application:** Chart annotations, data labels, callout lines. Clarify a specific point — peak, outlier, threshold — without interrupting the whole. IBM Plex Mono, 8pt, directly adjacent to the thing they describe. Never floating. The spatial relationship is the meaning.

**Failure mode:** A legend. Maximum cognitive load for minimum information. Direct labelling is always preferred.

---

## 10 / The Skeleton / Placeholder — structural honesty

**Problem:** Represent a slot that will hold variable content without the placeholder being mistaken for finished content.

**AF application:** Client logo placeholder on the front cover. Text fields like `<SEMANTIC PROJECT CATEGORY DESCRIPTION>`. Muted container, instructional text — visually uncomfortable, demanding attention and resolution.

**Failure mode:** A placeholder that blends into the slide. If it looks like content, it gets treated as content and left in place.

---

## 11 / The Navigation / Breadcrumb — orientation in a sequence

**Problem:** Tell the reader where they are in a larger structure at minimum footprint.

**AF application:** The section label / eyebrow. Every content slide carries one. Multi-part eyebrows (`02 / DEFINE / OUTPUTS`) are full breadcrumbs: deck position, section, subsection. Always in the same position, same format — the reader learns to find it without looking.

**Failure mode:** Eyebrow position or format that changes between slides. Inconsistency destroys the orientation function.

---

## 12 / Density Calibration — information load as a design variable

**Problem:** Design for content that varies dramatically in density, from a single headline to a 42-row table.

**AF application:** One job per slide. When content exceeds what a single slide can hold at appropriate type size and whitespace, it is split. The slide is the component. The component has a maximum load.

**Practical test:** If meeting type size minimums (8pt data, 10pt body) requires removing whitespace or reducing margins, the slide is over capacity. Split it.

**Failure mode:** Reducing type size to fit more content. Solving a layout problem by degrading legibility. The correct response is always structural — a new slide, a different layout, or less content — never smaller type.
