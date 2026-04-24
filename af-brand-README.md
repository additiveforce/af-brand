# AF Brand

Additive Force brand assets. Single source of truth for logo, color, and typography. All assets are fetched at runtime — any update to this repo is immediately live.

**Repository:** `https://github.com/additiveforce/af-brand`

---

## Accessing assets

```
https://raw.githubusercontent.com/additiveforce/af-brand/main/[filename]
```

---

## Logo

Three formats × three colors = nine files.

| File | Use |
|------|-----|
| `AF-Logo-Horizontal-Charcoal.svg` | Default. Light backgrounds. |
| `AF-Logo-Horizontal-Primary_Blue.svg` | Accent use on light backgrounds. |
| `AF-Logo-Horizontal-White.svg` | Dark backgrounds. |
| `AF-Logo-Stacked-Charcoal.svg` | Compact horizontal space. Light backgrounds. |
| `AF-Logo-Stacked-Primary_Blue.svg` | Compact horizontal space. Accent use. |
| `AF-Logo-Stacked-White.svg` | Compact horizontal space. Dark backgrounds. |
| `AF-Icon-Charcoal.svg` | Icon mark only. Light backgrounds. |
| `AF-Icon-Primary_Blue.svg` | Icon mark only. Accent use. |
| `AF-Icon-White.svg` | Icon mark only. Dark backgrounds. |

**Usage rules:**
- Never recolor the AF logo programmatically
- Never stretch, rotate, or modify logo geometry
- Never use the Charcoal or Blue logo on a dark background — use White
- Never use the White logo on a light background — use Charcoal
- Minimum clear space equal to the height of the AF letterform on all sides

---

## Color system

**File:** `af-color-system.json`

**Scope:** All non-PPT outputs — web, documents, HTML reports. Do not apply to PowerPoint — use the PPT-specific color file for PPTX work.

### Palettes

| Palette | Main token | Hex |
|---------|-----------|-----|
| Charcoal | Charcoal-900 | `#202020` |
| Charcoal (light) | Charcoal-50 | `#fafafa` |
| Deep Indigo | Deep-Indigo-900 | `#1c1b2b` |
| Primary Blue | Primary-Blue-800 | `#2563eb` |
| Secondary Red | Secondary-Red-600 | `#e53e3e` |
| Secondary Amber | Secondary-Amber-700 | `#f59e0b` |
| Secondary Jade | Secondary-Jade-400 | `#22c55e` |
| Secondary Teal | Secondary-Teal-700 | `#0891b2` |
| Secondary Purple | Secondary-Purple-400 | `#8b5cf6` |

Each palette runs 50–900. Fetch the full JSON for all values.

**Note:** Deep-Indigo-950 (`#13131f`) is website only — for contrast between adjacent dark sections. Not for use in presentations or other brand materials.

---

## Typography

**File:** `af-typography.md`

Three typefaces. No others.

| Typeface | Role |
|----------|------|
| Poppins Bold | Display — headlines, titles, subheadings |
| IBM Plex Serif Light | Body — narrative text, prose, explanatory copy |
| IBM Plex Mono | Data and labels — numbers, categories, eyebrows, captions, annotations |

**Key rules:**
- Bold only for Poppins. Light only for IBM Plex Serif. No other weights.
- Sentence case always. Never title case. Never all caps except IBM Plex Mono category labels.
- No inline emphasis — no bolding or italicising within body copy
- Body text: 55–65 characters per line maximum
- Fetch the full file for hierarchy logic, role definitions, and weight discipline

---

## Updating brand assets

Update the file in this repo. Claude fetches assets at runtime — no skill file changes required.
