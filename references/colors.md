# Color rules

## Figma source-of-truth and primary-color status

The checked Figma exports are `01-Tokens` and `03-颜色调色板` (nodes `5:312` and `5:295`). The accompanying Figma screenshot explicitly defines the product primary semantic group as orange:

| Semantic name in Figma | Primitive source | CSS token |
|---|---|---|
| `primary-text` | `orange/800` | `--primary-text-800` |
| `primary-accent` | `orange/700` | `--primary-accent-700` |
| `primary-brand` | `orange/600` | `--primary-brand-600` |
| `primary-` | `orange/300` | `--primary-300` |
| `primary-` | `orange/200` | `--primary-200` |
| `primary-` | `orange/50` | `--primary-50` |

Use `orange/600` as the default product primary/brand fill. Use `orange/700` for accent/hover emphasis and `orange/800` for primary text or pressed emphasis. The lighter `orange/300`, `/200`, and `/50` values are supporting backgrounds/borders, not the default button fill. Never substitute `blue/500`; blue is reserved for information semantics. Red/green/orange state ramps remain distinct from the primary semantic group.

Use semantic tokens in page and component code. Sources: Figma `01-Tokens` and `03-颜色调色板`.

| Purpose | Token | Source |
|---|---|---|
| Dominant/strong/support text | `--text-dominant-950`, `--text-strong-900`, `--text-support-800` | `neutral/950`, `/900`, `/800` |
| Secondary/muted/soft text | `--text-sub-700`, `--text-muted-600`, `--text-soft-neutral-500` | `neutral/700`, `/600`, `/500` |
| Disabled/white text | `--text-disabled-300`, `--text-white-0` | `neutral/350`, `/0` |
| Surfaces | `--bg-white`, `--bg-weak-50`, `--bg-soft-100`, `--bg-sub-hover-150`, `--bg-sub-200`, `--bg-strong-hover-250` | matching neutral scale |
| Disabled button | `--bg-button-disabled` | `neutral/300` |
| Borders | `--stroke-strong`, `--stroke-sub` | semantic direct values |
| Success | `--state-success-base/light/lighter` | `green/500`, `/200`, `/50` |
| Information | `--state-information-base/light/lighter` | `blue/500`, `/200`, `/50` |
| Error | `--state-error-base/light/lighter` | `red/500`, `/200`, `/50` |

Use `--icon-*` tokens for icons. Primitive `red`, `green`, `blue`, `orange`, and `neutral` variables belong only in the semantic-token definition layer.

## Primary semantic tokens

The screenshot establishes these mappings. Keep them centralized in the theme layer (convert the primitive values to CSS variables there): `--primary-brand-600` → `orange/600`, `--primary-accent-700` → `orange/700`, `--primary-text-800` → `orange/800`, `--primary-300` → `orange/300`, `--primary-200` → `orange/200`, `--primary-50` → `orange/50`.

Legacy names may exist in older component guidance (`--primary-brand-500`, `--primary-hover-400`, `--primary-disabled-300`, `--primary-border-hover-200`, `--primary-bg-light-50`). Do not assign them guessed values; migrate them to the explicit mappings above when a theme is updated.

When the brand mapping is added, record it as a table in this file and update the corresponding CSS variables in one centralized theme layer. A component must not silently substitute a palette token.

## Source cautions

- Figma `text/soft-blue-400` resolves to `neutral/400`; normalize the code name to `--text-soft-neutral-400`.
- Figma `text/disabled-300` resolves to `neutral/350`; preserve its semantic meaning rather than inferring from the suffix.
- Outside an `alpha-ui-exception`, flag raw hex, rgb(a), hsl(a), named colors, and page-scoped Ant component state colors.
