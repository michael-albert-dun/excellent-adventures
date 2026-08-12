# Mike & Claude's Excellent Adventures

A reveal.js slide deck. All content lives in `slides.md` — edit it in any
plain text editor.

## Editing

- Slides are separated by a line containing only `---`.
- Speaker notes go at the end of a slide's text, starting with a line
  `Note:`.
- A slide's "act" and its full-screen background colour are both set on a
  line at the very top of its block, e.g.
  `<!-- .slide: class="act1" data-background-color="#eef4f8" -->`. Leave
  these alone unless you're changing which act a slide belongs to
  (`act1`/`act2`/`act3`/`act4`, or `act-divider act1-bg` + the matching
  strong `data-background-color` for the big section-title slides). The
  colour genuinely fills the screen (it's reveal's native full-bleed
  background layer, not just a tint on the slide box).
- A full-screen image slide looks like
  `<!-- .slide: data-background-image="img/legacy/Front%20page.png" data-background-size="contain" data-background-color="#eef4f8" -->`
  with nothing else in the block but a `Note:` — see the "Where we were"
  screenshots. Spaces in filenames need `%20` in the path. Images live
  under `img/`.
- A few short inline tags appear here and there — `<div class="callout">...</div>`
  for the boxed one-liners, `<span class="demo-tag">Demo</span>` for the
  little "Demo" badges. Edit the text inside them freely; leave the tags.
- Markdown basics: `#`/`##` for headings, `**bold**`, `*italic*`, `-` for
  bullets, `> ` for a blockquote, `` `code` `` for inline code.

## Bullet reveal style

Two styles, chosen per list:

- **slow-reveal** (the default — do nothing) — one bullet appears per
  click, in order. Just write a normal list:
  ```
  - First point
  - Second point
  - Third point
  ```
- **all-reveal** — every bullet appears together, no clicking through.
  Wrap the list in a div, with a blank line right after the opening tag
  (needed so the list still parses as Markdown inside it):
  ```
  <div class="all-reveal">

  - First point
  - Second point
  - Third point

  </div>
  ```

Pick whichever fits a given slide — e.g. a montage/list-of-names slide you
want to flash all at once should be `all-reveal`; a slide where you'll
talk through each point in turn should stay plain (`slow-reveal`).

## Reflection slides

A recurring slide type for stepping back to reflect on the process or
bigger-picture questions — not tied to any one act, usable wherever it
fits (currently two, at the end of Act I; more can go anywhere). Visually
distinct: deep contemplative teal background, white text, an italic serif
eyebrow instead of the sans-serif uppercase one used elsewhere. To add
one:

```
<!-- .slide: class="reflection" data-background-color="#33525c" -->
<span class="eyebrow">Reflection</span>

## Your title here

Ordinary Markdown content — bullets, a blockquote, whatever fits.
```

There's also a `.quad-grid` component for 2x2 classification grids (used
on the "AI in submissions to the AJC" slide) — see that slide in
`slides.md` for the raw-HTML pattern to copy, and give any one cell
`class="fragment"` to have its checkmark click in after the others.

## Previewing

The deck loads `slides.md` at runtime, so it needs a local server (a
double-clicked `index.html` can't read a sibling file directly — that's a
browser security restriction, not a bug). From this folder:

```
python3 -m http.server 8000
```

then open `http://localhost:8000/`. On a Mac you can also just double-click
`serve.command`, which does the same thing.

Refresh the browser tab after saving changes to `slides.md`.

## Presenting

- Arrow keys / space bar advance slides — nothing auto-advances, no timers.
- Press `s` to open the speaker-notes window (shows notes + a timer on a
  second screen/window while the audience sees the plain slide).
- Press `f` for fullscreen, `Esc` for the slide overview grid.

## Structure

Four acts: **The Rebuild** (AJC), **The Digression** (Catalan-Wilf research),
**The Party** (games, ending on Tintangle → the block-rotation-group proof →
the Corner Cases demo), and an **Epilogue** ("Moralitas") reflecting on all
three, ending with "Claude's final words." Live demos (Tintangle, Corner
Cases) are meant to happen by switching to a separate browser tab, not
embedded in the deck — see the "Demo" slides.
