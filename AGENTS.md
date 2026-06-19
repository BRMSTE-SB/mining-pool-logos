# mining-pool-logos

A collection of mining pool logo SVGs plus `check_logos.js`, a Node.js CLI that
scans every `*.svg` in the repo root for unsafe content (script tags, `on*`
event handlers, `javascript:` URLs, external references in `<image>`/`<use>`),
using `jsdom` + `dompurify`. It exits non-zero if anything unsafe is found.

## Cursor Cloud specific instructions

- This repo has no application server, build step, lint config, or test suite.
  The validator CLI is the entire "application".
- Run the validator with `node check_logos.js` (or `npm run validate`). It scans
  only the repo root and exits `0` when clean, `1` when unsafe content is found.
- CI (`.github/workflows/validate-logos.yml`) runs exactly `npm install` then
  `node check_logos.js`, so a local pass matches CI.
- `npm install` reports a few audit vulnerabilities in transitive deps; these do
  not affect running the validator and can be ignored for development.
