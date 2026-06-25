# Enginuity Assets (public CDN)

Public-facing Enginuity brand images, served over a free CDN (jsDelivr) for use
in **email signatures, embeds, and anywhere a hosted image URL is needed**.

> **This repo is intentionally PUBLIC.** It contains only images that are already
> public (they ship on enginuityus.com and go out on every email). It holds **no
> code, no client data, and no licensed fonts** — the Gilroy font is *never*
> committed here (redistribution). Brand source-of-truth + working files stay on
> the NAS (`/Volumes/Clients/Enginuity/01_BrandAssets/`) and in the private
> `enginuity-templates` repo.

## Use (jsDelivr CDN)

```
https://cdn.jsdelivr.net/gh/illia-sapryga/enginuity-assets@main/<path>
```

Examples:
- Email signature logo: `…@main/signatures/logo.png`
- Horizontal logo (SVG): `…@main/logos/logo_rectangular_no_padding.svg`
- Square mark: `…@main/logos/logo_square_transparent_background.png`

> Updated a file but the CDN still serves the old one? jsDelivr caches `@main`.
> Purge a path at `https://purge.jsdelivr.net/gh/illia-sapryga/enginuity-assets@main/<path>`.

## Layout

```
logos/        full brand logo kit (PNG + SVG, padded / no-padding / square / favicon)
signatures/
  logo.png    email-sized horizontal logo (600×171) used by the signature generator
  portraits/  employee headshots for the with-portrait signature (square, ~400×400)
```

## Add an employee portrait

Drop `signatures/portraits/<slug>.png` (square ~400×400), commit, push. Reference
it from `enginuity-templates/signatures/signatures_data.py` as
`f"{ASSET_BASE}/portraits/<slug>.png"`.
