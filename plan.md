# Quadrat Sampling

**Course:** Environmental Science, Q1 (Population Ecology / Nature of Science)
**Purpose:** teach the *data-collection mechanics* of a vegetation survey before students do one outdoors.

## The three pieces

| File | Who uses it | How |
|---|---|---|
| `widget.html` | **Teacher**, projected | The full five-section simulation. You drive it; the class watches and argues. Self-contained — no server, no internet. |
| `class-script.md` | **Teacher** | What you say while driving the widget. Carries the prose that used to be section 1, the walkthrough step text, and section 4 — plus the questions and the numbers to expect. |
| `../../widgets-public/edrm/quadrat-practice.html` | **Students**, own devices | Just the data-collection half, standing alone. Published to GitHub Pages and embedded in the school site. |

The split is deliberate: the teaching is a conversation, and the practice is something each
student has to do with their own hands. Reading the teaching part off a screen alone was the
weakest use of it.

**Publishing the student page:** it lives in `widgets-public/edrm/`, kept separate from the
math widgets one level up — see `docs/25-widget-hosting-and-embedding.md`. Embed it with

```html
<iframe src="https://USERNAME.github.io/REPO/edrm/quadrat-practice.html?title=0"
        height="1400" scrolling="no" style="width:100%;border:0;"
        title="Quadrat practice"></iframe>
```

`?title=0` hides the widget's own heading when the host page supplies one. Inside a frame it
drops its card chrome and posts its height out, so the host can size the iframe to the
content (see the README in `widgets-public/edrm/` for the listener). It stores a student's entries
in `localStorage`, so a closed tab does not cost them the period; it makes no network calls
at all, and the only thing crossing the iframe boundary is a height integer.

## Why this exists

The first attempt at a real transect failed on procedure, not on concepts — students
weren't clear on what to write down. The mechanics are cheap to rehearse on a screen
and expensive to rehearse on grass with 28 kids and 40 minutes. This runs the rehearsal
as classwork so the field period is spent surveying rather than explaining.

Scope is deliberately one **1 m × 1 m quadrat**, not a whole transect. The quadrat is the
unit of work; a transect is just a row of them. Section 5 sets up why you need more than one.

## Structure of the projected widget

Sections 1, 2 and 4 are now delivered as discussion — their text lives in `class-script.md`.
Section 3 is what became the standalone student page.

| Section | What happens | What it fixes |
|---|---|---|
| 1. The square | Read; answer one placement question | Quadrat placement bias — "we picked good spots" |
| 2. Walkthrough | Read one quadrat under guidance — four numbers entered, one step at a time | The 10×10 grid = 1% per cell trick; subtract-the-dominant shortcut |
| 3. Collect the data | Estimate % cover in 4 quadrats, scored against truth | Actual estimation skill; totalling to 100% |
| 4. One isn't enough | Drop random quadrats, watch the mean converge | Why n matters |
| 5. Walk a transect | Record 8 quadrats in a line across the site; compare against 8 scattered | What position buys you that an average cannot |

The judgment calls are **not** in the widget — they run as a class discussion (below).

### How the walkthrough works

Steps are revealed one at a time, because the answer to each question would
otherwise be sitting in the text of the next step. Students enter four numbers:

1. **Eyeball guess** — bare ground, before any grid. Recorded and held.
2. **Dollarweed** — counted off the grid, revealed against truth.
3. **Bare ground** — counted off the grid, and the reveal compares it to the
   step-1 guess. This is the payoff: most students find their gut estimate was
   off by 10–20 points and the cell count was off by 2–3.
4. **St. Augustine** — *not* counted. They subtract their own two numbers from
   100. Wrong arithmetic here is the one thing the widget makes you fix before
   moving on; the two estimates are not retryable, since an estimate is not
   right or wrong, it is just yours.

## The four quadrats

Stations run along a mown-to-shade gradient, the same one the real transect will use.
Vegetation is generated from fixed seeds, so **every student sees identical quadrats** and
the work is gradeable. True percent cover is counted off the generated field, not authored
by hand, so the key below is exact by construction.

| | Q1 · 0 m mowed lawn | Q2 · 4 m turnaround | Q3 · 8 m unmowed margin | Q4 · 12 m hedge edge |
|---|---|---|---|---|
| St. Augustine | 60 | 38 | 11 | 7 |
| Crabgrass | 18 | 22 | 32 | — |
| Dollarweed | 9 | — | 11 | — |
| Nutsedge | — | 9 | 24 | 9 |
| White clover | — | — | 16 | — |
| Moss | — | — | — | 26 |
| Leaf litter | — | 5 | 6 | 42 |
| Bare ground | 13 | 26 | — | 16 |

The gradient is the point: turf collapses, litter and shade species take over, and the
mower turnaround (Q2) is the most disturbed square on the line. Worth asking about in class.

## What students turn in

The hand-in line at the bottom of **`quadrat-practice.html`**, once all four quadrats are checked:

> **Name** — 4 / 4 quadrats, mean error 5.2 points, **Field-ready**.
> Per quadrat: Q1 4.1 · Q2 6.8 · Q3 5.0 · Q4 4.9

They screenshot it or copy the numbers onto a data sheet. The projected `widget.html` keeps
its own summary, which is only useful if you work through it as a whole class.

