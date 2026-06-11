# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A static personal academic website for Tan Hong Ming (NUS Business School), served at `thm.sg` via GitHub Pages. No build step — changes to HTML/CSS are live immediately after pushing to `master`.

## Previewing changes

Open `index.html` directly in a browser, or use any static file server:

```bash
python3 -m http.server 8080
```

## File structure

- `index.html` — the entire personal website (About, Research, Publications, Teaching, Media, Industry, Contact), fully self-contained: all CSS in a `<style>` block in the `<head>`, all JS inline at the end of `<body>`, icons as inline SVGs. Only external dependency is Google Fonts (Fraunces for headings, Inter for body). Content changes go here.
- `eche.html` + `styles.css` — a separate minimal landing page for ECHE (analytics consulting brand). `styles.css` belongs to this page only, not the main site.
- `assets/img/` — profile photo (`profile-img2.jpg`) and favicons.
- `assets/js/` + `assets/vendor/` — leftover iPortfolio template boilerplate. No longer referenced by `index.html`; do not wire it back in.
- `docs/` — PDFs (CV, teaching feedback, awards). Referenced by direct links in `index.html`.
- `a3.html`, `a4.html`, `a5.html`, `a6.html`, `takehometest.html` — archived course assignment files (~800–970 KB each). Not linked from the main site.

## Key conventions in index.html

- Design tokens (colors, fonts, max-width) are CSS custom properties in `:root` — change them there, not inline.
- Content sections are `<section id="...">` with an `<h2 class="section-title">`; sub-groups use `<h3>` (styled as uppercase labels).
- Publication entries use `<ul class="pub-list">` with `.pub-title` / `.pub-venue` / `.pub-authors` spans. Courses, awards, and pedagogy use `<ul class="row-list">` with `.item-name` / `.item-meta`. Media mentions use `.media-list`; industry clients are `.chips` pills.
- The single mobile breakpoint is `max-width: 760px` (hamburger nav, stacked hero, single-column rows).
- The inline JS (bottom of `<body>`) handles three things: the typed hero animation (reads `data-typed-items` on `.typed-text`), the mobile nav toggle, and scroll-spy nav highlighting via IntersectionObserver. It respects `prefers-reduced-motion`.
- Hero CV/LinkedIn/GitHub buttons live in `.hero-links`.

## Deployment

Push to `master` — GitHub Pages deploys automatically. The custom domain is configured in `CNAME` (`thm.sg`).
