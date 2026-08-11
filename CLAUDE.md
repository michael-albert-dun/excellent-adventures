# Mike & Claude's Excellent Adventures — talk deck

Departmental seminar, Otago University School of Computing, September 2026.
A reveal.js slide deck built collaboratively, edited in bursts over several
weeks (not a one-session build — expect to pick this up repeatedly and
tweak).

## What this is

Personal/narrative talk about three collaborations with Claude, at three
registers: AJC (production webapp rebuild), the Catalan-Wilf paper
(research), and a family of browser games (play). Mullet structure:
business up front, party in the back, short digression in the middle, very
short postscript at the end. See `slides.md` for the actual content and
`README.md` for the full editing/presenting reference — read README.md
first when resuming, it documents all the conventions below in more detail.

## Where things stand

All four acts are drafted with placeholder-ish content; Michael is
iterating on wording live and has said the bullet text will shrink to
3-10 words per point over time (currently longer/fuller sentences in
several places — that's expected to keep changing, not a bug to fix).
Six legacy-AJC screenshots are in as full-screen image slides right after
"Where we were" (order: Front page, All papers, Contact record, Contact
edit, Submission display, Submission edit).

## Key technical decisions (don't relitigate without reason)

- **Plain-text editing workflow**: all content lives in `slides.md`,
  loaded by `index.html` via reveal's markdown plugin at runtime. Michael
  edits `slides.md` directly in a text editor; I (Claude) mostly do
  structural/syntax work he flags as needing tidying, plus new features.
- **Local server required to preview**: `slides.md` is fetched via
  `fetch()`, which browsers block for a double-clicked local file. Use
  `serve.command` (or `python3 -m http.server 8000`) and refresh after
  edits.
- **Presenting day-of via GitHub Pages**: the repo lives at
  github.com/michael-albert-dun/excellent-adventures; Michael plans to
  make it public close to the talk date so it can be served directly via
  GitHub Pages (real HTTP, so `fetch('slides.md')` works with no build
  step). This resolves the earlier open question about needing an
  offline/bundled export. `serve.command` / local `http.server` stays in
  place as the fallback if there's no network on the day.
- **Full-bleed backgrounds**: colours and images use reveal's native
  `data-background-color` / `data-background-image` on the `<!-- .slide:
  ... -->` attribute line, NOT CSS on the section itself — the latter only
  tints the scaled slide box, not the full screen, which Michael
  specifically wants (real edge-to-edge colour transitions between acts).
- **Bullet reveal styles**: two conventions, see README.md "Bullet reveal
  style" section. Plain list = `slow-reveal` (default, one bullet per
  click). Wrap in `<div class="all-reveal">...</div>` (blank line after
  the opening tag, so Markdown still parses the list inside) to show a
  list all at once. Chosen deliberately per-slide; don't assume one is
  "more correct."
- **Manual advance only, always**: no `autoSlide`, no timers, no
  auto-advancing fragments. This was an explicit early requirement
  (Michael doesn't present to a strict timing schedule) and should hold
  for any future additions too.
- **fade-group pattern**: a small reusable trick (see custom.css +
  index.html's `fragmentshown`/`fragmenthidden` handlers) where revealing
  one fragment dims a sibling bullet list to grey via JS-toggled class,
  since CSS alone can't target a preceding sibling from a later one's
  fragment-visible state without relying on `:has()`. Used on the "What's
  it about" cold-open slide; reusable if Michael wants the same effect
  elsewhere.
- **Demos are external, not embedded**: Tintangle and the "Corner Cases"
  interactive proof walkthrough are meant to be opened live in a separate
  browser tab during the talk, not iframed into the deck.

## Next time

Nothing blocking — just keep iterating on `slides.md` content and any new
staging/formatting requests the same way as above. The offline-export
question is settled (GitHub Pages + local-server fallback, see above).
