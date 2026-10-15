# AGENTS.md

## Overview

Static HTML + CSS student portfolio (袁磊 · 《高级网页设计》课堂实践). No build step, no package manager, no tests, no CI. Open any `.html` file directly in a browser.

## Conventions

- **No external dependencies.** The original assignment requires native code only — no CDN, no frameworks, no external libraries.
- **Prefix:** all CSS class names, id names, and JS variables must start with `xu_`.
- **Prompt log:** before executing any prompt, append it to `xu_prompt.md` with timestamp, model used, and prompt content. Never overwrite — append only.
- **Page naming:** practice pages follow `MMDD-N.html` (date + sequence, e.g. `903-1.html`, `914-2.html`). Use this pattern for new pages.
- **Styles:** most pages are self-contained with inline `<style>` blocks. The root `css.css` is only linked by `914-1.html` — don't assume it's global.
- **Images:** local assets live in `img/` and `img2/`. Reference with relative paths.

## index.html

The navigation hub. Every practice page must be linked from the work-card grid in `index.html`. When adding a new page, add a corresponding `<a class="work-card">` entry there.

## Conventions (continued)

- **New HTML pages must be linked from index.html.** After creating any new `.html` file, add a `<a class="work-card">` entry to the work-card grid in `index.html` so it appears on the navigation hub.

## Content

All UI text is in Chinese (simplified). Preserve the existing tone and language when editing.
