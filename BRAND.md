# tek·development — brand addendum

An extension of **Brand manual Teksistemi** (WMC, July 2026) covering the channels the
software development department runs on its own: this newsletter first, and whatever
comes after it.

Sections are numbered to **continue the manual's numbering**, not to replace it. Where
this document is silent, the manual governs. Where the two disagree, the manual wins and
this document is wrong and should be fixed.

**Not covered here:** corporate communication, sales material, the website, anything
signed `teksistemi` rather than `tek·development`. Those stay exactly as the manual says.

---

## 2.3 — Where this sits in the brand architecture

The manual already drew this. Section 2.2 defines a branded-house structure — a
monolithic parent plus derived marks *"solo in ambito comunicazione"* — and shows two of
them by name: **`tekdevelopment`** and `teksecurity`. The asset pack ships
`tekdevelopment` as a finished lockup in `Social/Asset vari/Logo_declinazioni.png`.

So the development channel is **not a new sub-brand**. It is the first real deployment of
a declination the manual already sanctioned. Nothing here asks for a decision that
WMC's structure hasn't already made.

**The rule that follows from it:** every surface carries the parent above the department.
`teksistemi` signs the page; `tek·development` speaks on it. A page that shows the
department mark without the parent mark is off-system.

### What we do not have

The official `tekdevelopment` lockup exists **only as raster** (a 4000×2250 PNG). There is
no vector. It cannot be faithfully rebuilt from the assets we hold:

> Measured against the official `teksistemi` vector, the descriptor's x-height is 74.6
> units and its width for "sistemi" is 407.68 units. Space Grotesk Light at the same
> x-height sets the same word at 520.52 units — **the official descriptor is ~22%
> narrower**. It is not Space Grotesk, and it is not a tracking adjustment.

Setting "development" in Space Grotesk and calling it the lockup would ship a visible
forgery — worse on a page that also shows the genuine `teksistemi` vector two centimetres
above it. So until WMC supplies the vector we do the honest thing: the **official monogram
vector** plus a descriptor **openly set in the brand's own mono**, which reads as a
typographic label rather than a counterfeit wordmark.

**Ask WMC for:** `tekdevelopment` as SVG, in the same four cuts as the parent
(color / color negative / mono / mono negative). When it lands, it replaces the
reconstruction in the masthead and this subsection goes away.

---

## 3.3 — Marks

### The green pixel

The monogram's detached square — the dot under the `t` — is the department's signature.
**On our channels that one square is green (`#22c55e`). Everything else in the mark is
untouched.**

It is the smallest intervention that still reads, and it is the right one: a lone square
pixel sitting on the baseline is a cursor. It is also a **one-element change** in every
logo file we hold, which is why it is a rule and not a redraw:

| file | the element to recolour |
|---|---|
| `Monogramma/Logo__monogramma_*.svg` | `<rect x="829.63" y="638.89" width="50.09" height="50.09">` |
| `Esteso/Logo__extended_*.svg` | `<rect x="692.9" y="586.95" width="24.42" height="24.42">` |
| `Icona/Logo__icon_*.svg` | `<rect x="898.4" y="586.1" width="23.62" height="23.62">` |

**One pixel, one green.** No other part of any mark changes colour — *above the size
threshold in §3.4.*

### Which mark, where

| context | mark |
|---|---|
| page signature (parent) | `teksistemi` extended logotype, negative — red `tek`, off-white `sistemi`, **red pixel** |
| department masthead | `tek` monogram, off-white, **green pixel** + descriptor in Overpass Mono |
| favicon, app icon, social avatar | see §3.4 — **the whole `tek` goes green** |

The icon's dark-tile variant is the manual's own (§3.2 shows the icon on a near-black
tile); we specify the tile as **Grigio 800 `#2E2C30`** so it is a palette colour and not
an invented one.

---

## 3.4 — Small sizes and avatars

**The one-pixel rule has a floor.** It depends on a detail that is roughly 3% of the
mark's width. Below about **64px** that detail is sub-pixel, so a mark carrying only the
green pixel is indistinguishable from the corporate mark — which is the opposite of what
an avatar has to do.

