# AF icons

Interface icons are [Phosphor](https://phosphoricons.com), Regular weight, from the official repository
(`github.com/phosphor-icons/core`). Icons take the text colour, or screen blue for the active state.

AF draws its own icons only where Phosphor has none, in Phosphor's style and weights. They live in `icons/<weight>/`
and use `fill="currentColor"`, like Phosphor's own files:

| Icon | Use |
|---|---|
| `grid-four-top-left`, `-top-right`, `-bottom-left`, `-bottom-right` | One quadrant of a 2×2 matrix, the named cell solid |

Weights: Regular (no suffix), Thin, Light, Bold, Duotone. Fetch one with:

```bash
curl -s "https://raw.githubusercontent.com/additiveforce/af-brand/main/icons/regular/grid-four-top-left.svg"
```

The Brand 1.0 icon set stays in the af-icons repository, tagged `brand-1.0`, for reference.
