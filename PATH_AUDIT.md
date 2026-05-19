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
- **Conclusion:** every `../img/` reference is broken in this repository
  snapshot. The correct relative path (from a page inside
  `Secretaría de Economía/`) is `img/…`, not `../img/…`. Whether the
  live production server is laid out so `../img/` resolves is unknown
  and depends on the deployment owner (Open Question in CLAUDE.md).
- **Not fixed in Phase 0.** Any future fix must keep the rendered header
  byte-identical (branding hard constraint).
