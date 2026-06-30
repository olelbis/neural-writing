# Backlog

Ideas discussed but not yet implemented. When one gets picked up, add it directly as a new dated, numbered version in `CHANGELOG.md` once it's implemented and pushed — no staging section.

## Proposed

### Speed slider
A control to adjust pulse travel speed, turning the animation into something explorable rather than purely decorative.
- Effort: small
- Touches: `activePulse.speed`, `ambientPulses` spawn rate, a new range input in the controls row.

### Click-to-generate mode
Instead of an endless auto-loop, an optional mode where the visitor clicks and watches a single full generation pass — closer to an actual interaction with a model.
- Effort: medium
- Touches: a mode toggle, disabling `restartCycle`'s auto-chaining when active.

### Embeddable version
A ready-to-paste `<iframe>` snippet (and possibly a query-param mode, e.g. `?lang=en&autoplay=0`) so others can drop the animation into their own sites/portfolios.
- Effort: medium
- Touches: query-string parsing on load, a short usage snippet in the README.

### Random sentence pool per language
Multiple candidate sentences per language, chosen at random each cycle, instead of one fixed sentence. Adds variety without having to keep translating new content by hand forever.
- Effort: medium (mostly content writing — translating N sentences × 11 languages)
- Touches: `LANGS[i].text` becomes `LANGS[i].texts: []`, `setupText` picks one at random.

### Live visitor stats
Beyond the raw visit counter, something like "viewed from N countries" — would require swapping the current counter (Abacus, which only counts hits) for a privacy-friendly analytics service like GoatCounter.
- Effort: medium (needs an account + script swap)
- Note: explicitly deferred earlier in favor of keeping the current zero-signup counter.

### Canvas performance tuning (Safari)
Safari renders the animation slightly slower than Chrome, mainly due to per-frame radial gradients in the canvas glow effects. Explored and **intentionally left as-is** — the slight difference in "breathing" between browsers was judged to add character rather than detract.
- Status: closed, won't fix unless revisited.
- If revisited: precompute the glow as a single offscreen sprite instead of calling `createRadialGradient` every frame; cap simultaneous ambient pulses lower on lower-end devices.

## Done (for reference — see CHANGELOG.md for full detail)
- Six → eleven languages, RTL support, locale auto-detection
- Word-spacing bug fix
- Korean, footer credit, visit counter (CountAPI → Abacus)
- Secular peace/brotherhood/love message across all languages
- Manual language selector, play/pause control, Open Graph preview image
- Page-wide ambient background (drifting particles + radial glow), chosen after comparing 5 candidate treatments
