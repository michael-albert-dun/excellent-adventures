<!-- .slide: class="title-slide center" -->
# Mike &amp; Claude's Excellent Adventures

<p class="meta">Marketing Department · Michael Albert · 25/9/2026</p>

Note:
Cold open. Same frame as the School of Computing version, but shorter and
non-technical throughout — this audience doesn't need (or want) any code,
schemas, or jargon. Two very different projects, two registers of
formality. Don't over-explain yet, that's the next slide.

---

## AI in 2026

<ul>
<li class="fragment strike" data-fragment-index="0">Existential Endgame</li>
<li class="fragment strike" data-fragment-index="0">Economic Erosion</li>
<li class="fragment strike" data-fragment-index="0">Environmental Emergency</li>
<li class="fragment strike" data-fragment-index="0">Ethical Enigmas</li>
<li class="fragment strike" data-fragment-index="0">Enlightening Encyclical</li>
</ul>

<p class="reveal-punchline fragment" data-fragment-index="0">Did you read the title?</p>

Note:
Unchanged from the main talk — works for any audience. The four bullets
appear together, deadpan. Pause. Click once: all four strike through at
once and "Did you read the title?" lands large and centered underneath,
as the reveal that this is not that talk.

---

<!-- .slide: class="center" -->

## Story time

- Two projects
- Claude as a collaborator, start to finish
- What did I experience, and what did I learn?
- What might it mean?

---

<!-- .slide: class="center" -->
<span class="eyebrow">The shape of the talk</span>

## A mullet talk

<p class="fragment"><em>Business up front, party in the back</em></p>

- Rebuilding the ageing internal system behind an academic journal I help run
- Building small browser games, purely for fun

Note:
Business = the journal's database/webapp rebuild. Party = the games.
Keep this slide quick, it's just a map. "Academic journal" needs zero
further explanation yet — that comes next.

---

<!-- .slide: class="act-divider act1-bg center" data-background-color="#1f4b6e" -->
<span class="act-label">Act I</span>

## The Rebuild

<p class="act-tagline">Business up front</p>

---

<!-- .slide: class="act1" data-background-color="#eef4f8" -->
<span class="eyebrow">Act I · Business</span>

## Where we were

I'm an editor of the *Australasian Journal of Combinatorics* — a small
academic journal. It has processed submissions for decades on a system
<span class="fragment strike" data-fragment-index="0">only its editors-in-chief truly understand</span><span class="fragment" data-fragment-index="0"> no one understands</span>

<div class="all-reveal">

- A patchwork nobody had fully documented
- One sprawling database holding the whole workflow together
- Every editor's process was tribal knowledge, not written rules

</div>

Note:
This isn't a toy side project — it's institutional knowledge trapped in
old, undocumented software. Skip any code/file-naming detail from the
technical version; the point lands fine without it.

---

<!-- .slide: data-background-image="../img/legacy/Contact%20record.png" data-background-size="contain" data-background-color="#eef4f8" -->

Note:
Legacy contact record. Let the room laugh at it — no narration needed.

---

<!-- .slide: data-background-image="../img/legacy/Submission%20edit.png" data-background-size="contain" data-background-color="#eef4f8" -->

Note:
Legacy submission edit screen. One more "before" beat, then move on —
don't linger on more than two screenshots given the time budget.

---

<!-- .slide: class="act1" data-background-color="#eef4f8" -->
<span class="eyebrow">Act I · Business</span>

## Back in the future

<div class="all-reveal">

- It's the 2020s, not the 1990s
- Make everyday tasks easy
- Don't add friction or rigidity
- Every action recorded, not just remembered
- The next person to run this journal should be able to pick it up seamlessly

</div>

<div class="callout fragment">Ended up smaller and simpler than the old system — while doing a lot more.</div>

Note:
The callout is the one number worth keeping from the technical version's
stats slide, with the stats themselves stripped out — "simpler while
doing more" lands without needing line counts or table counts.

---

<!-- .slide: class="act1" data-background-color="#eef4f8" -->
<span class="eyebrow">Act I · Business</span>

## The crunch

<div class="all-reveal">