> Measured on a contact sheet at 96 / 48 / 32 / 20px against Discord `#1e1f22`, Teams
> `#1f1f1f`, GitHub `#0d1117` and white: the green `tek` is legible at every size down to
> 20px. A single green pixel is not visible at any of them.

So there are two states, and the threshold is the rule:

| | treatment |
|---|---|
| **≥ 64px**, or shown with the wordmark / in a page that already carries the system | off-white `tek`, **green pixel** (§3.3) |
| **< 64px**, or standing alone with no supporting context — favicon, app icon, team avatar | **the whole `tek` in `#22c55e`** on a Grigio 800 tile |

The green mark and the corporate red-and-white one read as an obvious pair at every size:
same drawing, two colour substitutions.

### Avatars — Teams, Discord, GitHub, Slack

Built on **the corporate avatar's own construction**, measured from
`Social/Immagine profilo/Tesksistemi_Propic.png`:

- **full-bleed square, no rounded corners, no transparency** — every platform applies its
  own rounding, and self-rounding double-rounds or leaves the corners showing through
- **mark at 59.44% of the canvas width, dead centre** (the corporate file measures
  0.2016–0.7960 horizontally, centred at 0.4988)
- the mark clears the inscribed circle comfortably, so a circular crop never clips it

Ready-made in `assets/avatar/`:

| file | ground | use |
|---|---|---|
| `tek-development-avatar.svg` + `-1024/512/256/128.png` | Grigio 800 `#2E2C30` | **default** |
| `tek-development-avatar-ink900.svg` + PNGs | Antracite 900 `#1C1B1E` | light chrome, or when the tile should recede |

**Why Grigio 800 is the default and not Antracite 900:** on Discord's and GitHub's dark
sidebars, `#1C1B1E` is within a step or two of the chrome and the tile edge disappears —
the glyph floats with no avatar shape around it. `#2E2C30` holds its edge on every dark
chrome tested and still reads as black on light. It is also, as it happens, the value
this started from.

The **favicon is the one exception to full-bleed**: it keeps the icon's own rounded tile,
because a browser tab applies no rounding of its own.

---

## 3.5 — Geometry (for anyone rebuilding this)

The supplied SVGs are 1920×1080 slides with the artwork floating in the middle. Tight
boxes, measured with `getBBox()`:

| mark | viewBox to crop to |
|---|---|
| monogram | `747.98 376.33 424.06 327.35` |
| extended logotype | `652.81 458.95 614.68 162.12` |
| icon | `797.03 377.02 325.95 325.95` |

In the monogram, **the bottom of that box is the baseline** — the `e+k` sits on it, and
the detached pixel hangs *above* it, not below. An inline `<svg>` therefore aligns itself
to adjacent text with no vertical correction. (The `t` is raised; its own bottom edge at
`y=638.89` is not the baseline. This is the trap — do not align to the `t`.)

Clear space and minimum sizes: manual §3.2, unchanged.

---

## 4.3 — Colour: the dark mode

**Corporate is light. The department is dark.** That is the whole differentiation, and it
costs no new assets: same marks, same palette, same type — different room.

### The palette, all of it from manual §4.2

| token | hex | role |
|---|---|---|
| `--ink-900` | `#1C1B1E` Antracite 900 | page ground |
| `--ink-800` | `#2E2C30` Grigio 800 | raised surface — rows on hover, code, tiles |
| `--ink-700` | `#46444A` Grigio 700 | rules and borders **only** (1.78:1 — never text) |
| `--ink-500` | `#726F76` Grigio 500 | dim text, ≥24px only (3.47:1) |
| `--ink-300` | `#A6A3A9` Grigio 300 | body text (6.88:1) |
| `--ink-150` | `#D4D2D6` Grigio 150 | lead text, emphasis (11.42:1) |
| `--paper` | `#F7F5F3` Bianco sporco | headings, marks (15.76:1) |
| `--rosso` | `#e13b4c` Rosso primario | identity — **on the mark only** |
| `--verde` | `#22c55e` Successo | signal (7.52:1) |

### Why green, stated honestly

Manual §4.1 is explicit: *"Il rosso è l'unico colore identitario."* This addendum does not
contradict it — **green is never an identity colour here.** It is a state the system
reports. The parentage argument is made by red, which stays on the mark on every page.

The reason green is *needed* is measurable, not stylistic:

