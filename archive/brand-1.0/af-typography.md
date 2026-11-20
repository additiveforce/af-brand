---
name: AF Typography
description: "AF type system for all outputs. Apply when making typographic decisions. Three typefaces: Poppins Bold, IBM Plex Serif Light, IBM Plex Mono. Defines roles, hierarchy, and weight discipline."
document_id: af-typography
version: 2026
last_reviewed: 2026-Q1
review_cadence: on-change
skill_type: primitive
layer: both
tier: 1
scope: >
  Type system for all AF outputs. Three typefaces with defined roles: Poppins
  Bold (display/headlines), IBM Plex Serif Light (body), IBM Plex Mono (data,
  labels, eyebrows). Covers hierarchy, weight discipline, and size guidance.
does_not_cover: >
  PPT-specific type sizes in pt values or EMU coordinates. Those are in
  AF_Slide_Style. This file defines the type system; AF_Slide_Style defines
  its PPT application.
load_order: 3
load_with: []
dependencies: []
children: []
conflict_resolution:
  - This file defines typeface roles. AF_Slide_Style defines the precise PPT
    size scales. Where the two files specify different values, AF_Slide_Style
    takes precedence for PPTX work.
---

# AF Typography
**Scope:** Core knowledge. Defines the Additive Force type system. Applies to all outputs. Specific sizes and spacing are defined in artefact-specific files.

---

## Typefaces

Three typefaces. No others.

| Typeface | Role |
|----------|------|
| Poppins Bold | Display — headlines, subheadings, titles |
| IBM Plex Serif Light | Body — narrative text, prose, explanatory copy |
| IBM Plex Mono | Data and labels — all numerical content, categories, annotations, eyebrows, captions, table content |

The contrast between these three is intentional and load-bearing. Poppins Bold is assertive and geometric. IBM Plex Serif Light is considered and readable. IBM Plex Mono is precise and technical. Together they create a hierarchy that is legible before a word is read.

---

## Roles

### Display — Poppins Bold
Used for: headlines, titles, subheadings, card titles, numbered callouts, accent lines.
Never used for: body copy, data, captions, labels.
Weight: Bold only. No other weights.
Case: Sentence case. Never title case. Never all caps.

### Body — IBM Plex Serif Light
Used for: narrative text, prose, explanatory copy, supporting argument.
Never used for: data, labels, headings, anything inside a chart or table.
Weight: Light only. No other weights.
Case: Sentence case.

### Data and Labels — IBM Plex Mono
Used for: all numerical data, chart labels, axis labels, table content, eyebrow labels, section markers, annotations, captions, slide numbers, timestamps.
Never used for: narrative body copy, headlines.
Weight: Regular (400) for most uses. Medium (500) for emphasis within data contexts only.
Case: Uppercase for category labels, section markers, eyebrows. Sentence case for descriptive content within data.

---

## Hierarchy Logic

The type hierarchy communicates structure before content. A viewer should be able to read the hierarchy — understand what is a heading, what is a label, what is body — without reading the words.

**Eyebrow / Section Label**
- Typeface: IBM Plex Mono
- Case: Uppercase
- Tracking: Loose
- Colour: Primary Blue
- Purpose: Orients the viewer. Where are we? What section? What category?
- One per unit. Sits above the headline.

**Headline**
- Typeface: Poppins Bold
- Case: Sentence case
- Colour: Deep Indigo (primary), Primary Blue (accent — second clause or keyword only)
- Purpose: States the claim. The primary argument of the unit.
- One per unit.

**Accent Line**
- Typeface: Poppins Bold
- Case: Sentence case
- Colour: Primary Blue
- Purpose: Optional. Used for two-part headlines where the primary clause is Deep Indigo and the accent or second clause is Primary Blue. Used deliberately — not every headline needs one. Never more than one per unit.

**Subheading**
- Typeface: Poppins Bold
- Case: Sentence case
- Colour: Primary Blue (default) or white on dark theme
- Purpose: Secondary label. Card titles, numbered items, named sections within a unit.

**Body**
- Typeface: IBM Plex Serif Light
- Case: Sentence case
- Colour: Deep Indigo (light theme), theme-appropriate tint (dark theme)
- Purpose: Narrative support. Explains, contextualises, qualifies the claim.

**Data / Chart / Caption**
- Typeface: IBM Plex Mono
- Case: Uppercase for labels, sentence case for descriptive content
- Purpose: All quantitative content, axis labels, chart annotations, table cells, captions.

---

## Weight Discipline

Poppins Bold for display. IBM Plex Serif Light for body. The contrast between them is the system. Do not introduce intermediate weights. Do not bold individual words within body copy — use a subheading or accent line instead.

---

## No Inline Emphasis

Do not bold, italicise, or underline individual words within a body paragraph. If something needs emphasis, it belongs in a subheading or accent line — not embedded in prose. Inline formatting fractures the typographic colour of a body text block and signals that the hierarchy is doing insufficient work.

---

## Line Length

Body text reads best at 55–65 characters per line. Reduce font size or constrain column width before extending line length. Long lines increase reading fatigue and signal a layout that hasn't been properly considered.

---

## Typographic Colour

Typographic colour is the overall tone and texture of a text block as perceived before the words are read. A page with consistent typographic colour looks considered. Mixed weights, erratic sizes, and inconsistent spacing destroy it. The three-typeface system produces natural typographic colour when applied correctly — trust the system.
