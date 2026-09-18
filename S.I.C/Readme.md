# S.I.C — Sport in Cinema

WEDE5020 — Web Development (Introduction)
Student: Vilakazi · ST10537650

## What this repository contains

A 6-page static website (`home.html`, `about.html`, `services.html`,
`gallery.html`, `enquiry.html`, `contact.html`), one external stylesheet
(`css/style.css`), a `Documents/` folder with the original planning
artefacts (proposal, sitemap, wireframes), and an `images/` folder with
the site's photos and logo. **No JavaScript is used anywhere in the
site** — the mobile navigation menu is a pure‑CSS checkbox/label toggle.

## Part 2 — CSS Styling & Responsive Design

This section maps the work done for Part 2 directly onto the brief so
it's easy to mark against the rubric.

| Requirement (from the brief) | Where it's done |
|---|---|
| External stylesheet linked on every page | `css/style.css`, linked from the `<head>` of all 6 pages |
| Base style / reset | `*{box-sizing:border-box}`, base `body`/`img`/`a` rules at the top of `style.css` |
| Typography styles (`font-family`, `font-size`, `font-weight`, `line-height`, `letter-spacing`) | `h1–h4`, `.eyebrow`, `.lede`, nav and button type rules |
| Layout via CSS Grid / Flexbox | `.hero__grid`, `.grid-2`, `.grid-3`, `.gallery-grid` (Grid); `.site-header .wrap`, `.hero-actions`, `.btn` (Flexbox) |
| Visual styles (`color`, `background-color`, `border`, `box-shadow`) | `.card`, `.fixture`, `.form-panel`, `.eyebrow .dot` pulse glow |
| Pseudo-classes (`:hover`, `:focus`, `:active`) | `.btn`, `.card`, `.fixture`, `.gallery-item`, `.field input/select/textarea`, `.main-nav a` |
| Breakpoints / media queries | `@media (max-width: 860px)`, `760px`, `700px`, `640px`, `560px` in `style.css` |
| Relative units (`em`, `rem`, `%`) | Spacing, type sizes and the `.wrap` container are set in `rem`/`%` throughout `style.css` |
| Responsive images (`srcset`, `sizes`) | `gallery.html` — every `<img>` has a `srcset`/`sizes` pair plus explicit `width`/`height` to avoid layout shift |
| Test & iterate on multiple screen sizes | See "Manual testing" below — add your own screenshots here once captured |

### Background pattern

The diamond-lattice background from the original design was kept
deliberately (per feedback) rather than replaced. It's built purely
from layered CSS gradients on `body` (see the `--s`, `--_g`, `--_c`
custom properties near the top of `style.css`) — no image file is
needed, and it now uses the same colour palette as the rest of the
redesign (`--pattern-c`, `--panel-2`) so it sits behind the content
instead of clashing with it.

### Manual testing

Tested by resizing the browser window and using browser dev tools'
device toolbar at three breakpoints:

- Desktop (≥ 1024px) — multi-column grid layout
- Tablet (~768px) — 2-column grids, nav still inline
- Mobile (≤ 480px) — single-column stacked layout, nav collapses
  behind the "☰ Menu" checkbox toggle

*(Insert before/after screenshots for each breakpoint here as
required by the submission checklist.)*

## Changelog

### Part 2 — Feedback edits from Part 1
- Fixed a broken stylesheet path: the HTML linked to `css/style.css`
  (lowercase) while the folder on disk was `CSS/` (uppercase). This
  worked locally on case-insensitive filesystems (Windows/macOS) but
  would 404 on a case-sensitive host such as GitHub Pages. Renamed
  the folder to `css/` so the link resolves everywhere.
- Replaced the inline `style="..."` attributes and table-based layout
  used on every page with an external stylesheet and semantic
  CSS classes (`.hero`, `.card`, `.fixture`, `.grid-2`, `.grid-3`, etc.),
  per the Part 2 brief.

### Part 2 — Gallery expansion & menu fix
- Added 8 new photos from a real Ster-Kinekor visit to `images/`
  (`gallery-6.jpg` … `gallery-13.jpg`) and to the Gallery page's photo
  grid, each with its own `alt` text, caption and `srcset`/`sizes`
  pair — 13 photos total.
- Added a pure-CSS rotating 3D cube (`.cube-stage` / `.gallery` in
  `css/style.css`) to the top of the Gallery page, cycling through 6
  of the photos on an animated colour backdrop. Adapted from a
  supplied CSS snippet that animated the real `<body>` background
  directly — scoped it to its own `.cube-stage` panel instead, so it
  doesn't override the site's diamond background pattern on every
  other page.
- Fixed the mobile nav menu so it never needs its own internal
  scrollbar when the visitor is pinch-zoomed in: swapped `vh` for
  `dvh` (tracks the actual visual viewport), removed `overflow-y:
  auto` in favour of `overflow: hidden` with a flexible `gap` so the
  6 links always fit, and locked background scrolling while the menu
  is open with a `body:has(#nav-toggle:checked)` rule — still no
  JavaScript.

### Part 2 — New Part 2 work
- Added a full design system to `css/style.css`: colour and font custom
  properties, a typography scale, reusable button/card/form components.
- Rebuilt the layout of every page using CSS Grid (`.grid-2`, `.grid-3`,
  `.hero__grid`, `.gallery-grid`) and Flexbox (header, nav, button
  groups).
- Added visual styling: card borders, panel backgrounds, box-shadow
  pulse animation on the "live" indicator dot, hover/focus/active states
  across buttons, cards, fixture rows, form fields and the gallery grid.
- Added responsive breakpoints (860px / 760px / 700px / 640px / 560px)
  covering desktop, tablet and mobile, switching grids to fewer columns
  and collapsing the nav into a slide-in mobile menu.
- Converted the Gallery page's photos to use `srcset`/`sizes` and
  explicit `width`/`height` attributes for responsive image loading.
- Replaced the JavaScript-dependent hamburger menu markup with a
  JavaScript-free checkbox/label toggle so the whole site works with
  **no `<script>` tags and no `.js` files** — required by this
  submission.
- Kept the CSS-only diamond background pattern from the previous
  version, recoloured to match the new palette.

### References
- MDN Web Docs — CSS Grid Layout: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout
- MDN Web Docs — Flexbox: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Basic_concepts_of_flexbox
- MDN Web Docs — Responsive images (`srcset`/`sizes`): https://developer.mozilla.org/en-US/docs/Web/HTML/Guides/Responsive_images
- MDN Web Docs — Using media queries: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries/Using_media_queries
- CSS-Tricks — The "checkbox hack" for JS-free toggles: https://css-tricks.com/the-checkbox-hack/
- Google Fonts — Montserrat, Open Sans, Space Mono: https://fonts.google.com/

## Submission checklist (from the brief)
- [x] HTML files updated and included in this folder
- [x] External CSS stylesheet created and linked on every page
- [ ] Screenshot evidence of desktop/tablet/mobile added to this README
- [ ] Commit these changes with descriptive messages and push to the
      remote repository
- [ ] Submit the GitHub repository link to the LMS
