# AirType

Interactive concept prototype + investor overview for **AirType** — sensor gloves that turn
ten-finger touch-typing into text (and pointer control) on any device, with no keyboard.

| File | What it is |
|------|------------|
| `index.html` | The interactive 3D demo (Three.js). Realistic glove + components, real QWERTY keyboard, supervised training visualization, keyboard↔mouse gesture, and view controls. Links to the overview (top-right). |
| `overview.html` | Investor-ready 4–5 page overview: Why Now, concept, how it works, competitive positioning, market size, requirements, concept→MVP plan, hurdles, why it's exciting. Has a **Print / Save PDF** button. |
| `vercel.json` | Static hosting config (clean URLs). |

Pure static site — no build step, no dependencies. Open `index.html` locally to preview.

---

## Deploy to Vercel (project: `jesse-2692`)

> I've prepared everything below, but the account/login/push steps need **your** credentials —
> I can't authenticate or create accounts on your behalf. Pick **one** path.

### Path A — Vercel CLI (fastest, no GitHub required)

```bash
# 1. install the CLI (once)
npm i -g vercel

# 2. from inside this folder
cd airtype

# 3. log in (opens browser)
vercel login

# 4. first deploy — answer the prompts:
#    Set up and deploy? Y
#    Which scope?       jesse-2692
#    Link to existing?  N
#    Project name?      airtype
#    Directory?         ./   (root)
vercel

# 5. ship to production
vercel --prod
```

You'll get a live URL like `https://airtype-jesse-2692.vercel.app`.

### Path B — GitHub repo + Vercel auto-deploy (best for ongoing work)

**1. Create the GitHub repo** (using the GitHub CLI):

```bash
cd airtype
git init
git add .
git commit -m "AirType: prototype + investor overview"

# create a NEW repo under your account and push (opens browser to auth if needed)
gh repo create airtype --public --source=. --remote=origin --push
```

*No `gh`?* Create an empty repo at https://github.com/new (name it `airtype`), then:

```bash
git init && git add . && git commit -m "AirType: prototype + investor overview"
git branch -M main
git remote add origin https://github.com/<your-username>/airtype.git
git push -u origin main
```

**2. Import into Vercel:**
- Go to https://vercel.com/new
- Select the **jesse-2692** scope/team (top-left switcher)
- Import the `airtype` repo → Framework preset: **Other** (it's static) → **Deploy**

Every push to `main` now auto-deploys, with preview URLs on pull requests.

---

## Notes
- Custom domain: Vercel → Project → Settings → Domains.
- The overview is print-optimized; "Print / Save PDF" produces the shareable 4–5 page memo.
- Latency/WPM/accuracy shown in the demo are illustrative design targets, not measured results.
