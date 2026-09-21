# Color rules

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

## Pending brand tokens

Preserve these names but do not treat Figma fallback hex values as final: `--primary-brand-500`, `--primary-hover-400`, `--primary-accent-700`, `--primary-text-800`, `--primary-disabled-300`, `--primary-border-hover-200`, `--primary-bg-light-50`.

## Source cautions

- Figma `text/soft-blue-400` resolves to `neutral/400`; normalize the code name to `--text-soft-neutral-400`.
- Figma `text/disabled-300` resolves to `neutral/350`; preserve its semantic meaning rather than inferring from the suffix.
- Outside an `alpha-ui-exception`, flag raw hex, rgb(a), hsl(a), named colors, and page-scoped Ant component state colors.

