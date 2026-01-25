# Portfolio Website Rebuild — MS-0010

## Goal

Rebuild the bilingual (EN/PT) psychology portfolio website from scratch using Hugo, with world map showing global patient locations, CV integration, and greenish color palette.

## Context

Previous implementation (MS-0001 through MS-0009) had files that were not committed or were lost. This rebuild creates a complete, working Hugo site.

## Approach

- Hugo static site generator with native i18n support
- SCSS for styling with green calming palette
- Data-driven content via YAML files for easy translation
- SVG-based world map with location markers
- Print-friendly CV page
- Mobile-responsive design

## Files Created

### Configuration
- `config.toml` — Hugo configuration with bilingual settings
- `netlify.toml` — Netlify deployment configuration
- `.gitignore` — Git ignore rules

### Layouts
- `layouts/_default/baseof.html` — Base HTML template
- `layouts/_default/single.html` — Single page template
- `layouts/index.html` — Homepage template
- `layouts/section/cv.html` — CV page template
- `layouts/partials/head.html` — HTML head with meta and styles
- `layouts/partials/header.html` — Navigation with language switcher
- `layouts/partials/footer.html` — Footer with social links
- `layouts/partials/hero.html` — Hero section
- `layouts/partials/about.html` — About section
- `layouts/partials/approach.html` — CBT methodology section
- `layouts/partials/map.html` — World map with patient locations
- `layouts/partials/cv-summary.html` — CV summary section
- `layouts/partials/contact.html` — Contact CTAs

### Styles
- `assets/scss/_variables.scss` — Design tokens and green palette
- `assets/scss/main.scss` — Complete site styles with print support

### Content (English)
- `content/_index.md` — Homepage front matter
- `content/cv/_index.md` — CV page front matter
- `data/en/content.yaml` — English text content
- `data/en/cv.yaml` — English CV data
- `i18n/en.yaml` — English UI strings

### Content (Portuguese)
- `content/_index.pt.md` — Homepage front matter (PT)
- `content/cv/_index.pt.md` — CV page front matter (PT)
- `data/pt/content.yaml` — Portuguese text content
- `data/pt/cv.yaml` — Portuguese CV data
- `i18n/pt.yaml` — Portuguese UI strings

### Static Assets
- `static/images/profile-placeholder.svg` — Profile placeholder

## Related Work Items

- MS-0010 — Hugo project setup
- MS-0011 — Bilingual i18n content + language toggle
- MS-0012 — Professional identity section
- MS-0013 — World map component
- MS-0014 — Green palette + design system
- MS-0015 — CV section with print styles
- MS-0016 — Contact/Instagram CTAs + CBT approach

## Risks Addressed

- **SCSS compilation**: Using literal values instead of CSS variables in SCSS functions
- **Hugo version**: Specified 0.139.0 extended in netlify.toml
- **Accessibility**: Green palette designed with WCAG AA contrast ratios in mind

## Status

Complete

## Next Steps (Future Enhancements)

1. Replace profile placeholder with real photo
2. Add favicon and social sharing images (og:image)
3. Connect custom domain
4. Add analytics (if needed)
5. Consider contact form integration
