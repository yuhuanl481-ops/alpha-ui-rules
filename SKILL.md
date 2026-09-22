---
name: alpha-ui-rules
description: Use when creating, modifying, or reviewing Vue 3 interfaces that must follow the Alpha design system, especially typography, colors, buttons, checkboxes, inputs, hover, focus, active, disabled, and error states.
---

# Alpha UI Rules

Keep ordinary product UI consistent with Alpha Design System in Vue 3 + TypeScript + Vite projects using Ant Design Vue and SCSS/CSS.

## Workflow

1. Inspect existing theme tokens, shared styles, and wrappers.
2. Prefer Ant Design Vue over recreating controls.
3. Read only the relevant reference: [colors](references/colors.md), [buttons](references/buttons.md), [checkboxes](references/checkboxes.md), or [inputs](references/inputs.md).
4. Put reusable states in theme tokens, shared wrappers, or global component overrides—not individual pages.
5. Review changed `.vue`, `.scss`, and `.css` files before finishing.

## Rules

- Use semantic CSS variables for ordinary text, backgrounds, borders, icons, and states. No new raw color literals in page styles.
- Primitive palette values are sources for semantic tokens, not page usage guidance.
- Figma defines the product primary semantic group as orange: `primary-brand` → `orange/600`, `primary-accent` → `orange/700`, and `primary-text` → `orange/800`; use the full mapping in [colors](references/colors.md). Never substitute the information blue ramp for primary.
- Use PingFang SC with approved system fallbacks unless the project already defines the approved stack.
- Do not invent typography, component dimensions, radii, or interaction colors.
- Interactive controls require hover, focus-visible, active, disabled, and error behavior where applicable.
- Disabled controls use the native/component `disabled` API, not only a cosmetic class.
- Never remove keyboard focus without an accessible replacement.
- Icon-only controls require an accessible name and should have a tooltip when their meaning is not obvious.

## Exceptions

Illustrations, data visualization, campaigns, gradients, images, and explicitly art-directed Figma regions may use nonstandard colors. Keep the exception local and add `alpha-ui-exception` with a short reason. Exceptions cannot redefine shared Button, Checkbox, Input, Search, or Textarea states.

## Final review

- Replace ordinary raw colors with semantic variables.
- Pair every changed `font-size` with an approved line-height and weight.
- Verify button size, hierarchy, state, and icon arrangement.
- Verify checkbox unchecked, checked, indeterminate, hover, active, and disabled behavior.
- Verify input default, hover, focus/inputting, disabled, and error behavior.
- Confirm component states are centralized and report intentional exceptions.
