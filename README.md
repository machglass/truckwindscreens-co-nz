# truckwindscreens.co.nz – rebuilt static site

Plain static HTML/CSS (no build step, no JavaScript, no external fonts, trackers or secrets).
Publish the repository root as-is on Netlify (`netlify.toml` sets `publish = "."`).

## Business details used
Truck Windscreens – family owned NZ auto glass since 1967 · 133c Pilkington Road, Panmure, Auckland 1072 ·
**0800 321 800** · machglass@gmail.com · open 7am to 11pm, 7 days · direct bills all insurers ·
mobile and in-store **replacement** (no chip-repair wording).

## What was recovered (Internet Archive Wayback Machine)
The original site was a WordPress/WooCommerce install. Text was recovered from these captures:

| Content | Original URL | Wayback capture(s) used |
|---|---|---|
| Home page text (service boxes, "Request for Service" list, areas-covered list) | `/` | 2024-03-26, 2026-02-03 (`20260203150254`) – identical text |
| Insurance Glass Claims index (32 insurers) | `/insurance-glass-claims/` | 2025-03-05 (`20250305060024`) |
| Insurer pages – AON, Mainstream, Protecta, Motor & General fetched and compared | `/windscreen-insurance-with-<insurer>-call-us-for-your-auto-glass-replacement/` | 2025-02-20 (`20250220102502`, `…102624`, `…102709`, `…102636`) |
| Isuzu make list | `/isuzu/` | 2026-02-03 (`20260203150250`) |
| Ram make list | `/ram/` | 2025-03-05 (`20250305051339`) |
| Vehicle Make index (first page only – a generic car catalogue: Alfa Romeo, Aston Martin, Audi…) | `/vehicle-make/` | 2025-03-05 |

All 32 insurer pages used one identical template with only the insurer name changed (checked on 4 captures),
so all 32 were regenerated from that template at `/insurance/<insurer>/`.

## What was rebuilt from sibling sites
Layout/CSS is adapted from the Bus Glass NZ site (busglass.co.nz source zip). Wording for the welcome/About text,
"Rapid Response", "Night & Weekend Service", "Insurance Work" and the truck make groups (Japanese trucks: Dyna, Dutro,
Toyota, Atlas, Titan, Canter, Fuso, UD; European trucks: Acco, DAF, Iveco, Scania, MAN) comes from
windscreen-replacement.co.nz, uteglass.co.nz and vanglass.co.nz. Rebuilt pages: `/truck-glass/`, `/truck-makes/` and
its make pages, `/about/`, `/contact/` (Netlify Forms), `/thanks/`, `/areas/` (uses the recovered list), `/404.html`.
Per-make model names (e.g. Isuzu Elf/N Series, Hino Ranger, Fuso Canter/Fighter) are common NZ truck model names.

## Changes from the original
- Header number 0800 757-985 removed; only 0800 321 800 is used.
- "auto glass repair(s)" wording changed to replacement wording; no chip-repair wording.
- Wayback rewrites, WordPress/WooCommerce scripts and any third-party tracking removed.
- Original images (logo PNG containing 0800 757-985, insurer logo) were not reused; a text logo and SVG artwork are used.
- Old WordPress URLs 301-redirect to the new clean URLs (see `netlify.toml`).

## Not recovered
- The thousands of WooCommerce car-model/suburb "product" pages (e.g. "Alfa Romeo 147 Windscreen & Glass Replacement").
  This was a generic car catalogue, not specific to trucks. Old `/shop/`, `/product/`, `/vehicle-make/` URLs redirect to `/truck-makes/`.
- Original images and theme CSS (binary/asset captures could not be downloaded in this environment).

## Netlify notes
- The contact form uses Netlify Forms (`data-netlify="true"`). Turn on form notifications to machglass@gmail.com in the Netlify UI.
- Set the custom domain to `truckwindscreens.co.nz` (www redirects to the apex).