- A last-minute scramble once the new system was ready
- Claude and I had different ideas about what "finished" meant
- The bug that wasn't a bug
- I became Claude's secretary for a day

</div>

Note:
"Different ideas about what finished meant" — Claude had been treating
"finished" as covering the editor-facing actions and the publication
pipeline; I meant that plus the public-facing webpage. A genuine
last-minute scope mismatch, not just a joke.

Then tell the quick-hint story live: I was convinced a search box was
only showing 5 results when it should show 8 — spent a genuinely
embarrassing half hour convinced something was broken, before realising
the results box just... scrolled. Good "even AI collaborations have very
human miscommunications" beat. Skip the sysadmin details (file
permissions, tar, scp) from the technical version — not needed for the
story.

---

<!-- .slide: class="reflection" data-background-color="#33525c" -->
<span class="eyebrow">Reflection</span>

## What I learned

- Keep the big picture in your head
- Users have strange preferences
- But accommodating them is easy
- Scope creep is tempting and real

---

<!-- .slide: class="act1 center" data-background-color="#eef4f8" -->
<span class="eyebrow">Act I · Business</span>

## My greatest accomplishment

<div style="position:relative; display:inline-block; margin-top:0.8em;">
<img src="../img/new/greatest-accomplishment.png" style="display:block; width:auto; max-width:100%; height:auto; max-height:460px; object-fit:contain; border-radius:8px; box-shadow:0 2px 10px rgba(0,0,0,0.15);" />
<div class="fragment" style="position:absolute; left:74.7%; top:17.2%; width:24.3%; height:13.5%; border:4px solid #e0342a; border-radius:50%; box-shadow:0 0 0 2px rgba(255,255,255,0.55);"></div>
</div>

Note:
I submitted a deliberately bogus paper to my own journal, under a fake
name, then rejected it myself ("I thought better of him"). Let the room
read it — no need to narrate the screenshot line by line. Click: circle
the Polite/Blunt rejection buttons — the actual punchline. No maths
knowledge needed for this one, it's just a good joke.

---

<!-- .slide: class="reflection" data-background-color="#33525c" -->
<span class="eyebrow">Reflection</span>

## AI and journal submissions

<div class="all-reveal">

- **Bad content** — *wrong, unmotivated, or too niche*
- **Bad writing** — *unclear, poorly formatted, hard to follow*

</div>

<div class="quad-grid fragment">
<div></div>
<div class="quad-col-label">Good writing</div>
<div class="quad-col-label">Bad writing</div>
<div class="quad-row-label">Good content</div>
<div class="quad-cell">Send to referees</div>
<div class="quad-cell">Expert opinion</div>
<div class="quad-row-label">Bad content</div>
<div class="quad-cell fragment">??</div>
<div class="quad-cell">Desk reject</div>
</div>

Note:
Two classifications: good/bad content, good/bad writing — four
combinations. Historically submissions came in three of the four kinds —
bad content dressed up in good writing was essentially unseen. Click:
that fourth category is now common, and much harder to catch early,
because AI-assisted writing can make weak content read fluently and
confidently. This is the slide most likely to spark discussion with a
marketing audience — the same tension applies to any content review
process, not just academic publishing. Leave room for it.

---

<!-- .slide: class="reflection" data-background-color="#33525c" -->
<span class="eyebrow">Reflection</span>

## The journal's AI policy for authors

> The mathematical research literature is more than a record of known
> results. A paper communicates ideas, explains reasoning, and can inspire
> readers in ways that go beyond the formal content. Authors should bear
> this in mind when deciding how heavily to rely on AI-generated writing.

Note:
Read the quote straight, let it land. Swap "mathematical research
literature" for a line of your own if you want to draw the parallel to
marketing/brand content explicitly — the underlying question (how much
should this sound like a person?) is the same one this audience deals
with.

---

<!-- .slide: class="act1 center" data-background-color="#eef4f8" -->
<span class="eyebrow">Act I · Business</span>

## A looming crisis?

<img src="../img/new/submissions_by_month.png" style="display:block; width:auto; max-width:100%; height:auto; max-height:480px; object-fit:contain; border-radius:8px; margin:0.8em auto 0; box-shadow:0 2px 10px rgba(0,0,0,0.15);" />

