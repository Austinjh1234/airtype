# CLAUDE.md — AirType

Context for Claude Code when working in this repo.

## What this is
AirType: a concept prototype + investor overview for sensor gloves that turn ten-finger
touch-typing into text (and pointer control) on any device, output as a standard Bluetooth
HID keyboard. This repo is the **pitch/prototype site**, not the firmware/ML system.

## Files
- `index.html` — Apple-style marketing landing page (single file, vanilla JS, no deps).
  Dark gradient hero with an animated "engine" viz (per-finger sensor nodes + live
  typewriter), scroll-reveal sections (what / how it works / why now / the decoder / CTA),
  sticky blur nav. Links to the demo and overview.
- `demo.html` — interactive 3D demo (Three.js r128, single file, vanilla JS). Realistic
  glove with sensor components, real labeled QWERTY keyboard, supervised-training
  visualization, keyboard↔mouse gesture, view controls (freeze spin / lock movement),
  and top-right Home + Overview links. (Was `index.html` before the landing page landed.)
- `overview.html` — print-ready investor memo (Why Now → concept → how it works →
  competition → market → requirements → concept→MVP plan → hurdles → why exciting).
  Has a "Print / Save PDF" button.
- `vercel.json` — static hosting config (clean URLs).
- `README.md` — deploy runbook.

## Stack & conventions
- Currently a **pure static site** — no build step, no dependencies. Open `index.html` to preview.
- 3D demo is intentionally a single self-contained file with vanilla JS + Three.js from CDN.
  Keep it dependency-light and CDN-loaded unless we deliberately migrate.
- Brand: dark telemetry aesthetic for the demo; light editorial memo for the overview.
  Accent palette — left hand cyan `#34D9CE`, right hand amber `#F5A95A`, armed green `#3DF08C`;
  finger colors index `#5BB8FF`, middle `#5BE0A8`, ring `#FF8FB3`, pinky `#9B8CFF`, thumb `#F5C45A`.
- Fonts: Space Grotesk (display) + JetBrains Mono (telemetry) in the demo; + Newsreader (serif body) in the overview.

## Run / preview
```bash
# any static server, e.g.
npx serve .         # or: python3 -m http.server
```

## Deploy targets
- Vercel scope/team: **jesse-2692**, project name: **airtype** (static, framework preset "Other").
- See README for the CLI path (`vercel` → `vercel --prod`) and the GitHub path
  (`gh repo create airtype --public --source=. --remote=origin --push`, then import at vercel.com/new).

## Possible next work (not yet built)
- Migrate to **Next.js App Router** if/when this becomes more than two pages (Jesse's default stack:
  TypeScript/Node 20+, pnpm, Next.js App Router). The current static files port cleanly into `app/`.
- Demo: "air mode vs surface-tap mode" toggle contrasting WPM/accuracy; a keyboard⇄mouse
  mode-state diagram; an interactive (hold-to-engage) version of the mouse gesture; show
  decoder accuracy degrading under drift then recovering after re-baselining.
- Overview: add a concrete "The ask" block (raise amount, use of funds, team slots).
```
