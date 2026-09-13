# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Sean Wilkinson's personal portfolio site — static `index.html`, `styles.css`, plain files with no build system, no framework, no package manager, and no tests.

## Deployment

Deployed via **GitHub Pages** from the `master` branch of the `dontfollowsean.github.io` repo. Any push to `master` publishes the live site. `CNAME` maps it to the custom domain `www.seanewilkinson.com`. There is no deploy command — the push *is* the deploy, so treat commits to `master` as going live immediately.

To preview locally, open `index.html` in a browser or serve the directory (e.g. `python3 -m http.server`).

## Structure & conventions

- `index.html` holds only markup and inline SVG icons, plus a `<link rel="stylesheet" href="styles.css">`. All CSS lives in `styles.css`; there is no `script.js` since the site has no script logic — if you add real interactivity, create `script.js` and reference it with `<script src="script.js" defer></script>`.
- The design system is a set of CSS custom properties in the `:root` block (dark theme: `--bg`, `--accent` purple `#9b6dff`, etc.). Reuse these variables rather than hardcoding colors.
- Fonts (Inter, JetBrains Mono) load from Google Fonts via `<link>` — the only external dependency. Icons are inline SVG `<path>` elements, deliberately kept dependency-free.
- Page sections: `#hero`, `#experience`, `#projects`, `#contact`, matched by the `nav-links`. Experience and Projects share the `.timeline` / `.tl-item` markup pattern — copy an existing `.tl-item` to add an entry.
- Hover states are defined as CSS rules in `styles.css` (e.g. `.hero-bio a:hover`), not inline `onmouseover`/`onmouseout` handlers.

## Content is real

The experience, dates, employers, and contact details are Sean's actual résumé data. Do not invent or alter factual content (companies, roles, dates, metrics) unless the user explicitly asks.
