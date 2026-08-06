<div align="center">

<img src="./assets/banner.png" alt="Folding Stool Builder — DIY woodworking calculator" width="100%" />

# 🪑 Folding Stool Builder

### A premium, zero-dependency calculator & build guide for DIY folding camp stools.

[![Status](https://img.shields.io/badge/status-production--ready-22d3ee?style=flat-square)](#)
[![Build](https://img.shields.io/badge/build-zero--dependencies-10b981?style=flat-square)](#tech-stack)
[![React](https://img.shields.io/badge/React-18-61dafb?style=flat-square&logo=react&logoColor=white)](https://react.dev)
[![Tailwind](https://img.shields.io/badge/Tailwind-3.4-38bdf8?style=flat-square&logo=tailwindcss&logoColor=white)](https://tailwindcss.com)
[![License: MIT](https://img.shields.io/badge/license-MIT-emerald?style=flat-square)](./LICENSE)
[![Accessibility](https://img.shields.io/badge/WCAG-AA-blueviolet?style=flat-square)](#accessibility)

Enter **one** number — a leg length in millimetres — and instantly get every
measurement, cutting list, materials list, tools, a 5-step build guide, safety
notes, engineering diagrams and printable workshop reference you need to build a
folding stool.

</div>

---

## ✨ Features

| | |
|---|---|
| ⚡ **Instant dynamic engine** | Every value recalculates live as you type — no reloads. |
| 🧮 **Formula-driven** | All geometry derived from a single leg length `L`. |
| 📊 **Dashboard** | Six premium metric cards with icons, gradients and hover motion. |
| 📐 **Engineering diagrams** | Hand-built responsive SVG: Front, Side & Folded views, fully labelled. |
| 🪚 **Cutting list** | Auto-generated workshop table (qty, part, length, notes). |
| 🧰 **Materials & tools** | Required vs. optional materials, plus a full tools grid. |
| 📖 **5-step build guide** | Instructions with measurements auto-inserted at every step. |
| 🦺 **Safety panel** | Dedicated woodworking safety reminders. |
| 🖨️ **Print mode** | `window.print()` produces a clean A4 workshop reference — controls hidden. |
| 📋 **Exports** | Copy to clipboard, download **JSON**, download **CSV** — 100% client-side. |
| ♿ **Accessible** | Semantic HTML5, ARIA labels, focus rings, keyboard-friendly, `prefers-reduced-motion`. |
| 📱 **Fully responsive** | Desktop, tablet, mobile, portrait & landscape. |
| 🔒 **Private by design** | No backend, no analytics, no tracking. Everything runs in your browser. |

---

## 🚀 Quick start

There is **nothing to install**. The app is a single static `index.html`.

**Option A — open it directly**
```bash
# just double-click index.html, or serve the folder:
python3 -m http.server 8080
# then visit http://localhost:8080
```

**Option B — any static host / IDE**
```bash
npx serve .            # or:  php -S localhost:8080
```
VS Code users: right-click `index.html` → **Open with Live Server**.

> The only requirement is a browser with JavaScript enabled. React, ReactDOM,
> Tailwind and Babel load from CDNs at runtime (an internet connection is needed
> on first load).

---

## 🌐 Deployment

Because it's a single file, you can deploy it anywhere:

- **Linacre.site** — upload `index.html` to your web root.
- **GitHub Pages** — push to a repo and enable Pages on the `main` branch (see below).
- **Netlify / Vercel / Cloudflare Pages** — drag-and-drop the folder or connect the repo. Zero build command needed.

### GitHub Pages
1. Push this repo to GitHub.
2. **Settings → Pages → Source → Deploy from a branch → `main` / root**.
3. Your live calculator appears at `https://<your-name>.github.io/MyDIY/`.

---

## 🧮 The formula engine

Everything is a function of the leg length **L** (mm). Values are rounded to the
nearest millimetre.

| Measurement | Formula | Example (L = 350 mm) |
|---|---|---|
| Total Stool Height  | `L × 0.85` | 298 mm |
| Canvas Seat Width   | `L × 0.65` | 228 mm |
| Canvas Seat Length  | `L × 0.85` | 298 mm |
| Cross Brace Length  | `L × 0.75` | 263 mm |
| Pivot Hole Distance | `L × 0.50` | 175 mm |

Valid input range: **200 mm – 900 mm** (step 1 mm). The engine lives in a single
memoised function, so it's trivial to extend — see [CONTRIBUTING](./CONTRIBUTING.md).

---

## 🗂️ Project structure

```
MyDIY/
├── index.html          # The entire application (single-file SPA)
├── assets/
│   └── banner.png      # Repository / README banner
├── README.md
├── CONTRIBUTING.md     # How to extend the calculator
├── LICENSE             # MIT
└── .gitignore
```

The `index.html` component is organised into clearly-commented sections:

```
Constants & Formula Engine · Icons · Presentational helpers ·
SVG Diagrams · StatCard · Main Application Component · Mount
```

---

## 🛠️ Tech stack

- **React 18** — functional components & hooks only (`useState`, `useMemo`, `useCallback`, `useEffect`).
- **Tailwind CSS** — utility-first styling, responsive breakpoints.
- **Vanilla SVG** — all diagrams and icons hand-coded (no icon library).
- **No build step, no npm packages, no backend.** Edit `index.html` and refresh.

Performance hooks used: `useMemo` for the derived measurements, `useCallback`
for handlers, and refs to avoid unnecessary re-renders.

---

## ♿ Accessibility

Targets **WCAG AA**:

- Semantic landmarks (`header`, `main`, `section`, `article`, `aside`, `footer`).
- Every control has a descriptive label / `aria-label`; validation uses
  `role="alert"` and `aria-live` regions.
- Visible keyboard focus rings; full keyboard operability.
- Honours `prefers-reduced-motion`.
- Diagrams include descriptive `aria-label`s for screen readers.

---

## 🤝 Contributing

Contributions are welcome! See **[CONTRIBUTING.md](./CONTRIBUTING.md)** for how to
add a new measurement, restyle the theme, or add a build step.

---

## 📄 License

Released under the **[MIT License](./LICENSE)**.

---

<div align="center">

<sub>Built for DIY woodworking projects · Measure twice, cut once. 🪚</sub>

</div>
