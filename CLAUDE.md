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

- `index.html` — the entire personal website (About, Research, Publications, Teaching, Media, Consulting, Contact). All CSS is inline in a `<style>` block in the `<head>`. Content changes go here.
- `eche.html` + `styles.css` — a separate minimal landing page for ECHE (analytics consulting brand).
- `assets/js/main.js` — from the iPortfolio BootstrapMade template (v3.3.0). Handles the typed-text hero animation, smooth scroll, navbar active state, and AOS scroll animation init. Edit with care — it's shared boilerplate.
- `assets/vendor/typed.js/` — typed.min.js used for the animated subtitle in the hero section.
- `docs/` — PDFs (CV, teaching feedback, awards). Referenced by direct links in `index.html`.
- `a3.html`, `a4.html`, `a5.html`, `a6.html`, `takehometest.html` — archived course assignment files (~800–970 KB each). Not linked from the main site.

## Key conventions in index.html

- Content sections use `<section id="..." class="section-container">` with `<dl>/<dt>/<dd>` grids for publications, courses, and awards.
- The responsive breakpoint at `max-width: 1199px` enlarges fonts significantly for tablet/mobile — when adding new text styles, mirror them in that media query.
- The hero typed animation reads from `data-typed-items` on the `.typed` span: `"Assistant Dean, Deputy Head, Senior Lecturer"`.
- Social/CV links are in the `.social-media-icons` div in the `<header>`.

## Deployment

Push to `master` — GitHub Pages deploys automatically. The custom domain is configured in `CNAME` (`thm.sg`).
