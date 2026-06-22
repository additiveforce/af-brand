---
name: AF Logo
description: AF logo assets — horizontal wordmark, stacked wordmark, and icon mark. Reference when placing the AF logo in any output. Fetch SVGs at generation time via bash from the af-brand GitHub repo.
document_id: af-logo
version: 2026
last_reviewed: 2026-Q1
review_cadence: on-change
skill_type: resource
layer: both
tier: 2
scope: >
  Fetch instructions and usage rules for all nine AF logo SVG files.
  Files are fetched at generation time from the af-brand GitHub repo —
  never loaded into context as inline SVG.
does_not_cover: >
  AF icon library assets. For icons use af-icons.md.
load_order: 5
load_with: []
dependencies: []
children: []
conflict_resolution:
  - Logo SVGs are brand assets. Never recolor programmatically. Never modify
    geometry, proportions, or structure. Fetch and inline exactly as stored.
---

# AF Logo

Nine logo files. Three formats × three colors. Fetch at generation time — never load SVG into context.

---

## Repo

```
https://raw.githubusercontent.com/additiveforce/af-brand/main/logos/[filename]
```

---

## Files

| File | Format | Use |
|------|--------|-----|
| `AF-Logo-Horizontal-Charcoal.svg` | Horizontal wordmark | Default. Light backgrounds. |
| `AF-Logo-Horizontal-Primary_Blue.svg` | Horizontal wordmark | Accent use. Light backgrounds. |
| `AF-Logo-Horizontal-White.svg` | Horizontal wordmark | Dark backgrounds. |
| `AF-Logo-Stacked-Charcoal.svg` | Stacked wordmark | Compact horizontal space. Light backgrounds. |
| `AF-Logo-Stacked-Primary_Blue.svg` | Stacked wordmark | Compact horizontal space. Accent use. |
| `AF-Logo-Stacked-White.svg` | Stacked wordmark | Compact horizontal space. Dark backgrounds. |
| `AF-Logo-Icon-Charcoal.svg` | Icon mark only | Light backgrounds. |
| `AF-Logo-Icon-Primary_Blue.svg` | Icon mark only | Accent use. |
| `AF-Logo-Icon-White.svg` | Icon mark only | Dark backgrounds. |

---

## Usage rules

- Never recolor the AF logo programmatically — use the correct color variant file
- Never stretch, rotate, or modify logo geometry
- Never use Charcoal or Blue logo on a dark background — use White
- Never use the White logo on a light background — use Charcoal
- Minimum clear space equal to the height of the AF letterform on all sides

---

## Fetch pattern

Use bash to fetch and inline at generation time. SVG is never loaded into Claude's context.

**Single logo fetch:**
```bash
curl -s "https://raw.githubusercontent.com/additiveforce/af-brand/main/logos/AF-Logo-Horizontal-Charcoal.svg"
```

**In Python:**
```python
import requests

def get_logo(filename):
    url = f"https://raw.githubusercontent.com/additiveforce/af-brand/main/logos/{filename}"
    response = requests.get(url, timeout=10)
    response.raise_for_status()
    return response.text

svg = get_logo("AF-Logo-Horizontal-Charcoal.svg")
```

Fetch once per generation session. Inline the returned SVG string directly into the HTML or PPTX output.
