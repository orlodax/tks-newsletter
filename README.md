# Teksistemi · Newsletter tecnica

Archive of an internal technical newsletter about working with AI coding agents —
what they do to the code, and what they do to the heads of the people writing it.

Written by **orlodax**. Italian is the source language; every issue has an en-US edition.

**Read it:** https://orlodax.github.io/tks-newsletter/ · [English](https://orlodax.github.io/tks-newsletter/en/)

## Issues

| № | Issue | Format | Date |
|---|-------|--------|------|
| 001 | [Cosa fa l'AI alla nostra testa](001-ai-e-la-nostra-testa.html) · [What AI does to our heads](en/001-what-ai-does-to-our-heads.html) | Deck, 9 slides | 11 Jul 2026 |
| 002 | [Resa dello sviluppo agentico](002-resa-sviluppo-agentico.html) · [Agentic development yield](en/002-agentic-development-yield.html) | Note, interactive | 23 Jul 2026 |
| 003 | [La mappa che non c'è](003-la-mappa-che-non-ce.html) · [The map that isn't there](en/003-the-map-that-isnt-there.html) | Note, ~8 min | 26 Jul 2026 |
| 004 | [La finestra rotta](004-finestra-rotta.html) · [The broken window](en/004-the-broken-window.html) | Deck, 9 slides | 2 Aug 2026 |
| 005 | [Errori di fabbrica](005-errori-di-fabbrica.html) · [Factory settings](en/005-factory-settings.html) | Deck, 23 slides | 7 Aug 2026 |

## How this is built

There is no build step, no framework and no dev server. Every file is standalone HTML
with its CSS and JS inline, so any issue opens by double-clicking it, and the whole
folder deploys to static hosting unchanged. The only external request in the archive
is Google Fonts.

```
index.html                 Italian archive + language router
NNN-slug-italiano.html     issues, oldest to newest
en/index.html              English archive
en/NNN-english-slug.html   translations (matching numbers, translated slugs)
```

### Language routing

GitHub Pages does no content negotiation, so the root `index.html` does it in the
browser: Italian browsers stay on the Italian archive, everything else is sent to
`en/` with `location.replace` (which keeps the back button clean). An explicit
choice made with an IT/EN switcher is stored in `localStorage` as `tks-lang` and
beats detection from then on. Append `?stay=1` to reach the Italian archive
without being redirected. Without JavaScript there is no redirect at all — the
Italian archive simply renders, with the EN link in the top bar.

### Adding an issue

1. Drop the new self-contained `NNN-slug.html` in the root, and its translation in `en/`.
2. Add one line to the `ISSUES` array at the bottom of `index.html`, and one to `en/index.html`.

That's all. The indexes render newest first.

### One rule

**Published issues are frozen.** Their CSS is duplicated across files on purpose — do not
extract it into a shared stylesheet. A shared stylesheet means editing it later silently
restyles every past issue, and an archive whose old entries change is not an archive.
The two `index.html` files are the only shared artifacts.
