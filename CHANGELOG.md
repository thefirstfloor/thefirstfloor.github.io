# Changelog

## [2026-04-13] — Exclude docs from Jekyll build
- Added CLAUDE.md, CHANGELOG.md, and README.md to `exclude` in `_config.yml` to prevent Jekyll from rendering them as pages

## [2026-04-13] — Trigger GitHub Actions rebuild
- Trigger CI to pick up Node.js 24 environment variable change

## [2026-04-13] — Fix browser title and add project docs
- Fixed browser tab title from hardcoded template name "Creative - Start Bootstrap Theme" to `{{ site.title }}` (pulled from `_config.yml`)
- Added `CLAUDE.md` with build instructions, architecture overview, and changelog convention
