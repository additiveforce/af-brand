---
name: AF Design Charts
description: Chart design principles for all AF outputs. Apply when creating any data visualisation. Covers chart type selection, integrity rules, two-speed principle, and charts vs tables decisions.
document_id: af-design-charts
version: 2026
last_reviewed: 2026-Q1
review_cadence: biannual
skill_type: primitive
layer: both
tier: 1
scope: >
  Medium-agnostic chart design principles. Covers chart type selection via
  CHART_TYPE_SELECT hook, data integrity rules, the two-speed principle, and
  the CHART_OR_TABLE decision gate. Applies to all AF outputs.
does_not_cover: >
  PPT-specific chart execution, R templates, or python-pptx output specs —
  those are in AF_Slide_Charts. This file covers principles; AF_Slide_Charts
  covers PPT execution.
load_order: 4
load_with: []
dependencies:
  - af-design-principles
children: []
conflict_resolution:
  - This file governs chart type selection and integrity for all outputs.
    For PPT execution specifics, AF_Slide_Charts takes precedence. Where the
    two files conflict on a principle, flag the conflict — they should not
    disagree.
---

# AF Design — Charts
**Scope:** Core knowledge. Applies to all Additive Force outputs that contain data visualisation — presentations, reports, documents, digital, and any future format. Colour tokens, type sizes, and output specifications are defined in medium-specific files.

---

## What a Chart Is For

A chart is an argument made visible. It is not decoration, not a data dump, and not evidence that work was done. Every chart earns its place by answering one question better than words or a table could. If it cannot do that, it should not exist.

Four tests apply to every chart before it is considered complete:

1. **Information** — is the data accurate, proportional, and honestly represented?
2. **Function** — does the chart serve a clear argument?
3. **Form** — is the visual treatment appropriate to the data type?
4. **Story** — does the chart make the argument legible without explanation?

All four must be present. A chart that passes three is unfinished.

---

## Core Rules

These apply to every chart in every medium. No exceptions.

**The title states the argument, not the subject.**
"LinkedIn outperforms all paid channels" is a title. "Channel performance index" is a label. The title must deliver the insight — what the data proves, not what it shows. A viewer should be able to read the title and understand the point without reading the chart.

**Direct labels or axis scale. Never both.**
If values are directly labelled on bars, data points, or line ends, the axis scale is redundant non-data ink. Remove it. If the scale is present for reading intermediary values, remove the direct labels. Carrying both adds visual weight without adding information. Choose one and remove the other.

**Bar chart baselines start at zero. Always.**
A bar chart encodes quantity as length. Cutting the baseline distorts the length relationship and misrepresents the data. No exceptions. If the meaningful variation is too small to be visible from zero, a bar chart is the wrong chart type — use a line chart with a contextualised axis instead.

**Colour encodes meaning. It is never decorative.**
One colour signals importance. Everything else recedes to neutral. If adjacent bars are the same category with no meaningful distinction between them, they get the same colour. Using multiple colours to make a chart look more designed is chartjunk.

**No axis title when the unit is obvious from context.**
If the axis label says "MONTHS" and the data already shows Jan, Feb, Mar — the axis title is noise. Remove it. Retain axis titles only when the unit is genuinely ambiguous without them.

**No chart border, no chart background fill.**
A box around a chart signals the designer was unsure the chart had earned its space. The chart inherits the ground it sits on. Remove the border.

**No 3D. No gradients. No shadows.**
3D perspective distorts perceived lengths. Gradients create false emphasis. Shadows add visual weight with zero informational value. These are software defaults — they are never correct.

**Never use a legend when direct labels are possible.**
A legend forces the reader to look away from the data, find the swatch, decode the label, look back, and make the connection. That is maximum cognitive friction for minimum information. Label directly. Reserve legends only for cases where direct labelling is genuinely impractical — more than 4 series in close proximity.

**Data order follows reading order.**
Enter data in logical sequence. For ranked comparisons, the default is largest to smallest — left to right on a column chart, top to bottom on a horizontal bar chart. This matches the natural reading direction and makes the hierarchy immediately legible. For positive/negative diverging data, positive values sit at the top or right, negative at the bottom or left.

**Numbers flush right. Text flush left.**
This applies in tables, annotations, and any context where numbers and text labels coexist. Right-aligned numbers allow the reader to compare magnitudes by scanning down the column. Left-aligned text labels allow the reader to scan down the list. Never centre-align either.

---

## The Two-Speed Principle

Every chart is designed to be read at two speeds simultaneously.

**The fast read (under 3 seconds):** The macro pattern — the trend, the dominant bar, the outlier — should be visible without reading any labels. If the point requires reading to discover, the visual encoding has failed.

**The slow read (30+ seconds):** Specific values, annotations, and supporting detail reward closer attention. Present but subordinate — they do not compete with the macro signal.

Design sequence: establish the macro signal first. Then add the minimum supporting detail required. If adding a label, gridline, or annotation does not serve one of these two speeds, remove it.

