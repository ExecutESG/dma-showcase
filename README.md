# DMA Showcase

Visual walkthroughs of the ESGClick Double Materiality Assessment (DMA) process, generated automatically by Playwright E2E tests against real company profiles.

## Case Studies

| Company | Industry | Impacts | R&Os | View |
|---------|----------|---------|------|------|
| [Nokia Corporation](nokia/) | Telecommunications | 24 | 12 | [→ Showcase](nokia/index.html) |
| [Norsk Hydro — Energy](hydro-energy/) | Renewable Energy | 24 | 16 | [→ Showcase](hydro-energy/index.html) |

## How to Regenerate

```bash
# Run from the ESG project root
SHOWCASE_PROFILE=nokia npx playwright test tests/e2e/tools/dma-showcase-dynamic.spec.ts \
  --project=chromium --config=tests/e2e/tools/playwright.showcase.config.ts
```

Screenshots are saved to `{profile}/` directories. After regenerating, commit and push:

```bash
cd public/showcase-screenshots
git add -A && git commit -m "feat: regenerate showcase screenshots"
git push
```

## Viewing Locally

Open any `index.html` directly in a browser, or serve via:

```bash
npx serve .
```

## Architecture

This repo lives **inside** the ESGClick `public/showcase-screenshots/` directory (which is gitignored by the parent ESG repo). The Playwright tests output directly here — no copy step needed.

⚠️ **Warning**: Running `git clean -fdx` in the parent ESG repo will delete this directory. Always push changes to GitHub.
