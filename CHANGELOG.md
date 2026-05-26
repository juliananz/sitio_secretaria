# Changelog

All notable changes to the Secretaría de Economía de Coahuila website
modernization are documented here.

The format is loosely based on [Keep a Changelog](https://keepachangelog.com/).
Dates use ISO 8601 (YYYY-MM-DD). Branding constraints defined in `CLAUDE.md`
(header logos, institutional palette, footer, main navigation) are preserved
across all changes unless explicitly authorized.

## [Unreleased] — branch `module-1-redesign-poc`

### Added
- Favicon for every `*-propuesta.html` page. Generated `img/favicon.png`
  (32×32) by compositing the white institutional logotype
  (`img/LOGOTIPO-PRINCIPAL-BLANCO.png`) onto a gold (`#DAAB06`) background so
  it stays visible on light browser tabs, and added
  `<link rel="icon" type="image/png" href="img/favicon.png">` to each page
  `<head>`. Note: the source is a wide logotype, so at 32px it renders as a
  thin band; a dedicated square mark would read better and is flagged for
  future work.
- Added a full-width portada banner to `index-propuesta.html`, between the nav
  and the hero, mirroring how the production `index.html` uses it. Added a
  `.portada` rule to `css/redesign.css` (`width:100%; height:auto; display:block`
  — full-width, responsive, proportions preserved). Path corrected to `img/…`
  (no root `img/` exists) and a descriptive `alt` added for accessibility;
  administration branding overlays in the image are preserved.

### Fixed
- Social media icons rendered as blank circles in the footer of every
  `*-propuesta.html` page. Cause: Font Awesome was loaded via a **Kit**
  (`kit.fontawesome.com/eb496ab1a0.js`), which is domain-locked and refuses
  to load on non-whitelisted/`file://` origins, so no glyphs were injected —
  only the circular `.footer__redes` link backgrounds remained visible. Fix:
  switched all 21 pages to the origin-independent public Font Awesome 6
  stylesheet on cdnjs. Also modernized the social links: `fa-twitter` →
  `fa-x-twitter` (the X brand mark), each link given a descriptive
  `aria-label` and its decorative `<i>` marked `aria-hidden="true"`, and the
  YouTube link/icon removed (the account does not exist). Remaining links:
  Facebook, X, Instagram.
- Banner image was not loading (rendered as a thin broken-image strip). The
  asset filename on disk used a decomposed (NFD) accent while the HTML used a
  precomposed (NFC) `í`, so the byte sequences differed and the request 404'd.
  Renamed `img/Economía_Portada.png` → `img/economia-portada.png` (safe ASCII,
  via `git mv`) and updated the reference in `index-propuesta.html`. Note: the
  production `index.html` still points at the old name via an already-broken
  `../img/…` path, so production behaviour is unchanged.
- Replicated the redesign language across the whole site: 20 new standalone
  `*-propuesta.html` review pages that share `css/redesign.css`. Originals are
  left untouched; the redesign is fully additive. Inter typography, locked
  branding (header `#DAAB06`, nav/footer `#BF8B00`, three logos, footer), and
  card-based layouts throughout. Inter-page navigation links resolve between
  `-propuesta` pages so the prototype can be browsed end to end.
  - Main pages: `programas`, `invest`, `directorio`, `indicadores`,
    `Transparencia`. `invest` embeds the promotional video via
    `youtube-nocookie.com` with `loading="lazy"` and a responsive 16:9 wrapper.
    `directorio` was rebuilt from a broken HTML table into a clean grid grouped
    by area. `indicadores` adds a "Dashboards interactivos próximamente"
    placeholder for future Module 4 work.
  - Program subpages (12): `triplec`, `Premio`, `NAFIN`, `comprea`, `fed`,
    `eficiencia`, `agentesi`, `marca`, `mypimes`, `desarrollo`, `Mapas`,
    `CECCAV`. `Premio` keeps the 7-stage schedule as a styled table; `mypimes`
    (empty in the source) was built as a MiPyMEs program hub.
  - Legal pages (3): `Aviso`, `Conducta`, `docseg`, with readable document
    layouts and downloadable PDFs.

### Changed
- Theme inversion in `css/redesign.css`: light theme on white (`#FFFFFF`)
  with light-gray alternating sections (`#F5F5F5`), body text dark gray
  (`#333`), and gold (`#DAAB06` / `#BF8B00`) for headings, section titles,
  borders, dividers, accents, buttons and hovers. Display headings (`h1`,
  `h2`, `.seccion-titulo`) use `#DAAB06`; smaller headings (`h3`/`h4`) use
  the darker `#BF8B00` for legibility on white. Surface borders (`--borde`)
  switched from neutral gray to a light gold tint. Locked branding is
  untouched: the header bar stays `#DAAB06` with the three logos, the nav
  bar `#BF8B00`, and the footer `#BF8B00` with dark contact text (an explicit
  `.footer h3` color override keeps the footer heading dark, not gold).
  Note: gold on white is below WCAG AA contrast for small text — acceptable
  for large branded headings, flagged for review on smaller titles.
- Extracted the inline `<style>` block from `index-propuesta.html` into a new
  shared stylesheet `css/redesign.css` (~400 lines). Pure refactor: the
  rendered page is unchanged. The stylesheet is now reusable by the other
  `*-propuesta.html` redesign pages. Branding-locked rules (header `#DAAB06`,
  nav/footer `#BF8B00`, three header logos) are preserved and flagged in the
  stylesheet header comment.

## 2026-05-22

### Added
- Unidad de Género and QuejaNet sections added to `index-propuesta.html`
  redesign proof of concept. (`24bbf82`)
- `index-propuesta.html` redesign proof of concept, inspired by the SEFIRC
  layout. New homepage structure with area cards and updated navigation,
  built alongside the existing production `index.html`. (`66bbfdf`)

## 2026-05-19

### Added
- Initial commit: pre-modernization baseline of the existing static site
  (production HTML/CSS, `CLAUDE.md`, `.gitignore`). (`991aa2a`)
