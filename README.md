## Text Orientation Demo

### Overview
- **What**: Minimal HTML/CSS demo showing vertical typesetting using `writing-mode` and `text-orientation`.
- **Why**: Compare sideways vs upright glyph behavior for Latin and CJK text, and illustrate line and column progression across modes.

### How it works
The page renders multiple examples to demonstrate flow and glyph orientation:

- **Horizontal (horizontal-tb)**: lines left→right; blocks top→bottom.
- **Vertical RL, mixed**: `writing-mode: vertical-rl; text-orientation: mixed;`
  - Lines top→bottom; columns right→left. Latin appears sideways; CJK upright.
- **Vertical RL, upright**: `writing-mode: vertical-rl; text-orientation: upright;`
  - Lines top→bottom; columns right→left. All glyphs upright; often pair with `white-space: nowrap` to stack Latin letters.
- **Vertical LR, mixed**: `writing-mode: vertical-lr; text-orientation: mixed;`
  - Lines top→bottom; columns left→right.
- **Vertical LR, upright**: `writing-mode: vertical-lr; text-orientation: upright;`
  - Lines top→bottom; columns left→right.
- **Sideways RL**: `writing-mode: sideways-rl;`
  - Lines top→bottom; columns right→left; all glyphs are set sideways.
- **Sideways LR**: `writing-mode: sideways-lr;`
  - Lines top→bottom; columns left→right; all glyphs are set sideways.

Notes on properties:
- **`text-orientation`** controls glyph orientation within vertical flow: `mixed` vs `upright`.
- **`white-space: nowrap`** prevents breaks between upright Latin letters so they remain in a single stacked run.

### Browser support
- Widely supported in modern browsers. See: [MDN: writing-mode](https://developer.mozilla.org/en-US/docs/Web/CSS/writing-mode), [MDN: text-orientation](https://developer.mozilla.org/en-US/docs/Web/CSS/text-orientation), and [Can I use](https://caniuse.com/?search=writing-mode).

### Notes
- Prefer CSS `writing-mode` over rotating blocks with `transform: rotate(...)` for correct line layout, selection, and accessibility.
- When mixing scripts, verify letter spacing and wrapping behavior; `upright` often benefits from `white-space: nowrap`.

