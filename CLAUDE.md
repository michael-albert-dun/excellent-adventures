# Mike & Claude's Excellent Adventures — talk deck

Departmental seminar, Otago University School of Computing, September 2026.
A reveal.js slide deck built collaboratively, edited in bursts over several
weeks (not a one-session build — expect to pick this up repeatedly and
tweak).

## What this is

Personal/narrative talk about three collaborations with Claude, at three
registers: AJC (production webapp rebuild), the Catalan-Wilf paper
(research), and a family of browser games (play). Mullet structure:
business up front, party in the back, short digression in the middle. See
`slides.md` for the actual content and `README.md` for the full
editing/presenting reference — read README.md first when resuming, it
documents all the conventions below in more detail.

## Where things stand

Four acts plus an Epilogue, all drafted, ~40 slides. Michael edits
`slides.md` directly and it changes between sessions without warning —
always re-read it fresh rather than trusting memory of its contents.
Structure: title/cold-open → Act I "The Rebuild" (AJC, six legacy
screenshots, three Reflection slides: what Michael learned, AI in AJC
submissions, and the journal's AI policy for authors) → Act II "The
Digression" (Catalan-Wilf research, two extracted paper figures, four
Reflection slides — most drawn from `process_log.md` in that project,
one a general reflection on AI and open problems) → Act III
"The Party" (games, Tintangle demo, the grid-group-proof, a Reflection on
Claude's role) → Epilogue "Moralitas" (three Reflection slides, one per
domain, then "Claude's final words") → Thanks.

The three per-domain Epilogue Reflection slides ("The Rebuild" /
"The mathematics" / "The Party", eyebrow-tagged `Reflection · <domain>`)
were placeholders ("Content to come") for a while — Michael has since
filled all three in directly. Don't assume placeholder text still applies
anywhere; check before referencing.

## Key technical decisions (don't relitigate without reason)

- **Plain-text editing workflow**: all content lives in `slides.md`,
  loaded by `index.html` via reveal's markdown plugin at runtime. Michael
  edits `slides.md` directly in a text editor; I (Claude) mostly do
  structural/syntax work he flags as needing tidying, plus new features.
- **Local server required to preview**: `slides.md` is fetched via
  `fetch()`, which browsers block for a double-clicked local file. Use
  `serve.command` (or `python3 -m http.server 8000`) and refresh after
  edits.
- **Git + GitHub**: the deck is a git repo, pushed to
  github.com/michael-albert-dun (Michael pushes himself — I don't have
  push access from this environment). Plan is to make it public close to
  the talk date and serve it via GitHub Pages (real HTTP, so
  `fetch('slides.md')` works with no build step) — this settles the
  earlier open question about an offline/bundled export. `serve.command` /
  local `http.server` stays as the fallback if there's no network on the
  day. `.gitignore` excludes `.DS_Store` and `*.map`; `dist/` (the
  self-hosted reveal.js build) and all images are committed so the repo is
  self-contained.
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
- **Fragment ordering beyond simple lists**: reveal assigns fragment order
  by DOM position when no explicit index is given, so wrapping a whole
  block (e.g. `<div class="quad-grid fragment">`) makes it appear as one
  step at the point it sits in the markup, and a *nested* `.fragment`
  inside it (e.g. one grid cell) naturally comes after — used on the "AI
  in submissions to the AJC" slide (bullets show immediately since they're
  in `.all-reveal`, then a click reveals the whole grid, then a click
  reveals the fourth cell). Explicit `data-fragment-index="0,1,2..."` is
  used instead on slides needing a specific list-then-aside interleaving
  (see "Which Block-Rotation Puzzles Generate the Symmetric Group?").
- **Reflection slides**: `class="reflection" data-background-color="#33525c"`
  + `<span class="eyebrow">Reflection</span>` (or `Reflection · <domain>`
  for the Epilogue trio). Deep contemplative teal, white text, italic
  serif eyebrow. Originally two instances, now used heavily throughout all
  three acts plus the whole Epilogue — it's become the deck's default
  register for "stepping back," not a rare special case.
- **quad-grid component**: a reusable 2×2 classification-grid pattern (see
  custom.css `.quad-grid` and the "AI in submissions to the AJC" slide for
  the raw-HTML shape to copy). Sizing/centering went through several
  rounds of iteration — see the CSS fragility note below before touching
  it again.
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
- **Demos are external, not embedded**: Tintangle and the "Corner Cases" /
  grid-group-proof interactive walkthroughs are meant to be opened live in
  a separate browser tab during the talk, not iframed into the deck.
- **Image assets**: `img/legacy/` (six AJC legacy screenshots), `img/new/`
  (modern AJC screenshots + `tintangle-board.png`), `img/paper/`
  (`figure4.png` — cropped from the Catalan-Wilf `EJC.pdf`, and
  `arch-example.png`/`.svg` — a from-scratch redrawn arch system,
  connectivity traced from the PDF's own vector data, arches drawn ~20%
  taller than a true semicircle per Michael's request).

## CSS fragility to remember

Two separate bugs, same root cause: relying on the custom `.vcenter` flex
class (`display:flex; flex-direction:column; justify-content:center;`) to
center a single image/element whose effective container height is
ambiguous. First hit on the quad-grid (horizontal centering went visibly
wrong once `vcenter` was combined with `align-self`), second hit on the
Tintangle image slide (using `vh`-based `max-height` *inside* a
reveal-scaled slide is also independently wrong, since reveal applies a
CSS transform to the whole 1100×720 logical box, and `vh` is resolved
against the real viewport *before* that transform — so an image sized in
`vh` scales inconsistently with everything else and can overflow on some
window shapes but not others). Both times, the fix was the same: drop
`vcenter`, size images in fixed `px` within the slide's own 1100×720
logical coordinate space (never `vh`), and center with plain
`display:block; margin: ... auto;` rather than flex. Default to that
pattern for any new image/single-element slide; only reach for `vcenter`
if actually centering multiple stacked block elements where the
container's height is unambiguous.

## Sensitive spot: crediting ideas accurately

Several Epilogue/Reflection slides (the DFS bullet on "Some highlights
from the log", the last line of "Preliminary report card") exist
specifically because Michael corrected me for claiming or implying credit
for ideas that were actually his (the `av_dfs` algorithm, the
block-reversal bijection fix, the methodological pivot away from
guess-and-check). He cares about this being accurate, not just modest —
when drafting any new content that describes "what Claude did" on either
project, check `process_log.md` (in the Catalan-Wilf folder) rather than
assuming, and default to attributing the actual originating idea
correctly rather than writing generically flattering copy.

## Next time

Nothing blocking. Re-read `slides.md` fresh at the start of any session —
Michael edits it directly between sessions (sometimes right before asking
for a change) and the file-modified-since-last-read warning has fired
before. Keep iterating on content and formatting requests the same way as
above.
