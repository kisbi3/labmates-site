# Asterelle landing page

Static Korean one-pager for Asterelle (researcher audience, private-beta CTA).
**This directory is the source of truth.** The live site is served by GitHub
Pages from the separate public repo `kisbi3/asterelle-site` (the main repo is
private and the free plan cannot serve Pages from it).

Language routes:

- `/` — Korean
- `/en/` — English
- `/docs/`, `/en/docs/` — public product documentation
- `/changelog/`, `/en/changelog/` — user-facing product changes

Both pages carry reciprocal `hreflang` metadata and expose a language switch in the primary navigation.

## Brand assets

- `assets/asterelle-brand-original.png` is the preserved master image supplied for the Asterelle identity.
- `assets/asterelle-wordmark.png` is the tightly cropped horizontal lockup used by the site.
- `assets/asterelle-mark.png` is the mark-only crop used for compact UI and the favicon.
- `assets/asterelle-wordmark-transparent.png` and `assets/asterelle-mark-transparent.png` are the reusable transparent-background assets used by product surfaces.
- Keep the ivory-backed crops as visual references; use the transparent variants in UI unless a fixed brand field is required.
- Desktop copies are derived from these PNGs; do not redraw the mark as SVG.

- Live URL: https://kisbi3.github.io/asterelle-site/
- Screenshots in `assets/` were captured from the packaged desktop app running
  against an isolated demo vault ("Stochastic Dynamics Lab") — no real lab data.

## Deploy (sync this directory → public repo)

```bash
git clone https://github.com/kisbi3/asterelle-site.git /tmp/asterelle-site
rsync -av --delete --exclude .git site/ /tmp/asterelle-site/
cd /tmp/asterelle-site && git add -A && git commit -m "sync Asterelle site" && git push
```

Pages serves from `main` / root, so the push is the deploy.
