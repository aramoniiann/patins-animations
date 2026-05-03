# Copilot instructions for patins-animations

Purpose: Provide concise, repository-specific guidance for future Copilot sessions.

---

## Build / test / lint
- No build, test, or lint scripts detected (no package.json, no test files).
- Preview locally:
  - Open index.html in a browser (entry point: index.html).
  - Or run a simple static server from the repo root (examples):
    - npx http-server .
    - npx live-server .
  - These are suggestions only — the repo contains plain HTML/CSS and does not require a toolchain.

## High-level architecture
- Single-page static site. Entry point: index.html.
- Styles are in styles/; index.css imports the component CSS files (global.css, header.css, hero.css).
- assets/ contains:
  - icons/ (SVG icon set)
  - images/ (bitmap images)
  - hero/ (hero-specific SVGs/PNG)
- Fonts loaded from Google Fonts in index.html.
- The hero section uses a CSS keyframes animation (slideUp) applied to multiple <span> lines inside the H1.

## Key conventions and notes (important for Copilot)
- Styles use a nested, SCSS-like syntax inside header.css and hero.css (e.g., nested rules and `&` selectors). Treat these files as authored for a preprocessor (Sass/PostCSS nesting). If editing CSS, prefer working with a tool that supports nesting or flattening to valid CSS before previewing.
- Design tokens and variables live in styles/global.css (:root) — colors, font stacks, and sizing variables are centralized here.
- Component CSS split: one file per logical area (header.css, hero.css). index.css simply imports these.
- Icons are SVGs; prefer reusing assets/icons SVG files rather than duplicating markup.
- Small interactive UI patterns to note:
  - Header uses an absolute-position badge (<a> > span) for cart count.
  - Buttons use classes `.button`, with modifiers `.buy` and `.play`.
  - The hero text animates by stacking multiple <span> elements inside an inline container — keep that structure if changing animations.
- Language: index.html sets `lang="pt-br"` and content uses Portuguese copy. Keep locale in mind for text updates.

## Files/Configs checked
- Looked for README.md, CONTRIBUTING.md, package.json, test folders, and common AI assistant configs (CLAUDE.md, .cursorrules, AGENTS.md, .windsurfrules, CONVENTIONS.md, etc.) — none were found.

---

If changes are needed (add build scripts, tests, or a README), update this file to include exact commands and locations. Keep guidance minimal and concrete.