Mean error ≤6 points is genuinely good; two trained surveyors routinely differ by more.
Anything over 12 means they eyeballed the whole square instead of counting cells — send it back.

## In-class discussion: the four judgment calls

Run these out loud before going outside. None have obvious answers, which is why groups
lose ten minutes arguing about them mid-survey. The goal is a **written rule sheet the
whole class shares** — a consistent rule beats a correct rule, because inconsistency
between groups is what makes the pooled data unusable.

Each one below is: the prompt, the answers students actually offer, and the ruling.

### 1. The plant that is half in

> A clump of nutsedge straddles the left edge of the frame — about half in, half out.
> What do you record?

*You will hear:* the whole clump / nothing, it isn't fully inside / slide the frame over.

**Ruling — record only the part inside.** The square is a window; half a clump inside is
half a clump of cover. Watch for the student who remembers "count plants touching the top
and left edges only" — that rule is real, but it belongs to **counting individuals**, where
you need to avoid counting one plant in two neighbouring quadrats. Different measurement,
different rule. Good moment to make the class say out loud which one they are doing.

### 2. The plant that is rooted outside

> A hedge branch is rooted well outside the quadrat, but its leaves hang over one corner
> and shade about 8% of the square. Cover or not?

*You will hear:* no, it isn't growing there / only if it touches the ground inside.

**Ruling — yes, it is cover.** Percent cover is defined from directly overhead: if it blocks
your view of the ground, it is covering the ground. That overhang is exactly why nothing
grows underneath. Record it as a separate row ("hedge canopy") rather than folding it into
the ground layer — and note that this is the one case where the column legitimately passes
100%, because you now have two layers of the same square metre.

### 3. The plant nobody can name

> A low creeping thing with tiny red-tinged leaves covers about a fifth of the square.
> Nobody knows what it is.

*You will hear:* leave it blank / add it to bare ground / guess from the field guide.

**Ruling — "Unknown A", 20%, plus a photo.** Never discard data for lack of a label. An
unknown with a photo is identifiable later; a guessed name is a permanent error nobody can
catch. The fatal version is calling it Unknown A in quadrat 1 and Unknown C in quadrat 5 —
now it looks like two species, each patchier than the real one.

### 4. The column that won't add up

> Your single-layer estimates total 128%. What went wrong?

*You will hear:* we forgot bare ground / the frame wasn't exactly 1 m.

**Ruling — overlaps got counted twice.** Four people each asked "how much of the square is
*my* species?", so every shared patch was counted more than once. Note that forgetting bare
ground makes you come in **short**, not over — a useful diagnostic to hand them. The fix:
for the ground layer, assign every bit of ground to exactly one species (the biggest thing
covering it wins), and put genuine second-storey canopy on its own line.

### Close the discussion with a decision

Have the class write four lines on the board and copy them onto every data sheet. Whatever
they decide, it goes on all four quadrats.

## Section 5: the transect

The site widens out to show what the lawn sits between — a **road** down the west edge and a
**pond** off the east. The vegetation runs a real gradient across those 16 m: compacted bare
ground and crabgrass at the road, undisturbed St. Augustine through the middle, dollarweed
and nutsedge in the damp ground near the pond.

Students record 8 quadrats at 2 m intervals along a tape, and the stacked chart builds as
they go. Then a toggle re-runs the same eight quadrats **scattered at random** over the same
lawn. The transect chart shows clean wedges crossing each other; the scattered chart is
jagged noise. Same site, same effort, same species means to within a few points — and only
one of them shows there is a pond.

That contrast is the argument for a transect, and it is worth letting them find it rather
than telling them. Good question to put to the class afterwards: *what would the chart look
like if we had run the tape parallel to the road instead of across it?*

## Follow-up: the real survey

Students arrive already knowing the protocol, so the field period only needs:
tape, four 1 m frames (PVC or string), clipboards, and the rule sheet the class agreed on
during the judgment-call discussion. Sample every 2 m from mown lawn to hedge — the same
layout they walked in section 5. Same data table as the widget.

Pick a real gradient if the campus has one: a path, a fence line, a car park edge, a
drainage swale, the shade line of a building. A transect across a boundary produces a
readable chart; a transect down the middle of a uniform lawn produces a flat one, which is
a true result but a dispiriting first survey.

## Notes for editing

- Species live in the `SPECIES` object; quadrats in `QUADRATS`, near the top of the `<script>`.
- Patch counts and radii were **fitted** to hit deliberate cover profiles (no monodominant
  quadrats — those make estimation trivial). Change a seed and you must refit.
- Percent cover assumes a single layer, so columns total exactly 100%. Multi-layer canopy
  (where cover legitimately exceeds 100%) comes up in discussion #2 below but is not simulated.
- The section 5 site is generated from `ANCHORS` — target composition at the road edge, the
  middle, and the pond edge, interpolated between. Edit those three rows to change the story
  the transect tells. Species are then placed by inverse-CDF against a two-octave noise field,
  *not* by letting species compete: competition gives every patch a single winner, so each
  quadrat reads ~100% of one thing and the exercise collapses.
- The judgment calls were built as widget questions and then pulled back out; if you ever want
  them on screen, the pattern is the `.ec` block still used by the section 1 placement question.
