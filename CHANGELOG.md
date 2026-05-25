# Changelog

All notable changes to the Secretaría de Economía de Coahuila website
modernization are documented here.

The format is loosely based on [Keep a Changelog](https://keepachangelog.com/).
Dates use ISO 8601 (YYYY-MM-DD). Branding constraints defined in `CLAUDE.md`
(header logos, institutional palette, footer, main navigation) are preserved
across all changes unless explicitly authorized.

## [Unreleased] — branch `module-1-redesign-poc`

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
