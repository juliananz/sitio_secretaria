# Project: Secretaría de Economía de Coahuila — Website Modernization

## Context
Public website of the Ministry of Economy of Coahuila State, Mexico (seccoahuila.gob.mx). Static HTML/CSS site. Lead: Jorge Julián Anzaldúa Guitrón, Director of Investment and Economic Analysis. Primary audience: foreign investors doing site selection in Mexico.

## Hard constraints (Governor's office branding guidelines — DO NOT modify)
- Header logos: "A pasos de gigante", main logotype, WEQ logo
- Visual branding of the Manolo Jiménez Salinas administration
- Footer structure with institutional contact info
- Institutional color palette
- External links to coahuila.gob.mx, congresocoahuila.gob.mx, and transparency platforms
- Main navigation structure
These cannot be modified without explicit authorization.

## Free to modify
- Body content of each page (not header/footer/nav)
- Replace static content (PDFs, lists) with dynamic components
- Video/map/dashboard embeds
- Accessibility, SEO, performance improvements
- Internal refactors (partials, build system) as long as final public HTML looks the same or better

## Open questions (track, do not act on)

- Production deployment owner: UNKNOWN. Pending conversation with Antonio 
  Hernández (Director General de Estrategia y Vinculación Empresarial) 
  or Luis Alberto Torres Arsuaga (Subsecretario). Until resolved, do not 
  introduce build systems or partials.
- Institutional Google account: PENDING REQUEST to IT (asking for a 
  dedicated Gmail like analisis.sec.coahuila@gmail.com for hosting 
  Looker Studio dashboards). Until resolved, dashboards live on personal 
  Google account in prototype mode only.
- License upgrade: Director has basic M365 license with 2 GB OneDrive 
  quota — undersized for role. Separate IT escalation, tracked here for 
  context.

## Phase 3 stack decisions

- Video embeds: youtube-nocookie.com iframes with loading="lazy", 
  responsive aspect-ratio wrapper
- Indicator dashboards: Looker Studio public reports embedded via iframe
  - Data source: Google Sheets
  - Prototype on personal Google account; do NOT embed in public site 
    until institutional account is provisioned
  - Original signed PDFs remain downloadable for transparency compliance
  - Refresh cadence: quarterly, aligned with MIR reporting cycle

## Working conventions
- Never modify files without showing the plan first
- Create a branch or backup before structural changes
- Log every change in CHANGELOG.md
- Content language: Spanish, with English versions where applicable
- Always respond in English in chat, but keep all user-facing content in its original language (Spanish/English bilingual)
