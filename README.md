# mining-pool-logos

SVG logos for Bitcoin mining pools.

## Conventions

- One logo per pool, named after the pool's slug: `<pool>.svg`.
- An optional light-theme variant: `<pool>.light.svg`, used on light backgrounds.
- Logos must be **self-contained**: no `<script>`, no event handlers (`on*`),
  no `javascript:` URLs, and no external references in `<image>`/`<use>`.
- `npm run validate` runs `check_logos.js`, which sanitizes every SVG with
  DOMPurify and fails the build on unsafe content. CI runs the same check.

## Validate

```bash
npm install
npm run validate
```

## BRMSTE

`brmste.svg` (default/dark) and `brmste.light.svg` (light theme) provide the
BRMSTE mark: an orange gradient badge with a white `B` monogram, sized on the
shared `0 0 120 120` viewBox so it renders consistently across themes.
