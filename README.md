# Language synthesis

An animation that gives a sense of what happens inside a neural network while it writes text: pulses travel through the layers and transduce into words at the output.

Pure HTML/CSS/JS, no build step, no dependencies to install.

## Live demo

`https://olelbis.github.io/neural-writing/`

## What it shows

- A layered node graph (context → attention → processing → projection → token). Faint ambient connections simulate background neural activity.
- A signal pulse travels an actual path through the network, lighting up the synapses it crosses.
- When the pulse reaches the output node, a word appears in the generated text below, with a brief amber flash — the moment the signal becomes language.

## Internationalization

On load, the page reads the browser's locale (`navigator.languages`) and opens in the matching language if supported, defaulting to English otherwise. The sentence then cycles automatically through eleven languages, each with its own flag, layer labels, caption text, and (where relevant) script-specific typography:

| Language | Code | Word separation | Direction | Notes |
|---|---|---|---|---|
| Italian | `it` | space-separated | LTR | |
| English | `en` | space-separated | LTR | |
| Spanish | `es` | space-separated | LTR | |
| German | `de` | space-separated | LTR | |
| Portuguese | `pt` | space-separated | LTR | European Portuguese |
| Portuguese (Brazil) | `pt-br` | space-separated | LTR | Brazilian phrasing and vocabulary |
| Korean | `ko` | space-separated | LTR | Korean uses word spacing, unlike Chinese/Japanese |
| Chinese | `zh` | character-by-character | LTR | No spaces — standard for Chinese text |
| Japanese | `ja` | character-by-character | LTR | No spaces — standard for Japanese text |
| Hebrew | `he` | space-separated | RTL | |
| Arabic | `ar` | space-separated | RTL | |

Locale detection checks the full tag first (e.g. `pt-BR`) before falling back to the language prefix (e.g. `pt`), so European and Brazilian Portuguese resolve correctly.

Respects `prefers-reduced-motion`.
