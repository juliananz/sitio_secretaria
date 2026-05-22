# Production vs. Local Comparison

**Date:** 2026-05-22
**Branch:** phase-0-infra
**Live site:** https://seccoahuila.gob.mx
**Server:** Apache/2.4.39 (Win64) OpenSSL/1.1.1b PHP/7.3.5

## Why this investigation

The PATH_AUDIT.md conclusion was that **all 64 `../img/` references are
broken**. But the production site renders its header logos correctly.
Those two facts seem to contradict each other. This document resolves
the contradiction and characterizes how faithfully our local folder
mirrors production.

## Method

Fetched five pages from production with `curl -A "Mozilla/5.0"` and
compared byte-for-byte against the local copies in
`Secretaría de Economía/`. Then probed candidate image paths on the
server with HTTP HEAD/GET to see which actually resolve.

## Finding 1 — Local HTML is current, with ONE exception

| Page | Local bytes | Prod bytes | `diff` result |
|------|------------:|-----------:|---------------|
| index.html | 9852 | 9852 | **IDENTICAL** |
| programas.html | 6835 | 6835 | **IDENTICAL** |
| directorio.html | 16016 | 16016 | **IDENTICAL** |
| indicadores.html | 5413 | 5413 | **IDENTICAL** |
| invest.html | 6655 | 6647 | **DIFFERS** (see below) |

`invest.html` is the only divergence. Production has **newer** regional
fact-sheet PDFs; our local copy points at the previous month's files:

| Local (stale) | Production (current) |
|---------------|----------------------|
| `files/SEC- NORTE-CINCO MANANTIALES ABR26.pdf` | `files/SEC- NORTE-CINCO MANANTIALESMay26.pdf` |
| `files/SEC - CARBONIFERA ABR26.pdf` | `files/SEC - CARBONIFERAMay26.pdf` |
| `files/SEC - CENTRO -DESIERTO ABR26.pdf` | `files/SEC - CENTRO -DESIERTOMay26.pdf` |
| `files/SEC- LAGUNA ABR26.pdf` | `files/SEC- LAGUNAMay26.pdf` |
| `files/SEC_-_SURESTE ABR26.pdf` | `files/SEC_-_SURESTEMay26.pdf` |
| (plus the English `... Region ABR26.pdf` counterparts) | (`...May26.pdf`) |

The May PDFs exist on the server (verified
`files/SEC- NORTE-CINCO MANANTIALESMay26.pdf` → **200**). So our local
`invest.html` is roughly **one content revision behind** production
(April → May regional brief update). Everything else is in lockstep.

## Finding 2 — Production directory layout (the key to the contradiction)

The pages are served from the **domain root**, not from a subdirectory:

- `https://seccoahuila.gob.mx/index.html` → **200**
- `https://seccoahuila.gob.mx/sec/index.html` → **404** (no `/sec/` subdir)

The asset folders (`img/`, `css/`, `js/`, `files/`) sit **next to the
HTML at the root**. Probing the header logo at three candidate paths:

| URL | Result |
|-----|:------:|
| `https://seccoahuila.gob.mx/img/A-PASOS-DE-GIGANTE_BLANCO.png` | **200 OK** |
| `https://seccoahuila.gob.mx/sec/img/A-PASOS-DE-GIGANTE_BLANCO.png` | 404 |
| `https://seccoahuila.gob.mx/A-PASOS-DE-GIGANTE_BLANCO.png` | 404 |

The other two header logos confirm the same root `/img/` location:

- `/img/LOGOTIPO-PRINCIPAL-BLANCO.png` → **200**
- `/img/WEQ.png` → **200**

## Finding 3 — Why `../img/` works on production but breaks locally

The HTML is identical in both places (`src="../img/A-PASOS-..."`). What
differs is **where the HTML file sits**, and therefore what `../`
resolves to:

**Production** — page lives at the host root:
```
https://seccoahuila.gob.mx/index.html
  src="../img/A-PASOS-DE-GIGANTE_BLANCO.png"
  → browsers CLAMP ".." at the host root (cannot go above the origin)
  → https://seccoahuila.gob.mx/img/A-PASOS-DE-GIGANTE_BLANCO.png  → 200 ✅
```

**Local** — page lives one level deep inside the project:
```
E:\sec2\Secretaría de Economía\index.html
  src="../img/A-PASOS-DE-GIGANTE_BLANCO.png"
  → ".." resolves to E:\sec2\
  → E:\sec2\img\A-PASOS-DE-GIGANTE_BLANCO.png  → does not exist ❌
     (the actual file is at E:\sec2\Secretaría de Economía\img\)
```

So both statements are true at once:

- The PATH_AUDIT conclusion is **correct for the local filesystem
  layout** — `../img/` does not resolve when the HTML sits inside
  `Secretaría de Economía/`.
- The production site renders **correctly** because the pages are served
  at the origin root, where `..` is clamped and `../img/` and `img/`
  both collapse to `/img/`.

The `../img/` reference is, in effect, **harmless on production and only
broken in our local checkout**. It is not a live-site defect.

## Finding 4 — Caveat: the accented portada filename

`index.html` line 58 references `../img/Economía_Portada.png` (note the
accented `í`). On production this filename is **encoding-sensitive**:

| Request encoding | Result |
|------------------|:------:|
| UTF-8 `Econom%C3%ADa_Portada.png` | 404 |
| Latin-1 `Econom%EDa_Portada.png` | 403 |

The 403 (vs 404) on the Latin-1 byte indicates the file **exists** on
the server under a Windows/Latin-1 filename encoding (consistent with
the `Win64` Apache build), not UTF-8. The three header logos have no
accents and resolve cleanly; only the portada carries this risk. Flag
for Phase 1: the accented asset filename is fragile and worth
normalizing to ASCII when we touch body content (it is the cover image,
not a branding-locked header logo).

## Conclusion — what is our local folder?

Our local folder is a **near-current content dump, not a layout mirror**
of production:

1. **Content currency:** essentially current. 4 of 5 sampled pages are
   byte-identical; `invest.html` is one revision (≈1 month) stale on its
   regional-brief PDF links. Not a partial dump, not badly outdated.
2. **Layout fidelity:** different. Production serves pages at the origin
   root with assets beside them; our copy nests the pages inside
   `Secretaría de Economía/` with assets in the same subfolder. This
   nesting is what breaks `../img/` locally — it is an artifact of how
   the folder was saved/zipped, not of the site's authored markup.
3. **Implication for fixes:** the `../img/` paths are NOT broken on the
   live site and must not be "fixed" in a way that changes the rendered
   header (branding hard constraint). Any local-preview need should be
   met by reproducing the production root layout (serve from a docroot
   where `img/` sits beside the HTML), not by editing the `src`
   attributes.

## Verification commands (reproducible)

```bash
curl -s -A "Mozilla/5.0" https://seccoahuila.gob.mx/index.html -o prod_index.html
diff "Secretaría de Economía/index.html" prod_index.html        # IDENTICAL
curl -sI -A "Mozilla/5.0" https://seccoahuila.gob.mx/img/A-PASOS-DE-GIGANTE_BLANCO.png   # 200
curl -s -o /dev/null -w "%{http_code}\n" https://seccoahuila.gob.mx/sec/index.html        # 404
```
