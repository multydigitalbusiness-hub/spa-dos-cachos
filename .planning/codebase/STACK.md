# Stack

> Last mapped: 2026-05-02

## Languages

| Language | Usage | Files |
|----------|-------|-------|
| HTML5 | Page structure, semantic markup | `index.html` |
| CSS3 | Inline `<style>` block — all styling | `index.html` (lines 29–483) |
| JavaScript (ES6+) | Inline `<script>` block — interactivity | `index.html` (lines 595–671) |

- **Primary language:** HTML with embedded CSS and JS (single-file architecture).
- No TypeScript, no build tooling, no transpilation.

## Runtime

- **Browser-only** — static site served directly from the filesystem or a static host (e.g., GitHub Pages).
- No server-side runtime (Node.js, Python, etc.).
- No service workers or PWA manifest detected.

## Frameworks & Libraries

| Dependency | Version | Source | Purpose |
|------------|---------|--------|---------|
| Google Fonts (Montserrat) | N/A | CDN `fonts.googleapis.com` | Typography — weights 300–700 |
| Font Awesome | 6.4.0 | CDN `cdnjs.cloudflare.com` | Icon set (WhatsApp, phone, map, etc.) |

- **No JavaScript framework** (React, Vue, Angular, etc.) — vanilla JS only.
- **No CSS framework** (Tailwind, Bootstrap, etc.) — vanilla CSS with custom properties.
- **No package manager** — no `package.json`, `node_modules`, or lockfiles.

## Configuration

- **CSS Custom Properties (variables)** defined in `:root` (line 30–39):
  - `--primary: #0a84ff` — blue tech accent
  - `--accent: #00ffb2` — green neon accent
  - `--dark-bg: #0f1115` — dark background
  - `--glass-bg`, `--glass-border`, `--glass-highlight` — glassmorphism tokens
  - `--text-main: #ffffff`, `--text-muted: #a0aab2`
- No `.env`, no build config, no linting config.

## Build & Deploy

- **No build step required.** The project is a static HTML file.
- Deploy by copying `index.html` + image assets to any static host.
- Expected hosting: GitHub Pages (based on URL in vCard: `multydigitalbusiness-hub.github.io`).

## Assets

| File | Type | Size | Purpose |
|------|------|------|---------|
| `index.html` | HTML | ~19 KB | Entire application |
| `logoMulty.webp` | Image | ~178 KB | Developer credit logo (Multy Digital) |
| `profile.png` | Image | referenced | Business profile picture (not present in repo) |
| `background.png` | Image | referenced | Background image (not present in repo) |
| `service.png` | Image | referenced | Featured service image (not present in repo) |

> **Note:** 3 image files are referenced in HTML but **not present** in the repository (`profile.png`, `background.png`, `service.png`).
