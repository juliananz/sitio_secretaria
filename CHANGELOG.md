# Changelog

All notable changes to the Secretaría de Economía de Coahuila website
modernization are documented here.

The format is loosely based on [Keep a Changelog](https://keepachangelog.com/).
Dates use ISO 8601 (YYYY-MM-DD). Branding constraints defined in `CLAUDE.md`
(header logos, institutional palette, footer, main navigation) are preserved
across all changes unless explicitly authorized.

## [Unreleased] — branch `module-1-redesign-poc`

### Added
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
