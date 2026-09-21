# Checkbox specification

Source: Figma component set `815:4869`. Use `<a-checkbox>` and its `checked`, `indeterminate`, and `disabled` APIs; do not redraw marks in page markup.

- Slot: 16×16px.
- Main square: 14×14px, 4px radius.
- Inner inset: 12×12px, 3px radius.
- Indeterminate mark: 8×8px, 2px radius.
- Values: unchecked, checked, indeterminate.
- States: default, hover, active, disabled.
- Hover uses brand hover treatment; active uses brand accent treatment.
- Disabled unchecked uses strong stroke plus subtle background. Disabled checked/indeterminate uses disabled semantics and cannot activate.
- Disable label and control as one unit. Preserve keyboard focus-visible.

