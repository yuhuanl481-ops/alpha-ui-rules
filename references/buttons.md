# Button specification

Source: Figma component set `402:1029`. Use `<a-button>`; map Error intent to `danger`. Centralize Alpha sizing and state styling.

Color dependency: Figma defines the primary button family with orange semantics. Use the centralized `--primary-brand-600` default, `--primary-accent-700` hover, and `--primary-text-800` pressed emphasis. Never implement a primary button with `blue/500`; blue is information-only.

Variants: primary/Error intent; primary/secondary/text hierarchy; default/hover/active/disabled state; 40/36/32/28px height; no/leading/trailing/icon-only icon.

| Height | Font/line | Weight | Horizontal padding | Radius |
|---:|---:|---:|---:|---:|
| 40px | 14/20px | 500 | 16px | 10px |
| 36px | 14/20px | 500 | 16px | 8px |
| 32px | 14/20px | 500 | 12px | 8px |
| 28px | 13/18px | 500 | 8px | 8px |

- Text buttons have a 72px minimum width; do not apply it to icon-only buttons.
- At 40px height icons are 20px. Leading icon: 4px gap, 14px icon-side padding, 16px opposite. Trailing icon: 6px gap, 10px icon-side padding, 16px opposite. Preserve equivalent optical asymmetry at other sizes.
- Icon-only buttons are square and require an accessible name.
- Primary default/hover/active/disabled use `--primary-brand-500`, `--primary-hover-400`, `--primary-text-800`, `--primary-disabled-300`.
- Secondary retains a border; text hierarchy has no border or filled background. Error variants preserve geometry and use error semantics.
- Use real `disabled`, CSS state selectors, and accessible focus-visible. Never render persistent hover/active states in templates.

Mapping: primary → `type="primary"`; secondary → default button plus centralized Alpha theme/wrapper; text → `type="text"`; Error → add `danger`.