Note:
Submissions have roughly tripled since the AI-writing surge discussed
earlier. Genuinely unclear yet whether this settles into a new normal or
keeps climbing — the question mark in the title is doing real work. Good
place to pause for a question if one's already brewing.

---

<!-- .slide: class="act-divider act3-bg center" data-background-color="#c9552f" -->
<span class="act-label">Act II</span>

## The Party

<p class="act-tagline">In the back</p>

---

<!-- .slide: class="act3" data-background-color="#fbeee6" -->
<span class="eyebrow">Act II · Games</span>

## A lot of games

<div class="all-reveal">

- **<a href="https://michael-albert-dun.github.io/tilexicon/" target="_blank" rel="noopener">Tilexicon</a> / <a href="https://michael-albert-dun.github.io/tilehexicon/" target="_blank" rel="noopener">Tilehexicon</a>** — square &amp; hex word puzzles
- **<a href="https://michael-albert-dun.github.io/digitiler/" target="_blank" rel="noopener">Digitiler</a> / <a href="https://michael-albert-dun.github.io/hexiler/" target="_blank" rel="noopener">Hexiler</a>** — their numeric siblings
- **<a href="https://michael-albert-dun.github.io/matrixmind/" target="_blank" rel="noopener">Matrixmind</a>** — two-dimensional Mastermind
- **<a href="https://michael-albert-dun.github.io/deliagonal/" target="_blank" rel="noopener">Deliagonal</a>** — diner-themed rectangle clearing
- **<a href="https://michael-albert-dun.github.io/tintangle/wordtangle/" target="_blank" rel="noopener">Wordtangle</a> / <a href="https://michael-albert-dun.github.io/tintangle/reflexicon/" target="_blank" rel="noopener">Reflexicon</a>** — segment &amp; word puzzles
- All at <a href="https://michael-albert-dun.github.io/" target="_blank" rel="noopener">https://michael-albert-dun.github.io/</a>

</div>

Note:
Move fast here. This slide is a montage — flash it, name a couple out
loud, don't linger. Save the time for the live demo next.

---

<!-- .slide: class="act3 center" data-background-color="#fbeee6" -->
<span class="eyebrow">Act II · Games</span>

## Tilexicon

My first game in this suite.

<p style="text-align:center;"><a href="https://michael-albert-dun.github.io/tilexicon/" target="_blank" rel="noopener" class="demo-tag demo-tag-lg">Demo</a></p>

Note:
Switch to the browser here and play/talk through it live — abandon the
deck for this bit. Just one demo this time; keep it brief and come back
to close the act.

---

<!-- .slide: class="reflection" data-background-color="#33525c" -->
<span class="eyebrow">Reflection</span>

## Claude's role

- Rapid prototyping for interaction
- Checking each new puzzle actually has a solution — and only one
- Final tweaking of the look and feel
- Learns from experience — each game is a little easier to build than the last one

---

<!-- .slide: class="act-divider act4-bg center" data-background-color="#3a3f47" -->
<span class="act-label">Epilogue</span>

## Morals

<p class="act-tagline">What have we learned?</p>

---

<!-- .slide: class="reflection" data-background-color="#33525c" -->
<span class="eyebrow">Reflection</span>

## Looking back

<div class="cols">
<div>

<strong style="color: #ffd88a;">The Rebuild</strong>

- On my urgent list since 2022
- Not easy, but possible
- Workflow improvements I hadn't even planned

</div>
<div>

<strong style="color: #ffd88a;">The Party</strong>

- A 30+ year dream, finally cheap enough to just try
- A genuine pleasure
- Opened up a new creative outlet

</div>
</div>

Note:
Merged version of the two domain-reflection slides from the technical
talk — same lines, side by side, callback to the "business up front,
party in the back" framing from the map slide.

---

<!-- .slide: class="reflection" data-background-color="#33525c" -->
<span class="eyebrow">Reflection · Use of AI</span>

## Final words on using AI

- Doing what you already do, but better, is uninspiring and potentially problematic
- Though sometimes necessary
- Instead, think about building what's been blocked only by mechanical obstacles

---

<!-- .slide: class="center" -->
## Thanks

<p class="small">Questions &amp; discussion</p>
