---
name: AF Design Gestalt Principles
description: AF compositional logic and slide archetypes. Apply when designing any AF presentation or document layout. Covers visual hierarchy, gestalt principles, and argumentative structure.
document_id: af-design-gestalt-principles
version: 2026
last_reviewed: 2026-Q1
review_cadence: biannual
skill_type: primitive
layer: both
tier: 1
scope: >
  Compositional logic for AF layouts. Covers gestalt principles, visual
  hierarchy, and the slide archetypes used to structure arguments. Bridges
  design philosophy and execution.
does_not_cover: >
  Specific PPT grid coordinates or layout dimensions — those are in
  AF_Slide_Canvas. Component-level craft (cards, dividers, labels) is in
  AF_Design_UI_Craft.
load_order: 3
load_with:
  - af-design-principles
dependencies:
  - af-design-principles
children: []
conflict_resolution:
  - Where this file and AF_Design_Principles conflict, AF_Design_Principles
    takes precedence as the parent file. Where this file and AF_Slide_Style
    conflict on a PPT-specific decision, AF_Slide_Style takes precedence.
---

# AF Design — Gestalt and Compositional Logic
**Scope:** Compositional techniques and slide archetypes. Colour, type size, and grid coordinates live in their own files.

---

## 1. Core visual logic

**Hierarchy through contrast.** Every slide is built on one dominant element. Contrast is created through weight, not decoration. Nothing competes with the dominant element.

**Restraint as signal.** Whitespace is a decision, not an absence. Sparse is intentional. Density is reserved for data slides and is controlled there.

**Two-speed reading.** The fast read (headline + anchor) delivers the argument in under two seconds. The slow read (body + detail) rewards attention but is never required for comprehension. A slide that requires the slow read to land has failed.

---

## 2. Compositional techniques

### The dual headline
Two lines, visually differentiated, working as a unit.

- Line 1 states the condition, context, or problem — neutral.
- Line 2 delivers the reframe, insight, or payoff — charged.
- Together they create cause/effect or tension/resolution. Reading one without the other leaves the argument incomplete.
- Visual differentiation (weight, colour) mirrors semantic difference — they look different because they mean different things.

The primary voice of the presentation. Appears on nearly every content slide.

### The section label
Small, monospace, uppercase. Sits above the headline, subordinate. Functions like a chapter heading — orients without consuming attention.

### The numerical anchor
Large numerals as visual entry points in multi-column layouts. Not labels. They create rhythm and imply sequence before the eye reads a word.

### The horizontal rule as structural joint
Thin lines separating zones, not decorating them. Mark categorical boundaries — label from headline, headline from content, header row from table body. Structural only.

---

## 3. Slide archetypes

Every slide belongs to one of these. The archetype is chosen before content is placed.

**A — Cover / Title.** Headline dominates. Metadata subordinate. Confident stillness. Nothing moves the eye except the headline.

**B — Section Statement.** Opens every major section. Dual Headline is the content. If stripped to the headline alone, the point would still land.

**C — Card Grid.** Equal-weight cards. The grid implies parity — no card more important than another. Consistent internal grammar (identity zone → content zone) lets the reader learn the structure once and apply it to all subsequent cards.

**D — Three-Column Numbered.** Three columns, each anchored by a numeral. The sequence (01, 02, 03) implies progression or causality. Horizontal rule at the top of each column acts as a visual full stop. Equal weight across columns.

**E — Split Panel.** Narrative panel holds context. Smaller distinct panel holds a single piece of evidence — a stat, a callout, a warning. The juxtaposition does the work: narrative says what; evidence says how much or why it matters.

**F — Detail Table.** Structured evidence for an argument already made. Tables are confirmatory, not persuasive. Strict structure: dominant header row, consistent row rhythm, distinct total row. Reader moves top-to-bottom, left-to-right without ambiguity.

**G — Next Steps / CTA.** Three items, no more. Each item is a complete, actionable statement. Visual treatment (numbered badge + full-width row) implies a checklist — these things will be done, in this order. The slide does not ask; it proposes.

**H — End / Brand Close.** Brand mark only. A diagonal division creates visual energy at the point of closing. Last impression is the brand, not a data point.

---

## 4. Gestalt principles in use

**Proximity.** Related items group tightly; unrelated items separate. Space between groups carries meaning.

**Similarity.** Recurring visual patterns (dual headline, numerical anchor, section label, thin rule) teach the reader a grammar. Once learned, cognitive load drops.

**Continuation.** The eye is led in a deliberate sequence. Horizontal rules at column tops create a visual line across before the eye moves down. Vertical divisions create reading lanes.

**Figure / ground.** Dominant element sits forward through weight contrast, never through literal depth (shadow, gradient). The ground is always flat.

**Common fate.** Items that travel through the deck together (01/02/03 phases) share visual treatment. The reader understands they belong to the same system before reading the content.

---

## 5. Tension and resolution

Visual and argumentative tension mirror each other.

**Visual tension.** Heavy, dominant headline sits above a sparse content zone. Weight imbalance creates tension resolved by reading the body.

**Argumentative tension.** Line 1 names a problem or condition. Line 2 resolves, reframes, or escalates it. The reader experiences a micro tension/resolution cycle on every slide.

**Sequential tension.** Phases are presented as insufficient in isolation (e.g. Stabilise is explicitly "not a solution"). The sequence builds a case that only resolves at the end.

---

## 6. What the system refuses

- **No decoration.** No gradients, drop shadows, textures, ornamental elements. Every visual element must be justified by function.
- **No scale inflation.** When something is very large, it is because it is the most important thing on the slide — not because large things look more designed.
- **No competing focal points.** One dominant element per slide. Supporting elements genuinely support.
- **No slide that requires reading to understand.** The argument is graspable from a fast scan. Slides that bury their point in body copy have failed.
- **No transition for its own sake.** Progression is argumentative, not theatrical. Each slide opens, deepens, or closes. No slide exists merely to exist.

---

## 7. Voice and visual alignment

Written voice and visual language operate on the same principles.

| Writing principle | Visual equivalent |
|---|---|
| Short declarative sentences | Sparse slides with dominant headlines |
| Tension in the headline pair | Visual contrast between headline lines |
| No filler language | No decorative elements |
| Insight on line 2, not line 1 | Accent treatment on line 2 |
| Numbers as standalone evidence | Stats isolated as visual anchors |
| Candid, unhedged | Heavy weight type, no softening effects |
| Three things, not five | Three columns, three phases, three next steps |

The work feels coherent because words and visuals make the same argument in the same way. Neither decorates the other. Both are the argument.
