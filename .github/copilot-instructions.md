<!-- Copilot / AI agent instructions for the Footmark static site -->
# Quick context

This repository is a small static marketing site for Footmark (land-plot management). It contains plain HTML pages and a single CSS file. There are no build tools, server code, or tests in this repo — it's served directly (GitHub Pages) from the `main` branch. The presence of `CNAME` (value: `footmark.co.in`) indicates a GitHub Pages custom domain.

# High-level architecture & intent

- Static-site only: pages are simple HTML files under the repo root (`index.html`, `product.htm`, `contact.htm`) and styles live in `css/footmark_styles.css`.
- No JS, backend, or build pipeline in this repo — changes are immediate on push (after Pages publish). Do not attempt to add complex build steps without discussing with maintainers.
- Assets: images like `logo.png` are referenced from the site root (see `index.html` header). Keep same relative paths when editing.

# What an AI coding agent should know and do first

- Preserve the repo's static structure. Edit HTML/CSS in-place. Don’t introduce build tooling or package manifests unless the maintainer asks.
- Keep file naming conventions: pages use `.htm` for `product.htm` and `contact.htm` (index uses `.html`). Match the existing extension when adding pages.
- Routing is purely relative links. Examples:
  - Header nav links: `index.html`, `product.htm`, `contact.htm` (see `index.html` nav block).
  - CSS: linked as `css/footmark_styles.css` in page `<head>`.

# Common tasks & exact locations (examples you can act on)

- Change hero text or stats: edit `index.html` — look for `<section class="hero">` and `<div class="stats">`.
- Update product copy: `product.htm` in the `<section class="about-content container">` block.
- Edit contact form fields or labels: `contact.htm` — `<form class="contact-form">`.
- Tweak global styles, colors, spacing: `css/footmark_styles.css` (root selectors and `.hero`, `.features`, `.footer-container`). Example color tokens: primary teal (#007b82) and accent (#ffb700).

# Deployment & validation notes

- Deployment: changes are published via GitHub Pages. `CNAME` indicates custom domain `footmark.co.in` — do not alter `CNAME` unless maintainer requests.
- Preview locally: open the HTML files in a browser (double-click or `Live Server` tools). There's no build step.

# Conventions, gotchas, and patterns

- Accessibility / semantics: pages already include `meta viewport` and basic headings; follow existing class names and grid structure when adding markup.
- CSS organization: a single stylesheet controls layout and palette. Add new styles to `css/footmark_styles.css` and keep names consistent with existing BEM-like patterns (`hero-content`, `feature-card`, `footer-container`).
- Keep external links and email/phone values intact (contact values appear in multiple files). If you change contact email/phone, update every file and mention it in the PR.

# When to open a PR versus direct commit

- Small content fixes (typos, copy tweaks) can be committed directly if you have permission. For any UI, UX, or structural change (new pages, layout updates, adding JS), open a PR and include screenshots of the before/after and how you validated locally.

# Example concise instructions for a PR description

- What I changed: (one-line summary)
- Files touched: `index.html`, `css/footmark_styles.css`
- Why: (reason)
- How tested: opened `index.html` locally in browser; verified layout at 320px and 1280px widths.

# Non-goals / do not do without maintainers' approval

- Do not add server-side code, CI/CD workflows, or package manifest files (e.g., `package.json`) in this repo unless requested.
- Do not change `CNAME` or DNS-related values.

# Helpful references in repo

- `index.html` — main landing, hero, stats, nav.
- `product.htm` — product details and mission copy.
- `contact.htm` — contact form and contact details.
- `css/footmark_styles.css` — single stylesheet controlling layout and theme.

If any of these notes are unclear or you want added examples (for changing colors, adding a small JS widget, or adding a new page), tell me which area you'd like more detail on and I'll iterate. 
