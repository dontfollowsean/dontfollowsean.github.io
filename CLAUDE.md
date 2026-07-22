# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Sean Wilkinson's personal portfolio site — a single, self-contained `index.html`. There is no build system, no framework, no package manager, and no tests. Everything (markup, CSS, inline SVG icons) lives in `index.html`; edit it directly.

## Deployment

Deployed via **GitHub Pages** from the `master` branch of the `dontfollowsean.github.io` repo. Any push to `master` publishes the live site. `CNAME` maps it to the custom domain `www.seanewilkinson.com`. There is no deploy command — the push *is* the deploy, so treat commits to `master` as going live immediately.

To preview locally, open `index.html` in a browser or serve the directory (e.g. `python3 -m http.server`).

## Structure & conventions

- The design system is a set of CSS custom properties in the `:root` block (dark theme: `--bg`, `--accent` purple `#9b6dff`, etc.). Reuse these variables rather than hardcoding colors.
- Fonts (Inter, JetBrains Mono) load from Google Fonts via `<link>` — the only external dependency. Icons are inline SVG `<path>` elements, deliberately kept dependency-free.
- Page sections: `#hero`, `#experience`, `#projects`, `#contact`, matched by the `nav-links`. Experience and Projects share the `.timeline` / `.tl-item` markup pattern — copy an existing `.tl-item` to add an entry.
- Some links use inline `style=` and `onmouseover`/`onmouseout` hover handlers (e.g. the hero bio links) rather than CSS classes; match the surrounding pattern when editing those.

## Content is real

The experience, dates, employers, and contact details are Sean's actual résumé data. Do not invent or alter factual content (companies, roles, dates, metrics) unless the user explicitly asks.
