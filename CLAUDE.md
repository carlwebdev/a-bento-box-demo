# CLAUDE.md — AI Assistant Guide for a-bento-box-demo

## Project Overview

**a-bento-box-demo** is a lightweight, static HTML/CSS design prototype exploring the "bento box UI" trend — a modern design aesthetic using glassmorphism, layered cards, and CSS Grid geometry. The project serves as both an interactive showcase and a living style guide.

- **Stack:** Pure HTML5 + CSS3 (no JavaScript, no build tools, no frameworks)
- **Entry point:** `index.html` — open directly in any modern browser
- **Purpose:** Educational design showcase demonstrating a reusable design system

---

## Repository Structure

```
a-bento-box-demo/
├── index.html          # Main single-page application (~232 lines)
├── assets/
│   └── css/
│       └── styles.css  # Complete styling system (~685 lines)
├── README.md           # Project overview and style guide summary
├── hello.txt           # Empty placeholder file (can be ignored)
├── CLAUDE.md           # This file
└── .gitattributes      # Git LF normalization rules
```

There is intentionally no `package.json`, build config, linter, or test framework — this is a static site by design.

---

## Development Workflow

### Running the Project

No installation or build step required:

```bash
# Option 1: Open directly in browser
open index.html

# Option 2: Use any local HTTP server (optional, for testing external resource loading)
python3 -m http.server 8080
# then visit http://localhost:8080
```

### Making Changes

1. Edit `index.html` for structural/content changes
2. Edit `assets/css/styles.css` for visual/layout changes
3. Refresh the browser — no build step needed

### Git Workflow

- Default branch: `master`
- Feature branches follow the pattern: `claude/<description>-<id>`
- Commits are small and descriptive (see history for style reference)
- No CI/CD pipeline is configured

---

## Architecture & Design System

### HTML Structure (`index.html`)

The page is organized into semantic sections:

| Section | Purpose |
|---|---|
| `<header>` | Sticky nav with brand name and links |
| `<section class="hero">` | Introduction with stacked preview cards |
| `<section class="principles">` | 4-card grid of design philosophy |
| `<section class="gallery">` | Interactive component samples (wide/tall card variants) |
| `<section class="style-guide">` | Design token documentation (colors, type, spacing, components) |
| `<footer>` | Contact information |

### CSS Architecture (`assets/css/styles.css`)

The stylesheet uses a component-based structure without CSS custom properties/variables (all values are hardcoded). Key sections:

1. **Reset & Base** — box-sizing, margin reset, font defaults
2. **Header** — sticky glassmorphism nav
3. **Hero** — two-column grid with stacked card preview
4. **Principles** — responsive 4-column card grid
5. **Gallery** — asymmetric grid with `grid-column: span 2` wide cards
6. **Style Guide** — nested demo components
7. **Responsive** — single breakpoint at `720px`

### Design Tokens (hardcoded values to reuse consistently)

**Colors:**
- Background gradient: radial from `#f9f2ff` (lilac) to `#edf8f7` (teal)
- Accent gradient: `#7f5dff` (violet) → `#1fb9ff` (aqua)
- Surface: `rgba(255,255,255,0.65–0.80)` with `backdrop-filter: blur(20–24px)`
- Text primary: `#1a1f2b`
- Text muted: `#5e6688`

**Typography:**
- Font: `Manrope` (loaded from Google Fonts), with system fallbacks
- Weights: 400 (body), 600 (labels/nav), 700 (headings)
- Base size: `16px`

**Spacing & Radii:**
- Border radii: `32px` (large), `24px` (medium), `16px` (small)
- Grid gap: `40px` (hero/gallery), `24px` (principles)
- Component padding: `6px–24px`

**Effects:**
- Shadow: `0 20px 40px rgba(80, 92, 138, 0.18)`
- Hover lift: `translateY(-2px)` + shadow adjustment
- Shimmer animation on waveform visualization

---

## External Dependencies

The project uses two external services (no npm packages):

| Service | URL | Purpose |
|---|---|---|
| Google Fonts | `fonts.googleapis.com` | Manrope typeface |
| Pravatar | `i.pravatar.cc` | Placeholder avatar images |

Both are loaded at runtime. The project works offline for layout/styling; avatar images and custom fonts require an internet connection.

---

## Accessibility Conventions

- Use semantic HTML elements (`<header>`, `<main>`, `<section>`, `<article>`, `<nav>`, `<footer>`)
- Add `aria-label` on interactive or landmark elements
- Use `role="img"` with `aria-label` for decorative SVGs that convey meaning
- Maintain sufficient color contrast (dark text `#1a1f2b` on light surfaces)

---

## Responsive Design

Single breakpoint at `720px`:
- Header nav wraps using `flex-wrap`
- Hero, principles, and gallery collapse to single-column layouts
- Sticky positioning reverts to `static` on mobile

When adding new sections, follow the pattern: desktop multi-column grid → mobile single-column via `@media (max-width: 720px)`.

---

## Conventions for AI Assistants

### What to do

- **Keep it static** — do not introduce JavaScript unless explicitly requested
- **Preserve the glassmorphism aesthetic** — semi-transparent surfaces, blur effects, and the violet-to-aqua accent gradient are central to the design
- **Follow existing naming patterns** — BEM-inspired class names (e.g., `.gallery-card`, `.principle-card`, `.style-guide`)
- **Maintain semantic HTML** — use the correct sectioning elements, not generic `<div>` wrappers
- **Match the design token values** exactly when extending components (colors, radii, shadows listed above)
- **Respect the single breakpoint** — all responsive adjustments belong inside `@media (max-width: 720px)`

### What to avoid

- Do not add a `package.json` or build toolchain unless the user explicitly requests a migration
- Do not add JavaScript event listeners for effects that can be achieved with CSS (`:hover`, `:focus`)
- Do not introduce CSS custom properties (variables) unless refactoring the entire stylesheet — mixing hardcoded values and variables creates inconsistency
- Do not add new external dependencies without noting the internet requirement
- Do not modify `.gitattributes` or Git configuration files

### Adding new components

1. Add the HTML in the appropriate `<section>` in `index.html`
2. Add corresponding CSS at the bottom of the relevant section in `styles.css`
3. Follow existing card structure: outer container with `border-radius`, `background` rgba, `backdrop-filter`, `box-shadow`
4. Add hover state with `transform: translateY(-2px)` and shadow adjustment
5. Add mobile override inside the existing `@media (max-width: 720px)` block

---

## Key Files Quick Reference

| File | Lines | Role |
|---|---|---|
| `index.html` | ~232 | All markup, structure, content |
| `assets/css/styles.css` | ~685 | All styles, layout, animation |
| `README.md` | 18 | Human-readable project intro |
| `CLAUDE.md` | this file | AI assistant guide |
