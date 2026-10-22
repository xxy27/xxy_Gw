# AGENTS.md

## Overview

Static HTML + CSS student portfolio (袁磊 · 《高级网页设计》课堂实践). No build step, no package manager, no tests, no CI. Open any `.html` file directly in a browser.

## Conventions

- **Native code only.** 使用原生 HTML、CSS 和 JavaScript 实现，不使用任何第三方库和 CDN。`cdn/` 目录下的 Font Awesome / Lucide 为早期练习遗留，新页面不得引用。
- **Icons:** 图标统一使用 `font/` 目录下的 iconfont 图标——`<link rel="stylesheet" href="font/iconfont.css">`，类名形如 `iconfont icon-xxx`；可用 `font/demo_index.html` 预览可用图标。
- **Data fetching:** 需要获取服务器端数据时，一律使用原生 `fetch` API，不使用 XMLHttpRequest、jQuery、axios 等。
- **Prefix:** all CSS class names, id names, and JS variables must start with `xxy_`.（早期页面使用 `xu_` 前缀，仅在新代码中使用 `xxy_`，不回改旧页面）
- **Author comment:** every HTML page must include a comment near the top of `<head>` or `<body>`: `<!-- 姓名：徐昕妤，日期：YYYY-MM-DD，功能名称：页面功能 -->`（日期为创建日期，功能名称为该页面/功能的名称）。
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
