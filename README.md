# Bento Box UI Prototype

A lightweight static exploration of the bento box UI trend. The layout features layered glassmorphism cards, playful grid geometry, vibrant gradients, and tactile hover states to highlight what sets this design approach apart.

## Getting started

Open `index.html` in a browser to view the prototype.

## Style guide

The prototype relies on a compact set of design tokens and reusable patterns:

- **Typography:** Manrope is the primary typeface, paired with system fallbacks to maintain legibility across platforms. Base font size is 16px with semibold weights used for navigation, buttons, and key labels.
- **Color palette:** A soft radial background gradient anchors the layout while glassmorphism surfaces (`rgba(255, 255, 255, 0.4–0.8)`) provide depth. Accent gradients blend violet (`#7f5dff`) and aqua (`#1fb9ff`) for interactive highlights.
- **Spacing & radius:** Generous border radii (16–32px) and a 40px grid gap in hero and gallery layouts create the signature bento-box geometry. Components use balanced padding ranges (6–24px) to reinforce tactile affordances.
- **Effects:** Subtle box-shadows (`0 20px 40px rgba(80, 92, 138, 0.18)`) and blur filters enhance the layered aesthetic. Hover states translate elements by 2px and adjust shadows for responsive feedback.
- **Components:** Hero badges, CTA and ghost buttons, principle cards, avatar rows, and utility progress rings share consistent tokens to ensure cohesion when recomposing layouts.
