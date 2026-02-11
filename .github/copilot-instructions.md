# Copilot instructions for this repository

Purpose
- Help AI coding agents make small, safe changes to this static portfolio site (HTML/CSS, no build step).

Big picture
- Single-page, static portfolio. Entry point: [index.html](index.html).
- All static assets live under `assets/` (subfolders: `css/`, `images/`, `icons/`, `cv/`, `favicon/`, `mockups/`, `wireframes/`).
- Styling: Bootstrap 5.3 is loaded via CDN; custom overrides live in [assets/css/style.css](assets/css/style.css).
- No backend or build pipeline in this repo — changes are served as plain files (GitHub Pages).

Key patterns & concrete examples
- Navigation & sections: update section content or anchors in [index.html](index.html). Navbar uses anchor links (e.g. `href="#about"`).
- Hero / CTAs: modify text or links directly in [index.html](index.html). CTAs use `.btn-brand`, `.btn-brand-primary`, `.btn-link-cta` classes.
- Project cards: images live in `assets/images/` and tags use the `.tag` utility class. Example: `<span class="tag">React</span>`.
- Spacing helpers: the project uses small utility classes in `style.css` (e.g. `.py-64`, `.mb-20`, `.pt-20`) — prefer those over arbitrary inline styles.
- Form UI: the contact form is client-side only (no server processing). Do not add server-side assumptions.
- External links: existing pattern requires `target="_blank" rel="noopener noreferrer"` for external links — preserve this.

Local preview & developer workflow
- Quick preview (from repo root):

  ```bash
  python3 -m http.server 8000
  # then open http://localhost:8000
  ```

- Alternatively use VS Code Live Server extension for rapid refresh.
- There are no test or build commands to run. Changes are validated by manual browser checks and GitHub Pages deployment.

Conventions to follow
- Assets: add images to `assets/images/` and icons to `assets/icons/`; use webp where present.
- Styling: update `assets/css/style.css` for global styles and utilities. Keep Bootstrap CDN reference intact unless you intentionally migrate to a local copy or a build.
- Accessibility: keep semantic tags (`header`, `main`, `section`, `footer`) and `alt` text for images.
- Links & security: external links must include `target="_blank" rel="noopener noreferrer"`.
- Deployment: site is served from repository root (GitHub Pages). Keep `index.html` and `404.html` at the root for correct routing.

When making edits
- Small content changes: edit `index.html` and update `assets/` as needed. Keep commits focused and atomic.
- Adding a page: put the new HTML in the repo root, add nav/footer links in `index.html`, and ensure relative asset paths (e.g. `assets/css/style.css`) remain correct.
- Image updates: keep filenames lowercase and avoid spaces; update references in `index.html`.

What not to assume
- There is no Node, npm, or other build tooling in this repo.
- The contact form does not submit to a server; do not attempt to wire server-side handlers unless adding separate backend infrastructure.

Where to look
- Entry: [index.html](index.html)
- Styles: [assets/css/style.css](assets/css/style.css)
- README for project rationale and live URL: [README.md](README.md)

If anything here is unclear, ask for a pointer to the exact file/section you plan to change.
