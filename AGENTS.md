## Cursor Cloud specific instructions

This is a **pure static HTML/CSS site** with no dependencies, no build step, no linter, and no test framework. See `CLAUDE.md` for full architecture details.

### Running the site

```bash
python3 -m http.server 8080
```

Then open `http://localhost:8080/` in a browser. No installation or build step is needed.

### Key caveats

- There is no `package.json`, no `node_modules`, and no npm/yarn/pnpm usage. Do not attempt to run `npm install` or similar.
- There are no automated tests. Verification is visual — open the page in a browser and confirm the glassmorphism cards, gradient backgrounds, and responsive layout render correctly.
- External resources (Google Fonts for Manrope typeface, Pravatar for placeholder avatars) require internet access but are not required for layout/styling to work.
- The default git branch is `main`.
