# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A Jekyll-based single-page website for thefirstfloor, a freelance 3DXR developer. It is built from the "Creative" Start Bootstrap theme adapted for Jekyll.

## Build & local development

This is a Jekyll site. There is no `Gemfile` in the repo, so you need Jekyll installed globally:

```bash
jekyll serve        # build and serve with live reload at http://localhost:4000
jekyll build        # build to _site/
```

CSS is compiled by Jekyll from `css/main.scss`, which imports `_sass/_mixins.scss` and `_sass/_base.scss`. No separate Sass build step is needed.

## Architecture

The entire site renders as a single scrolling page via one layout:

- `_layouts/front.html` — the only layout; assembles all sections in order via `{% include %}` tags
- `index.html` — just front-matter (`layout: front`), no content
- `_includes/` — one file per page section: `head.html`, `nav.html`, `header.html`, `call-to-action.html`, `services.html`, `aside.html`, `contact.html`, `scripts.html`, `portfolio.html` (currently unused/commented out in nav)

### Site-wide settings

All configurable metadata lives in `_config.yml`: title, email, description, and social usernames (`twitter_username`, `github_username`, `bluesky_username`). Includes reference these via `{{ site.<key> }}`. The `<title>` tag in `head.html` uses `{{ site.title }}`.

### Styling

- `css/main.scss` — brand colours (`$theme-primary: #90b73e`, `$theme-dark: #242521`) and custom layout classes; imports the Sass partials
- `_sass/_base.scss` — component and section styles
- `_sass/_mixins.scss` — font and transition mixins
- Vendor CSS (`bootstrap.min.css`, `animate.min.css`) is static in `css/`; do not edit these

## Changelog

Before every commit, update `CHANGELOG.md` with a brief description of what changed. Use the format:

```
## [date] — short description of change
- bullet point details
```

### Navigation

Nav links in `_includes/nav.html` use `href="#section-id"` anchors and the `.page-scroll` class for smooth scrolling. The Portfolio section is commented out; to re-enable it, uncomment the `<li>` in `nav.html` and add `{% include portfolio.html %}` to `_layouts/front.html`.
