# Changelog

All notable changes to this project are documented here.

## [Unreleased]

### Added
- Social share row below the footer (X, WhatsApp, LinkedIn, Reddit) with a friendly, non-corporate invite line and pre-filled share text.

### Fixed
- Layout shift bug: the page was vertically centered, so when generated text wrapped to a different number of lines across languages (especially Chinese, Arabic, Hebrew), the whole layout — including the network diagram — would jump up or down. Anchored the page to the top instead and reserved more height for the text area.

## [1.4.0] — 2026-06-30 — Ambient background

### Added
- Page-wide ambient background: slow-drifting particles, sinuous field lines, and a barely-visible grain texture, sitting behind the whole page (not just the network diagram). Disabled or static where appropriate when `prefers-reduced-motion` is set.

### Removed
- Dropped the ambient radial glow from the background combination — kept particles, field lines, and grain only.

## [1.3.0] — 2026-06-30 — Controls and sharing

### Added
- Manual language selector — clickable flag row lets visitors jump to a specific language instead of waiting for the auto-cycle.
- Play / pause control for the generation cycle — freezes pulses, ambient activity, and word reveal in place.
- Open Graph / Twitter Card preview image (`og-image.png`) and meta tags, so shared links show a proper preview instead of a bare URL.

## [1.2.0] — Language expansion and message change

### Added
- Portuguese (`pt`), Brazilian Portuguese (`pt-br`), Hebrew (`he`), and Arabic (`ar`).
- RTL (right-to-left) support: `dir` attribute set dynamically, no forced italic on Hebrew/Arabic script.
- Dedicated web fonts for Hebrew (Noto Serif Hebrew) and Arabic (Noto Naskh Arabic).
- Locale detection now checks the full tag (e.g. `pt-BR`) before falling back to the prefix (`pt`), so European and Brazilian Portuguese resolve correctly.

### Changed
- Replaced the original "how AI writes" sentence with a secular message about peace, brotherhood, and universal love — adapted (not translated word-for-word) into all 11 languages.

## [1.1.0] — Korean, footer, visit counter

### Added
- Korean (`ko`) — space-separated like Latin languages, but without italics (Hangul renders poorly in faux-italic).
- Credit footer with a link back to the repository.
- Visit counter via CountAPI.

### Fixed
- CountAPI was discontinued and stopped responding — swapped for [Abacus](https://abacus.jasoncameron.dev), its actively maintained successor, same request/response shape.

## [1.0.0] — Multilingual cycling

### Added
- Five additional languages (English, Spanish, German, Chinese, Japanese) cycling automatically alongside Italian.
- Browser locale detection (`navigator.languages`) sets the starting language.
- Per-language eyebrow label, layer captions, and output label.
- Chinese/Japanese tokenize by character rather than by space, matching how those scripts are actually written.

### Fixed
- Word-spacing bug: spaces were embedded as trailing characters inside `inline-block` spans and could be collapsed inconsistently by the browser at wrap points. Switched to CSS `margin-right` for spacing instead.

## [0.1.0] — Initial release

### Added
- Canvas-based neural network diagram: layered nodes, ambient background pulses, and a signal pulse that travels a real path through the network.
- Word-by-word text reveal synced to the pulse reaching the output node, with an amber flash marking the "transduction" moment.
- Italian-only generated text, original composition.
- `prefers-reduced-motion` support.
