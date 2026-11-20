---
name: AF Icons
description: 330+ custom AF SVG icons. Reference when any visual artifact, HTML output, dashboard, or document requires iconography. Icons are fetched at generation time from the af-icons GitHub repo via af_icons.py — never loaded into context. Live count and full index live in the repo README, not here.
document_id: af-icons
version: 2026
last_reviewed: 2026-Q2
review_cadence: on-change
skill_type: resource
layer: both
tier: 2
scope: >
  Fetch instructions, naming convention, and usage rules for the AF icon library.
  ~330 icons (live count in the repo README), kebab-case naming, 24×24 viewBox.
  Icons are fetched at generation time via af_icons.py — SVG content is never
  loaded into Claude's context. The authoritative icon list is NOT duplicated
  here; resolve names from the repo README or `af_icons.py --list`.
does_not_cover: >
  AF logo marks — use af-logo.md for the AF wordmark and icon mark.
load_order: 6
load_with: []
dependencies: []
children: []
conflict_resolution:
  - Icon SVGs are brand assets. Do not modify geometry.
  - If an exact name match is not found, choose the closest semantic match.
  - The repo README is the canonical name list. Use names exactly as listed there
    when calling af_icons.py.
---

# AF Icons

330+ custom SVG icons. 24×24 viewBox, single-colour solid style. Fetched at generation time —
never loaded into context.

The library grows over time. **This file intentionally does not list the icons or pin an exact
count** — the live index lives in the repo so it can't go stale. Resolve names from there.

---

## Repo (source of truth)

```
https://raw.githubusercontent.com/additiveforce/af-icons/main/[name].svg
```

- **Full index** (every name + category + aliases, with the live count):
  `https://raw.githubusercontent.com/additiveforce/af-icons/main/README.md`
- **Name list, programmatic:** `python3 af_icons.py --list`  (filter: `--list --filter arrow`)

---

## Fetch pattern

Use `af_icons.py` for all icon fetches. The script handles caching, fill normalization, and
error handling.

**Single icon:**
```python
from af_icons import get_icon

svg = get_icon("ai-chip")                   # fill="currentColor"
svg = get_icon("ai-chip", color="#2563eb")  # explicit hex fill
```

**Multiple icons:**
```python
from af_icons import get_icons

icons = get_icons(["ai-chip", "focus-group", "evp-framework"])
# returns: {"ai-chip": "<svg...>", "focus-group": "<svg...>", ...}
```

**Via bash:**
```bash
python3 af_icons.py ai-chip
python3 af_icons.py --color "#2563eb" ai-chip focus-group
```

---

## Usage rules

- Always fetch via `af_icons.py` — never construct raw GitHub URLs manually in production.
- Inline the returned SVG string directly into HTML or PPTX output.
- Never use `<img src="">` — always inline.
- Scale with `width` and `height` attributes or CSS.
- Color via `fill` or `currentColor` — do not hardcode colors into SVG geometry.
- When multiple icons could fit, prefer the most specific name (e.g. `chart-bar` over `chart`).
- **To find an icon name:** fetch the repo README index, or run `python3 af_icons.py --list`.
  Names are kebab-case and chosen for meaning, not appearance.
- If an exact name isn't found, pick the closest semantic match from the index.
