---
name: AF Color System
description: Additive Force colour tokens for all non-PPT outputs. Reference when specifying colours for web, documents, or reports. Tokens are fetched from af-color-system.json in the af-brand GitHub repo — main tokens summarised here for quick reference.
document_id: af-color-system
version: 2026
last_reviewed: 2026-Q1
review_cadence: on-change
skill_type: primitive
layer: primitive
tier: 1
scope: >
  Brand colour tokens for all AF outputs except PowerPoint. Covers primary,
  secondary, neutral, and utility colours. Full stacks in af-color-system.json
  in the af-brand repo.
does_not_cover: >
  PPT-specific colour tokens. For PowerPoint, use af-color-system-ppt.json
  exclusively. Never apply values from this file to PPTX work.
load_order: 3
load_with: []
dependencies: []
children: []
conflict_resolution:
  - This file governs colour for all non-PPT outputs.
  - af-color-system-ppt.json governs colour for all PPT outputs. These two
    systems must never be cross-applied. If in doubt about the output medium, ask.
---

# AF Color System — Non-PPT

All non-PPT outputs. Full token stacks are in `af-color-system.json` in the af-brand repo.

```
https://raw.githubusercontent.com/additiveforce/af-brand/main/af-color-system.json
```

---

## Main tokens

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

**Note:** Deep-Indigo-950 (`#13131f`) is the **primary dark web surface**; Deep-Indigo-900 (`#1c1b2b`) is the raised/adjacent panel. Web only — not for presentations or other brand materials.

**Primary blue on dark:** On dark backgrounds, Primary Blue is a **large-text / UI accent only** — headlines, large figures, icons. Not for body text or small labels: Primary-Blue-800 cannot reach 4.5:1 contrast on any dark background (it caps at ~4.06:1 on black), so small blue text on dark is physically unreachable; 3:1 for large/UI is the bar. Small text on dark uses white or a light Deep-Indigo tint.

Primary Blue extends to darker shades **1000–1300** (see `af-color-system.json`) for deep UI surfaces.

---

## Fetch pattern

```python
import requests

def get_colors():
    url = "https://raw.githubusercontent.com/additiveforce/af-brand/main/af-color-system.json"
    response = requests.get(url, timeout=10)
    response.raise_for_status()
    return response.json()

colors = get_colors()
```