---

## Chart Selection

### CHART_TYPE_SELECT

```
IF argument = change_over_time AND series ≤ 2 → LINE
IF argument = change_over_time AND series > 2 → SMALL_MULTIPLES (line)
IF argument = ranking OR category_comparison → HORIZONTAL_BAR (long labels) OR COLUMN (time series)
IF argument = single_highlighted_vs_others → COLUMN with colour emphasis
IF argument = part_of_whole AND segments ≤ 5 → PIE or DONUT
IF argument = part_of_whole AND segments > 5 → STACKED_BAR or combine smallest → "Other" + breakout
IF argument = relationship_two_variables → SCATTER
IF argument = multi_attribute AND polygon_profile_meaningful → RADAR
IF argument = single_key_figure → DISPLAY_STAT (typographic — not a chart)
IF argument = same_metric_many_categories → SMALL_MULTIPLES
IF argument = diverging_comparison → TORNADO
```

**Do not use:**
- PIE: segments > 5, magnitude argument, non-adjacent comparison needed
- LINE: categorical data with no continuity between points
- RADAR: < 5 attributes, polygon shape not meaningful, or > 3 series — beyond 3 the chart becomes unreadable regardless of treatment

**Multi-series radar rule:** No fill on any series — stroke only. Colour and weight work inversely: darker series get thinner strokes, lighter series get thicker strokes. Lead company / primary subject takes the most saturated colour at standard weight. This prevents any comparator from dominating while keeping all series distinct.
- BUBBLE: only when 3 quantitative dimensions must be encoded simultaneously; always label directly

### PIE_SEGMENT_POSITION

```
IF segments have unequal values:
  largest → 12 o'clock RIGHT, clockwise
  second largest → 12 o'clock LEFT, anticlockwise
  continue alternating
IF all segments similar in value:
  start 12 o'clock RIGHT → proceed clockwise in data order
```

---

## Annotations

Annotations bridge the gap between data and meaning. Always directly adjacent to the element they describe — never floating, never substituted by a legend.

Use when: flagging an outlier, marking a threshold or benchmark, identifying a significant period on a line chart, calling out the single most important data point.

The spatial relationship between an annotation and its data point is not decorative — it is the meaning. If it is not adjacent, it is not an annotation — it is a legend.

---

## Gridlines

### GRIDLINE_SELECT

```
IF direct_labels present → NO gridlines
IF scale_reference needed AND complexity = medium → HORIZONTAL only, light weight
IF complexity = complex (scatter, radar, multi-axis) → BOTH axes OR concentric rings, light weight
```

Gridlines are the lightest visible element on the chart. If they compete with the data, they are too heavy.

---

## Small Multiples

Use when: same metric across multiple categories, single chart would be too crowded, showing how a relationship changes across subgroups.

Rules:
- Same chart type across all panels
- Same scale across all panels — varying axis range destroys comparability
- Same colour treatment across all panels
- Minimal labelling per panel — shared grammar does the work once

---

## Charts vs Tables

### CHART_OR_TABLE

```
IF data has single dominant argument (trend, ranking, proportion, magnitude) → CHART
IF reader needs to look up specific values by name → TABLE
IF multiple attributes compared simultaneously, no dominant argument → TABLE
IF exact figures required over pattern recognition → TABLE
DEFAULT → CHART
```

When a table is unavoidable and has a dominant numeric column, add an inline data bar column adjacent to the numbers. Solid fill rectangle scaled so largest value = full cell width. Does not replace the number — sits alongside it.

---

## Integrity

Charts shape how people think and make decisions. They must represent data honestly.

**The Lie Factor (Tufte):** The visual representation of a change must be proportional to the actual change in the data. A numerical change of 20% shown as a graphical change of 200% has a lie factor of 10. Keep the lie factor as close to 1.0 as possible.

**Proportional encoding:** Always choose the encoding that makes quantities most accurately perceptible. Length (bars) is more accurately perceived than area (bubbles), which is more accurate than angle (pie slices). Prefer the more accurate encoding.

**Missing or estimated data:** Must be visually distinguished from confirmed data. Use a dashed line, a different opacity, or a direct annotation. Never present estimated values with the same visual weight as confirmed values.

---

## Quality Check

Run before considering any chart complete.

**Integrity**
- [ ] Bar chart baseline at zero?
- [ ] Quantities proportionally represented — lie factor ≈ 1.0?
- [ ] Missing or estimated data visually distinguished?

**Clarity**
- [ ] Title states the argument, not just the subject?
- [ ] Direct labels or axis scale — not both?
- [ ] Legend removed where direct labels are possible?
- [ ] Chart border removed?
- [ ] No 3D, gradients, or shadows?
- [ ] Gridlines recessive or absent?
- [ ] Colour encoding meaning — not decoration?

**Two-speed test**
- [ ] Macro pattern (trend, dominant bar, outlier) visible in under 3 seconds without reading labels?
- [ ] Specific values reward closer reading without cluttering the macro view?
