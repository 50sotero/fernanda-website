# Tasklist

Purpose: Single source of truth for active work. Keep this current as tasks are added/closed.
Rule: If it's being worked on, it must be here.

## Read First (REQUIRED)

AI/Agents must read `AGENTS.md` before working.

---

## Tracking (required)

- **Next ID:** MS-0017
  - Use this for the next new Issue/Task ID, then increment here AND in `system/tracking/assessment.md`.

---

## Active Priorities (Top 5)

1) None — All current tasks completed

---

## Work Queue

### P0 — Must fix (breaking / core workflow)

- None.

### P1 — Should fix (important but not blocking)

- None.

### P2 — Nice to have (polish / refactor / cleanup)

- None.

---

## In Progress

- None.

---

## Done (recent)

- [x] **MS-0001 — Core website structure + Hugo setup**
  - **Completed:** 2026-01-25
  - **Expert(s):** Design, Implementation
  - **Verification:**
    - Commands run: `./system/scripts/verify.ps1 fast -SkipIfNoTests`
    - Evidence: See `assessment.md` (verification failed due to missing bash on Windows).

- [x] **MS-0002 — Bilingual i18n content + language switch**
  - **Completed:** 2026-01-25
  - **Expert(s):** Design, Implementation
  - **Verification:**
    - Commands run: `./system/scripts/verify.ps1 fast -SkipIfNoTests`
    - Evidence: See `assessment.md` (verification failed due to missing bash on Windows).

- [x] **MS-0003 — World map component**
  - **Completed:** 2026-01-25
  - **Expert(s):** Design, Implementation
  - **Verification:**
    - Commands run: `./system/scripts/verify.ps1 fast -SkipIfNoTests`
    - Evidence: See `assessment.md` (verification failed due to missing bash on Windows).

- [x] **MS-0004 — Professional identity section**
  - **Completed:** 2026-01-25
  - **Expert(s):** Design, Implementation
  - **Verification:**
    - Commands run: `./system/scripts/verify.ps1 fast -SkipIfNoTests`
    - Evidence: See `assessment.md` (verification failed due to missing bash on Windows).

- [x] **MS-0005 — Green palette + design system**
  - **Completed:** 2026-01-25
  - **Expert(s):** Design
  - **Verification:**
    - Commands run: `./system/scripts/verify.ps1 fast -SkipIfNoTests`
    - Evidence: See `assessment.md` (verification failed due to missing bash on Windows).

- [x] **MS-0006 — CV section with print styles**
  - **Completed:** 2026-01-25
  - **Expert(s):** Design, Implementation
  - **Verification:**
    - Commands run: `./system/scripts/verify.ps1 fast -SkipIfNoTests`
    - Evidence: See `assessment.md` (verification failed due to missing bash on Windows).

- [x] **MS-0007 — Instagram + contact CTAs**
  - **Completed:** 2026-01-25
  - **Expert(s):** Design
  - **Verification:**
    - Commands run: `./system/scripts/verify.ps1 fast -SkipIfNoTests`
    - Evidence: See `assessment.md` (verification failed due to missing bash on Windows).

- [x] **MS-0008 — Fix Netlify build (Hugo install)**
  - **Completed:** 2026-01-25
  - **Expert(s):** DevOps, Implementation
  - **Verification:**
    - Commands run: `./system/scripts/verify.ps1 fast -SkipIfNoTests`
    - Evidence: See `assessment.md` (verification failed due to missing bash on Windows).

- [x] **MS-0009 — Fix Hugo SCSS build error**
  - **Completed:** 2026-01-25
  - **Expert(s):** Design, Implementation
  - **Verification:**
    - Commands run: `./system/scripts/verify.ps1 fast -SkipIfNoTests`
    - Evidence: See `assessment.md` (verification failed due to missing bash on Windows).

- [x] **MS-0010 — Hugo project setup (rebuild)**
  - **Completed:** 2026-01-25
  - **Expert(s):** Implementation, DevOps
  - **Files:** `config.toml`, `netlify.toml`, `.gitignore`, base layouts

- [x] **MS-0011 — Bilingual i18n content + language toggle**
  - **Completed:** 2026-01-25
  - **Expert(s):** Design, Implementation
  - **Files:** `i18n/en.yaml`, `i18n/pt.yaml`, `data/en/content.yaml`, `data/pt/content.yaml`, content files

- [x] **MS-0012 — Professional identity section**
  - **Completed:** 2026-01-25
  - **Expert(s):** Design, Implementation
  - **Files:** `layouts/partials/hero.html`, `layouts/partials/about.html`

- [x] **MS-0013 — World map component**
  - **Completed:** 2026-01-25
  - **Expert(s):** Design, Implementation
  - **Files:** `layouts/partials/map.html` with 5 location markers (IE, PT, SE, BR, PE)

- [x] **MS-0014 — Green palette + design system**
  - **Completed:** 2026-01-25
  - **Expert(s):** Design
  - **Files:** `assets/scss/_variables.scss`, `assets/scss/main.scss`

- [x] **MS-0015 — CV section with print styles**
  - **Completed:** 2026-01-25
  - **Expert(s):** Design, Implementation
  - **Files:** `layouts/section/cv.html`, `data/en/cv.yaml`, `data/pt/cv.yaml`

- [x] **MS-0016 — Contact/Instagram CTAs + CBT approach**
  - **Completed:** 2026-01-25
  - **Expert(s):** Design, Implementation
  - **Files:** `layouts/partials/contact.html`, `layouts/partials/approach.html`
