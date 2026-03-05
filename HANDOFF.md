# NeuroBook Theme Handoff

## Current State (Done)
- Base theme: Casper `5.9.0`, renamed to `neurobook` in `package.json`.
- Sprint 1 goal implemented: homepage transformed into landing structure (without routing/academy/Stripe logic).
- Header CTA changed to `/pricing/` (`Get Lifetime Access`), Sign in kept via Portal.
- Landing sections added on home:
  - Hero (standard Casper)
  - Problem (wide card block)
  - Course sections (3 cards in row, currently placeholder text/image)
  - Bonus (wide block)
  - Final CTA (wide block)
- Footer note added: `Designed for guided independent play under adult supervision.`
- Hero background changed from image to gradient:
  - `linear-gradient(135deg, #003029 0%, #00695C 100%)`
- Created pages in local Ghost via Admin API:
  - `/pricing/`, `/cards/`, `/parents-guide/`, `/privacy/`, `/terms/`
- `.gitignore` updated to ignore local runtime dirs:
  - `.ghost-docker/`, `.ghost-local/`
- Changes committed and pushed:
  - Commit: `1e918a2`
  - Repo: `https://github.com/MozRom1987/Neurobook`
  - Branch: `main`
- Sprint 2 started:
  - Added `academy.hbs` for academy collection listing
  - Added `routes.yaml` scaffold with `/academy/` collection filtered by `tag:academy`

## Important Files Changed
- `default.hbs`
- `index.hbs`
- `assets/css/screen.css`
- `assets/built/screen.css` (runtime sync case)
- `package.json`
- `.gitignore`

## Local Preview (Working Method)
- Ghost runs in Docker container: `neurobook-ghost`
- Site: `http://localhost:2368`
- Admin: `http://localhost:2368/ghost`

Commands:
```powershell
docker start neurobook-ghost
docker stop neurobook-ghost
docker logs -f neurobook-ghost
```

## Why Docker Was Used
- System Node/CLI path was unstable in terminal sessions.
- Docker + mounted theme gave a stable local preview quickly.

## What Still Needs To Be Done (Next)
1. Replace placeholder card images/text on homepage with final content.
2. Replace temporary card links (now mostly `/parents-guide/`) with real target URLs.
3. Apply `routes.yaml` in Ghost Admin (`Settings -> Labs -> Routes`) and upload this file.
4. Create/mark academy posts with tag `academy` so `/academy/` has content.
5. Fill content on pages:
   - `/pricing/`, `/cards/`, `/parents-guide/`, `/privacy/`, `/terms/`
6. QA pass on desktop/mobile after real content is inserted.
7. Continue Sprint 2:
   - Paid gating
   - Stripe automation
   - Cards upgrade tier

## Demo Content Warning
- Homepage and static pages currently use demo/lorem ipsum copy for layout testing.
- Before release, replace all demo copy with final approved content.

## Notes
- Do not store API keys/tokens in repo files.
- If theme ZIP is needed, rebuild and validate before upload:
  - `gscan -z <theme.zip>`
