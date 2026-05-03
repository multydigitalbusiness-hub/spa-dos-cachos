# Integrations

> Last mapped: 2026-05-02

## External Services

### WhatsApp Business (Primary Communication)

- **Type:** Deep link integration
- **Endpoint:** `https://wa.me/5561984822215`
- **Usage locations:**
  - Action grid button (`index.html` line 522) — general quote request
  - Featured service card (`index.html` line 559) — screen replacement inquiry
- **Pre-filled messages:**
  - `"Olá, gostaria de solicitar um orçamento!"` (quote request)
  - `"Olá, gostaria de saber mais sobre a Troca de Tela"` (screen service)

### Google Business Profile

- **Type:** Review link
- **Endpoint:** `https://g.page/r/CTVaUjt132zOEBM/review`
- **Usage:** Main CTA button (`index.html` line 510) — prompts customers to leave Google review.

### Google Maps

- **Type:** Location deep link
- **Endpoint:** `https://maps.app.goo.gl/e2kVqk94dbde4yno7`
- **Usage:** Action grid "Localização" button (`index.html` line 545).

### Instagram

- **Type:** Social profile link
- **Endpoint:** `https://www.instagram.com/iteccelulare`
- **Usage:** Footer social icon (`index.html` line 580).

### Google Fonts CDN

- **Type:** Font delivery
- **Endpoint:** `https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600;700`
- **Impact:** Blocks first paint until font stylesheet loads (uses `display=swap`).

### Font Awesome CDN

- **Type:** Icon delivery
- **Endpoint:** `https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css`
- **Impact:** Loads full icon set (~60 KB CSS + WOFF2 fonts).

## Databases

- **None.** Fully static — no backend, no database, no API calls.

## Authentication

- **None.** Public-facing static page with no authentication layer.

## Webhooks / Callbacks

- **None.**

## Client-Side Data Generation

### vCard Contact Download

- **Type:** In-browser Blob generation
- **Location:** `downloadVCard()` function (`index.html` lines 600–620)
- **Output:** `.vcf` file with:
  - Name: `ITEC Assistência Técnica`
  - Phone: `+5561984822215`
  - URL: `https://multydigitalbusiness-hub.github.io/itec-digital-card/`
- **Note:** This is the only "data export" — generated entirely client-side.

## Third-Party Dependency Risk

| Service | Risk Level | Impact if Down |
|---------|-----------|----------------|
| Google Fonts | Low | Falls back to system sans-serif |
| Font Awesome | Medium | Icons disappear (no text fallback) |
| WhatsApp | Low | Link still works, opens default handler |
| Google Maps | Low | Link still works |
| Instagram | Low | Social link unavailable |
