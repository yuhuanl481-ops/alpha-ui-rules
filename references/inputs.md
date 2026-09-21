# Input specification

Source: Figma node `457:5479`. Use `<a-input>`, `<a-input-search>`, and `<a-textarea>` or shared Alpha wrappers. Centralize states.

Shared: `line` or `fill`; heights 40/36/32px; default/hover/focus(inputting)/disabled/error; 8px radius; 12px horizontal padding; PingFang SC Regular 14/20px. Placeholder uses `--text-soft-neutral-500`, value `--text-strong-900`, default border `--stroke-sub`, disabled surface `--bg-weak-50`, error `--state-error-base`. Hover/focus uses the brand semantic token. Use real focus and disabled behavior.

## Single line

Large/Medium/Small are 40/36/32px, each with 12px horizontal and 6px vertical padding. Error text is 12/18px below the field. Combined error examples are 60/56/54px; these are not input heights.

## Search

- Same height system and radius; minimum source width 200px.
- Internal gap 8px; Large icon 20px; clear action 16px while inputting.
- Search action divider is 1×14px with 12px gap.
- Disabled state disables input, clear, and search actions together.

## Textarea

- Box height 76px; padding 12px horizontal and 8px vertical; radius 8px.
- Text/placeholder 14/24px; helper gap 2px; count 12px with 4px horizontal inset.
- Normal count aligns right. Error row shows 12/18px error text left and count right; current count may use error color at/over limit.
- Connect errors to Ant Design Vue form validation and associate messages programmatically.
