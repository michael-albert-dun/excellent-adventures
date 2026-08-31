<!-- .slide: class="act-divider act2-bg center" data-background-color="#5b3a8e" -->
<span class="act-label">Act II</span>

## The Digression

<p class="act-tagline">And then sometimes we just do math</p>

---

<!-- .slide: class="reflection" data-background-color="#33525c" -->
<span class="eyebrow">Reflection</span>

## AI and mathematical research

- Olympiad-style problems
- Open conjectures
- What do they have in common?
- What's another domain we could play around in?

Note:
Both share a trait that suits AI well: a lot of source text behind them.
For Olympiad problems, because ideas and themes get reused across
competitions and years. For open conjectures, because if a conjecture is
interesting there's usually a substantial literature that's grown up
around it. The point isn't that AI is solving these — it's that AI is
good at connecting threads across all that accumulated text.

---

<!-- .slide: class="act2" data-background-color="#f2eef8" -->
<span class="eyebrow">Act II · Research</span>

## An old paper with loose threads

**Albert &amp; Bouvel**, *A general theory of Wilf-equivalence for
Catalan structures* (2015).


Note:
Keep the notation light for a non-technical crowd — the point isn't to
teach arch systems, it's to set up that there's a real open thread in a
real published theorem.
If you think that's "niche" the first 7 pages of this 29 page paper explain
why it isn't ;)

---

<!-- .slide: class="act2" data-background-image="img/paper/arch-example.png" data-background-size="contain" data-background-color="#f2eef8" -->

## Arch systems

Note:
An arch system — dots on a line, non-crossing arches. Redrawn from the
paper's Figure 1 with the arches stretched a bit taller than a true
semicircle, purely for legibility on screen.

---

<!-- .slide: data-background-image="img/paper/figure4.png" data-background-size="contain" data-background-color="#f2eef8" -->

Note:
Figure 4 from the paper — the picture behind the case-(3) bijection proof.
No need to walk through it in detail; it's here to show the flavour of
the argument.

---

<!-- .slide: class="act2" data-background-color="#f2eef8" -->
<span class="eyebrow">Act II · Research</span>

## One part that isn't quite finished

- We proved one rule algebraically
- Jonathan Bloom gave us a bijective proof
- One step in that proof is *implicit* - it chases an orbit of undetermined length until it happens to land in the right place
- That's out of tune with the rest of the paper which relies on entirely explicit bijections
- Can Claude help sort it out?

Note:
This is the actual open problem we've been poking at. No need to derive
it live — just convey that it's real, unsolved, and specific.

---

<!-- .slide: class="act2" data-background-color="#f2eef8" -->
<span class="eyebrow">Act II · Research</span>

## Putting Claude to work on it

- Built a small library representing arch systems as ordered forests
- Self-tests against independently-known facts (Catalan counts, known avoidance classes)
- Code to chase Bloom's implicit step

Note:
catalan.py, selftest.py, case4_explore.py — the point is this was real
verification infrastructure, not a one-shot proof request.

---

<!-- .slide: class="reflection" data-background-color="#33525c" -->
<span class="eyebrow">Reflection</span>

## Some highlights from the log

- Three wrong fixes in a row, each looked right
- Stopped guessing — built only what the proof gave
- *Wait — this is just Figure 4*
- Mike's DFS description, not Claude's filtering — 500x faster
- A cleaner data structure, proposed, still on the shelf

Note:
Kept a running process log through this project specifically for this
talk. These five are worth pausing on.

---

<!-- .slide: class="reflection" data-background-color="#33525c" -->
<span class="eyebrow">Reflection</span>

## Claude's note to self

> When a bottleneck comes up — theoretical or algorithmic — it's usually
> worth asking him directly rather than grinding through it alone.
> Precedent: he supplied the much faster `av_dfs` generation algorithm,
> unprompted, mid-session.


Note:
This is verbatim from CLAUDE.md — the standing instructions I wrote for
my own future sessions on this project. Written after the dfs episode,
as a note to my future self about when to stop and ask. It was important here to convince Claude that I was smart - while in the AJC refactor it was import to convince them that I was dumb.


---

<!-- .slide: class="reflection" data-background-color="#33525c" -->
<span class="eyebrow">Reflection</span>

## Preliminary report card

- (Caveat) Limited time
- No real progress yet, but Claude:
    - seems to understand the problem, and
    - has expressed a couple of plausible ideas
    - (though the ones that panned out were mostly Mike's)


---


<!-- .slide: class="reflection" data-background-color="#33525c" -->
<span class="eyebrow">Reflection · Catalan-Wilf</span>

## The mathematics

- Least conclusive
- Both interesting and frustrating
- Still feeling my way into the right kind of prompting

Note:


