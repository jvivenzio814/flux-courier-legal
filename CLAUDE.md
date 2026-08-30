# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

Public, static legal-pages site for Sunsetrock Studio (John Vivenzio's indie iOS
apps). It is deliberately separate from any app's private source repo — this repo
is public so App Store Connect can link to hosted privacy policies. There is no
build step, no dependencies, and no test suite: it is hand-written HTML served
directly by GitHub Pages.

- Hosted at https://sunsetrockstudio.com/ (custom domain set via `CNAME`)
- FLUX Courier Privacy Policy: https://sunsetrockstudio.com/legal/flux/privacy-policy/

## Structure and conventions

- `index.html` — site root, lists links to each app's legal pages. When adding a
  new app's legal page, add a link here too.
- `legal/<app-name>/privacy-policy/index.html` — the actual privacy policy content
  for an app. Using a directory with `index.html` (rather than `privacy-policy.html`)
  gives it the clean URL `/legal/<app-name>/privacy-policy/` on GitHub Pages.
- `privacy-policy.html` (repo root) — a legacy/compat redirect stub (meta-refresh +
  canonical link) pointing old links at `/legal/flux/privacy-policy/`. Keep this
  kind of redirect stub in place if a page's URL ever moves, so external links
  (e.g. already-approved App Store Connect submissions) don't break.
- `CNAME` — GitHub Pages custom domain config; do not remove unless the domain
  changes.
- Each app gets its own folder under `legal/<app-name>/`. Follow the existing
  FLUX folder as the template when adding a new app.

## Editing conventions

- Pages are self-contained HTML with an inline `<style>` block (no shared CSS
  file, no framework). Match the existing minimal style (system font stack,
  `max-width: 700px` centered body, muted color palette) when adding pages.
- Privacy policy pages include a `.meta` block at the top with App, Developer,
  Bundle ID, and Last updated date — update the "Last updated" date whenever
  policy content changes.
- No build/lint/test commands apply here — changes are plain HTML files, verified
  by opening them directly or checking rendered output at the live GitHub Pages
  URL after push.