> On `#1C1B1E`, Rosso primario reaches **4.03:1**. That is below the 4.5:1 threshold for
> body text — red works as a mark and as large type, and fails as a link, a label or a
> state. Green reaches **7.52:1** (AAA). Once the channel goes dark, the palette contains
> exactly one accent that is legible as text, and §4.2 already specifies it.

If red must ever be set as text on dark, use **Rosso chiaro `#f15c69`** (5.29:1), never
Rosso primario.

### Where green is allowed

The pixel in the mark · the §6.1 step rule · hover and focus states · the active item in
a set · one emphasis per block of running text · genuine machine output (a passing test, a
green diff line).

**Where it is not:** headings, body text, borders, large fills, or as a second colour in
any mark. Green marks the thing that is *live*; if everything is green, nothing is.

### Guardrails

- `--ink-500` fails on `--ink-800` (2.80:1). Anything that sits on a raised surface must
  be `--ink-300` or brighter.
- Every combination above was measured, not eyeballed. Re-measure before adding a token.

---

## 5.2 — Type

Manual §5.1, unchanged: **Space Grotesk** and **Overpass Mono**, both Google Fonts. The
logotype is built from Space Grotesk, so display type set in it rhymes with the mark.

What this addendum adds is the split in *role*:

- **Space Grotesk** — headings (700, tight tracking, sentence case), titles (500), running
  text (300–400). Sentence case, not uppercase: the face's character is in its lowercase.
- **Overpass Mono** — all chrome: eyebrows, metadata, numbers, navigation, colophon,
  the department descriptor. 10–11px, uppercase, tracked `.14–.2em`.

Mono is not decoration on this channel — it is the working voice, and it carries every
piece of text the system printed rather than a person wrote.

---

## 6.2 — Graphic elements

### The step

Manual §6.1's motif is two 4.03-unit squares offset diagonally, repeating. It is the
department's rule and divider, **in green**.

One exact period of the official `Divider_teksistemi.svg` is **103.93 × 8.15** units, with
step-pairs at x = 0, 24.19, 52.62, 76.81 and alternating y offsets — the spacing is
deliberately irregular, so tile the real period rather than inventing a regular one.
Implement as a `mask-image` over a solid colour, never as a hard-coded coloured asset, so
one file serves both the red (corporate) and green (department) forms.

### The watermark

The manual sets an oversized monogram bleeding off the format on nearly every page. On
dark, that is `#1F1E22` on `#1C1B1E` — a whisper, about 1.1:1. Anything more legible
competes with the headline. It bleeds off the right edge and is clipped by the format;
the clip is the point.

### What we do not use

No grid overlays, no generic tech patterns, no gradients, no glow. The archive's front
door used a hairline grid before this system; it belonged to no one and it is gone.

---

## 7.1 — Voice

Codified from what the newsletter already does, not invented for it.

- **Lead with the measurement, not the claim.** A number, a date, a case — then the point.
- **Name the trap explicitly.** "Don't simplify this into X: X reintroduces the bug."
- **The receipt stays, the essay moves.** The dated fact lives where the work is; the
  derivation goes in the document beside it. This is already the house rule for code
  comments; it is the same rule for writing.
- **Italian is the source, English is a twin** — not a summary. Every issue ships both.
- **First person plural, about our own work.** We describe what we did and what it cost.
- **No hype register.** No exclamation marks, no "rivoluzionario", no "game changer". If a
  result is good the number says so.
- **Say when something failed.** An issue that only reports wins is marketing.

---

## Applying this

**Frozen issues stay frozen.** Issues 001–008 keep their own palettes — each one is a
bespoke design and the archive rule is that published issues never change. This system
governs the **index pages** and **new issues** from 009 on.

Worth noting on the way past: issue 008 independently landed on `#21c55d` on near-black —
one digit from the green specified here. The department was already reaching for it.

### Open items

1. **`tekdevelopment` vector from WMC** — see §2.3. The one real blocker.
2. **Sign-off on green as a signal colour** from whoever owns the corporate brand. The
   argument is in §4.3; the contrast numbers are the case.
3. **Light mode for the department**, if we ever need to print or present. Not designed
   yet; it would be the manual's own light system plus the green pixel.
