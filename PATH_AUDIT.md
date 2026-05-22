# Path Reference Audit — `../img/` references

**Date:** 2026-05-19
**Branch:** phase-0-infra
**Command basis:** `grep -rn '\.\./img' *.html` run over
`Secretaría de Economía/*.html`
**Status:** AUDIT ONLY — no paths fixed (per Phase 0 instruction).

## Resolution legend

- **In `./img/`** = file exists in `Secretaría de Economía/img/` (the
  directory that sits *beside* the HTML files).
- **In `../img/`** = file exists at the path the HTML actually requests,
  i.e. one directory above the HTML files. **There is no `img/`
  directory at that level** (`E:\sec2\img\` does not exist), so every
  `../img/` reference resolves to a missing file.

## Reference table (64 rows)

| File | Line | src path | Image filename | In `./img/` | In `../img/` |
|------|------|----------|----------------|:-----------:|:------------:|
| agentesi.html | 33 | `../img/A-PASOS-DE-GIGANTE_BLANCO.png` | A-PASOS-DE-GIGANTE_BLANCO.png | YES | NO |
| agentesi.html | 34 | `../img/LOGOTIPO-PRINCIPAL-BLANCO.png` | LOGOTIPO-PRINCIPAL-BLANCO.png | YES | NO |
| agentesi.html | 35 | `../img/WEQ.png` | WEQ.png | YES | NO |
| Aviso.html | 33 | `../img/A-PASOS-DE-GIGANTE_BLANCO.png` | A-PASOS-DE-GIGANTE_BLANCO.png | YES | NO |
| Aviso.html | 34 | `../img/LOGOTIPO-PRINCIPAL-BLANCO.png` | LOGOTIPO-PRINCIPAL-BLANCO.png | YES | NO |
| Aviso.html | 35 | `../img/WEQ.png` | WEQ.png | YES | NO |
| CECCAV.html | 33 | `../img/A-PASOS-DE-GIGANTE_BLANCO.png` | A-PASOS-DE-GIGANTE_BLANCO.png | YES | NO |
| CECCAV.html | 34 | `../img/LOGOTIPO-PRINCIPAL-BLANCO.png` | LOGOTIPO-PRINCIPAL-BLANCO.png | YES | NO |
| CECCAV.html | 35 | `../img/WEQ.png` | WEQ.png | YES | NO |
| comprea.html | 32 | `../img/A-PASOS-DE-GIGANTE_BLANCO.png` | A-PASOS-DE-GIGANTE_BLANCO.png | YES | NO |
| comprea.html | 33 | `../img/LOGOTIPO-PRINCIPAL-BLANCO.png` | LOGOTIPO-PRINCIPAL-BLANCO.png | YES | NO |
| comprea.html | 34 | `../img/WEQ.png` | WEQ.png | YES | NO |
| Conducta.html | 33 | `../img/A-PASOS-DE-GIGANTE_BLANCO.png` | A-PASOS-DE-GIGANTE_BLANCO.png | YES | NO |
| Conducta.html | 34 | `../img/LOGOTIPO-PRINCIPAL-BLANCO.png` | LOGOTIPO-PRINCIPAL-BLANCO.png | YES | NO |
| Conducta.html | 35 | `../img/WEQ.png` | WEQ.png | YES | NO |
| desarrollo.html | 32 | `../img/A-PASOS-DE-GIGANTE_BLANCO.png` | A-PASOS-DE-GIGANTE_BLANCO.png | YES | NO |
| desarrollo.html | 33 | `../img/LOGOTIPO-PRINCIPAL-BLANCO.png` | LOGOTIPO-PRINCIPAL-BLANCO.png | YES | NO |
| desarrollo.html | 34 | `../img/WEQ.png` | WEQ.png | YES | NO |
| directorio.html | 32 | `../img/A-PASOS-DE-GIGANTE_BLANCO.png` | A-PASOS-DE-GIGANTE_BLANCO.png | YES | NO |
| directorio.html | 33 | `../img/LOGOTIPO-PRINCIPAL-BLANCO.png` | LOGOTIPO-PRINCIPAL-BLANCO.png | YES | NO |
| directorio.html | 34 | `../img/WEQ.png` | WEQ.png | YES | NO |
| docseg.html | 33 | `../img/A-PASOS-DE-GIGANTE_BLANCO.png` | A-PASOS-DE-GIGANTE_BLANCO.png | YES | NO |
| docseg.html | 34 | `../img/LOGOTIPO-PRINCIPAL-BLANCO.png` | LOGOTIPO-PRINCIPAL-BLANCO.png | YES | NO |
| docseg.html | 35 | `../img/WEQ.png` | WEQ.png | YES | NO |
| eficiencia.html | 32 | `../img/A-PASOS-DE-GIGANTE_BLANCO.png` | A-PASOS-DE-GIGANTE_BLANCO.png | YES | NO |
| eficiencia.html | 33 | `../img/LOGOTIPO-PRINCIPAL-BLANCO.png` | LOGOTIPO-PRINCIPAL-BLANCO.png | YES | NO |
| eficiencia.html | 34 | `../img/WEQ.png` | WEQ.png | YES | NO |
| fed.html | 32 | `../img/A-PASOS-DE-GIGANTE_BLANCO.png` | A-PASOS-DE-GIGANTE_BLANCO.png | YES | NO |
| fed.html | 33 | `../img/LOGOTIPO-PRINCIPAL-BLANCO.png` | LOGOTIPO-PRINCIPAL-BLANCO.png | YES | NO |
| fed.html | 34 | `../img/WEQ.png` | WEQ.png | YES | NO |
| index.html | 32 | `../img/A-PASOS-DE-GIGANTE_BLANCO.png` | A-PASOS-DE-GIGANTE_BLANCO.png | YES | NO |
| index.html | 33 | `../img/LOGOTIPO-PRINCIPAL-BLANCO.png` | LOGOTIPO-PRINCIPAL-BLANCO.png | YES | NO |
| index.html | 34 | `../img/WEQ.png` | WEQ.png | YES | NO |
| index.html | 58 | `../img/Economía_Portada.png` | Economía_Portada.png | YES | NO |
| indicadores.html | 33 | `../img/A-PASOS-DE-GIGANTE_BLANCO.png` | A-PASOS-DE-GIGANTE_BLANCO.png | YES | NO |
| indicadores.html | 34 | `../img/LOGOTIPO-PRINCIPAL-BLANCO.png` | LOGOTIPO-PRINCIPAL-BLANCO.png | YES | NO |
| indicadores.html | 35 | `../img/WEQ.png` | WEQ.png | YES | NO |
| invest.html | 33 | `../img/A-PASOS-DE-GIGANTE_BLANCO.png` | A-PASOS-DE-GIGANTE_BLANCO.png | YES | NO |
| invest.html | 34 | `../img/LOGOTIPO-PRINCIPAL-BLANCO.png` | LOGOTIPO-PRINCIPAL-BLANCO.png | YES | NO |
| invest.html | 35 | `../img/WEQ.png` | WEQ.png | YES | NO |
| Mapas.html | 33 | `../img/A-PASOS-DE-GIGANTE_BLANCO.png` | A-PASOS-DE-GIGANTE_BLANCO.png | YES | NO |
| Mapas.html | 34 | `../img/LOGOTIPO-PRINCIPAL-BLANCO.png` | LOGOTIPO-PRINCIPAL-BLANCO.png | YES | NO |
| Mapas.html | 35 | `../img/WEQ.png` | WEQ.png | YES | NO |
| marca.html | 33 | `../img/A-PASOS-DE-GIGANTE_BLANCO.png` | A-PASOS-DE-GIGANTE_BLANCO.png | YES | NO |
| marca.html | 34 | `../img/LOGOTIPO-PRINCIPAL-BLANCO.png` | LOGOTIPO-PRINCIPAL-BLANCO.png | YES | NO |
| marca.html | 35 | `../img/WEQ.png` | WEQ.png | YES | NO |
| mypimes.html | 32 | `../img/A-PASOS-DE-GIGANTE_BLANCO.png` | A-PASOS-DE-GIGANTE_BLANCO.png | YES | NO |
| mypimes.html | 33 | `../img/LOGOTIPO-PRINCIPAL-BLANCO.png` | LOGOTIPO-PRINCIPAL-BLANCO.png | YES | NO |
| mypimes.html | 34 | `../img/WEQ.png` | WEQ.png | YES | NO |
| NAFIN.html | 33 | `../img/A-PASOS-DE-GIGANTE_BLANCO.png` | A-PASOS-DE-GIGANTE_BLANCO.png | YES | NO |
| NAFIN.html | 34 | `../img/LOGOTIPO-PRINCIPAL-BLANCO.png` | LOGOTIPO-PRINCIPAL-BLANCO.png | YES | NO |
| NAFIN.html | 35 | `../img/WEQ.png` | WEQ.png | YES | NO |
| Premio.html | 33 | `../img/A-PASOS-DE-GIGANTE_BLANCO.png` | A-PASOS-DE-GIGANTE_BLANCO.png | YES | NO |
| Premio.html | 34 | `../img/LOGOTIPO-PRINCIPAL-BLANCO.png` | LOGOTIPO-PRINCIPAL-BLANCO.png | YES | NO |
| Premio.html | 35 | `../img/WEQ.png` | WEQ.png | YES | NO |
| programas.html | 33 | `../img/A-PASOS-DE-GIGANTE_BLANCO.png` | A-PASOS-DE-GIGANTE_BLANCO.png | YES | NO |
| programas.html | 34 | `../img/LOGOTIPO-PRINCIPAL-BLANCO.png` | LOGOTIPO-PRINCIPAL-BLANCO.png | YES | NO |
| programas.html | 35 | `../img/WEQ.png` | WEQ.png | YES | NO |
| Transparencia.html | 31 | `../img/A-PASOS-DE-GIGANTE_BLANCO.png` | A-PASOS-DE-GIGANTE_BLANCO.png | YES | NO |
| Transparencia.html | 32 | `../img/LOGOTIPO-PRINCIPAL-BLANCO.png` | LOGOTIPO-PRINCIPAL-BLANCO.png | YES | NO |
| Transparencia.html | 33 | `../img/WEQ.png` | WEQ.png | YES | NO |
| triplec.html | 31 | `../img/A-PASOS-DE-GIGANTE_BLANCO.png` | A-PASOS-DE-GIGANTE_BLANCO.png | YES | NO |
| triplec.html | 32 | `../img/LOGOTIPO-PRINCIPAL-BLANCO.png` | LOGOTIPO-PRINCIPAL-BLANCO.png | YES | NO |
| triplec.html | 33 | `../img/WEQ.png` | WEQ.png | YES | NO |

## Summary

- **64** `../img/` references across **21** HTML pages.
- **4** distinct image filenames referenced:
  `A-PASOS-DE-GIGANTE_BLANCO.png`, `LOGOTIPO-PRINCIPAL-BLANCO.png`,
  `WEQ.png` (header logos, all 21 pages) and `Economía_Portada.png`
  (`index.html` only).
- **All 4** exist in `./img/` (`Secretaría de Economía/img/`).
- **0** exist in `../img/` — that directory does not exist at all.
- **Conclusion:** every `../img/` reference is broken **in this local
  repository snapshot**, because the HTML files sit inside
  `Secretaría de Economía/` and `../img/` therefore points at
  `E:\sec2\img\`, which does not exist. The correct relative path *for
  this local layout* would be `img/…`.
- **Not fixed in Phase 0.** Any future fix must keep the rendered header
  byte-identical (branding hard constraint).

## Update 2026-05-22 — resolved against production (see PROD_COMPARISON.md)

The earlier "whether the live server resolves `../img/` is unknown"
question is now **answered**: it does resolve, and the live site is
**not** broken.

- Production serves every page from the **domain root**
  (`https://seccoahuila.gob.mx/index.html` → 200; no `/sec/` subdir).
  Assets (`img/`, `css/`, `js/`, `files/`) sit beside the HTML at the
  root.
- From a page at the origin root, browsers **clamp `..` at the host**, so
  `../img/A-PASOS-DE-GIGANTE_BLANCO.png` collapses to
  `/img/A-PASOS-DE-GIGANTE_BLANCO.png`, which returns **200**. All three
  header logos resolve this way. That is why production renders correctly.
- The HTML is byte-identical between local and production (4 of 5 sampled
  pages); the only difference is `invest.html`, where production has
  newer May PDFs and our copy still links the April ones.
- **Therefore the `../img/` references are harmless on the live site and
  broken only in our local checkout's nested layout.** Do **not** rewrite
  the `src` attributes to "fix" them — that would risk the header
  branding constraint for no production benefit. For local preview,
  reproduce the production root layout instead.
- **Caveat:** `../img/Economía_Portada.png` (index.html:58) has an
  accented filename that exists on the server only under Latin-1
  encoding (UTF-8 request → 404, Latin-1 → 403). Flagged for Phase 1.
