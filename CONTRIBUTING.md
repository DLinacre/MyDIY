# Contributing to Folding Stool Builder

Thanks for your interest in improving this project! The whole app lives in a
single, well-commented file — [`index.html`](./index.html) — so it's easy to
extend. Here's how.

## Running locally

```bash
python3 -m http.server 8080   # then open http://localhost:8080
```

No install step is required. Edit `index.html` and refresh.

## Code map

The file is split into clearly labelled sections:

| Section | What it does |
|---|---|
| **Constants & Formula Engine** | `compute(L)` returns every derived measurement. |
| **Icons** | Inline SVG icon set (Lucide-style). |
| **Presentational helpers** | `SectionHeader`, `Panel`. |
| **SVG Diagrams** | `Diagrams({ calc })` renders Front / Side / Folded views. |
| **StatCard** | A single dashboard metric card. |
| **Main Application Component** | `FoldingStoolCalculator` — state, handlers, layout. |
| **Mount** | Renders into `#root`. |

## Common changes

### Add a new derived measurement
1. Add the calculation inside `compute(L)` and round with `Math.round`.
2. Add a `StatCard` entry to the `stats` array in the main component.
3. (Optional) include it in the export payload (`buildPayload`) and CSV rows.

### Change the colour palette
Colours are Tailwind utilities. Swap the accent tokens
(`emerald`, `cyan`, `blue`, `amber`) or edit the `theme` block in the
`tailwind.config` script near the top of the file.

### Add a build step (optional)
Prefer a compiled bundle? You can lift the `<script type="text/babel">` contents
into a Vite + React project, install `@babel/preset-react`, and build normally.
The component is plain JSX with no runtime quirks.

## Guidelines

- Keep it **dependency-free** at runtime (React + Tailwind + Babel CDN only).
- Maintain accessibility: labels, `aria-*`, focus states, keyboard support.
- Verify with the browser console open — **no errors, no warnings** (CDN
  production notices from Tailwind/Babel are expected and acceptable).
- Run a quick responsive check at 375 px, 768 px and 1280 px widths.

## Pull requests

1. Fork & branch from `main`.
2. Make your change with a clear commit message.
3. Open a PR describing the change and any manual testing you did.

Happy building! 🪑
