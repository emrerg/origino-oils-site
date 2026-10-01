# Origino Design System

Origino is a direct-to-consumer olive oil brand, and an experiment on the
traditional agricultural business model. It picks the olives from trees it
looks after itself, cold-presses them within hours, and delivers the oil in
750ml tins. Before each season it asks subscribers to reserve a place in the
coming harvest; sensing demand that way lets it give farmers purchase
guarantees above local market prices before picking starts.

The thing that makes the brand a design problem rather than a packaging
problem is what happens after delivery. The tin carries a QR code, and
scanning it opens an app that replays the full journey of *that* oil — who
picked it, where, when, which mill pressed it within how many hours, which
laboratory tested it, and what the free-acidity and polyphenol numbers came
back as. Traceability is the product.

## Sources

Everything here was extracted from two artefacts supplied by the user. Neither
is included in this project; if you have access, they are the ground truth.

- **`Origino Unpacking.fig`** — a Figma file, mounted read-only during the
  build. Page 1 holds 14 top-level frames: nine designed app screens, one
  component-showcase frame, and four pasted reference screenshots of the live
  `origino.co.uk` bottle page. Page 2 is empty. All values in `tokens/` are
  transcribed from it verbatim.
- **`uploads/Origino Brand Guide_rev3.pdf`** — a 40-page brand guide dated
  2024, covering the model, mood board, personality, a six-alternative colour
  palette exploration, typography, logo construction and don'ts, the
  typographic pattern, business card, a presentation template, two tin designs
  and two re-usable pouch designs.

Where the two disagree, the Figma file wins: it is the newer, built artefact.
The brand guide's typographic specification (Matcha + IBM Plex Mono) was not
carried into the app, which is set entirely in Neue Haas Grotesk Display Pro.

## Products represented

One product surface is designed: **Origino Unpacking**, the mobile journey app
(`ui_kits/unpacking/`). The marketing site exists only as flattened
screenshots pasted into the Figma file, so it is deliberately *not* recreated
here — recreating it would mean inventing a design, not importing one.

The brand guide additionally specifies non-screen surfaces — 750ml tin, 500ml
pouch, business card, presentation deck — which are documented below but have
no component counterpart, because no editable source for them was supplied.

---

## Content fundamentals

**The app talks like a person who was there.** Copy is written in first person
plural about Origino and second person about the reader: "We pick the olives
from the trees we look after on our own." "Your Origino® finally has reached
its final destination." "We want you to view the full journey of your olive
oil."

**Headlines are questions or arrivals.** The app opens with `Hi\nthere!` and
proceeds by asking what the reader is about to be told: *"How do you
distinguish quality olive oil from others?"*, *"What are the most appropriate
storage conditions?"*, *"Storage?"*. The answer follows immediately in a
smaller size, never as a separate click.

**Sentences trail off with ellipses when a stage is about to open.** "And it's
been an adventurous journey…", "The less the better…", "The more the better…".
This is the app's one piece of voice decoration and it is used sparingly.

**Facts are labelled, not narrated.** Every provenance value is a
small-caps label over a value, never a sentence: `HARVEST DATE / November 8th,
2023` · `GROVE LOCATION / Northwest of Iznik Lake, Bursa, Turkiye` · `HEAD
CULTIVATOR / Turker Yalcinkaya (42)` · `TIME BETWEEN PICKING & PRESSING /
<12 hours` · `PRESSING TEMPERATURE / 24C (Cold Pressed)`. Ages are given in
parentheses. Distances and temperatures keep their units attached. Nothing is
rounded for comfort.

**Casing.** Sentence case for headlines and body. UPPERCASE for data labels
and for button text (`RESERVE`, `OR BUY WHILE IN STOCK`). Never title case.
The brand guide sets the logotype and its lock-ups in lowercase, and letter-
spaces the tagline wide: `F R O M  O R I G I N O  W I T H  F U L L  J O U R N E Y`.

**Action links read as invitations, not commands.** "See the picking stories
→", "See the pressing stories →", "Review test results →". They name the
reward, not the mechanic.

**Brand guide vocabulary** to draw on when writing new copy — from the mood
board: *minimalist, simple, explained, modern, elegant, healthy*; from the
personality page: *Trustworthy, Authentic, Roots, Compassionate, Crafty, Fair,
Longevity, Guilt-free, Pleasure*. The brand describes its own personality as
leaning feminine, youthful, uncomplicated, contemporary, friendly and
approachable rather than authoritative.

**No emoji.** None appear in either source. The registered mark on `Origino®`
is used in body copy. `©` appears once, in the footer: `© 2025 Origino`.

---

## Visual foundations

**The core move is a dark, full-bleed photograph with type sitting directly on
it.** No cards, no containers, no rounded panels. Screens are either a black
ground carrying a photo, a flat saturated green ground, or a white/`#F5F5F5`
explainer panel. Two background colours per screen at most.

**Colour.** Greens do the work, and they run hot. The grounds are deep —
`--green-olive #006837`, `--green-deep #00532C` — and the accents are almost
fluorescent: `--signal-green #59E631` for the provenance stages,
`--signal-neon #38FF00` on the ultramarine `--blue-lab #0224E2` lab panels,
`--signal-chartreuse #D4E631` on the black Storage page. Mid greens
(`--green-grass #29BA00`, `--green-leaf #1DA111`) are section grounds. The
brand guide's five named roles — olive, farmer, health, sea, sunset — survive
in the app as this green family plus the blue lab ground and the four-step lab
quality scale (`#2892EF` best → `#86CA46` → `#FBBF12` → `#EF3E25` worst).

**Type.** One family, three weights. Neue Haas Grotesk Display Pro at 55
Roman, 65 Medium and 75 Bold. The scale is not a ratio, it is a set of
literal sizes the designer chose: 100/80 for the hero, 82.481/82.481 for the
cover, 48/64 for display, 44.25 for type over photography, 40/40 and 32/32 for
titles, 24/24 for stage names, 20/24 for body, 18/24 for actions, 16/24 for
uppercase labels, 14/28 for captions. Negative tracking (−2% on hero and
display, −1% on stats and actions) is what gives it the tight, modern feel.
Hero type hard-wraps mid-word when it has to: `Sto\nrage?`.

**Spacing.** A 20px outer gutter on dark screens, 40px on the white cover.
393 screen → 353 card → 313 content. Stack gaps are 1, 8, 10, 12, 16, 20, 30,
60, 90 — no 4/8 grid, and the 1px gap is load-bearing: it is how the accordion
rows let their ground colour through as a hairline.

**Corner radii.** Mostly zero. Rows, panels, swatches, the glass location
plates and the blue lab blocks are all square. The exceptions are deliberate:
12px on the device frame, 8px on the top corners of the white cover sheet,
32px on the bottom corners of a masked photo sheet, 40px on pill CTAs, 100px
on the story progress segments and home indicator.

**Cards.** There are none in the usual sense — no shadow, no border, no
rounding. What looks like a card is a full-width block of flat colour butted
against its neighbours. Where a boundary is needed the design uses a 1px inset
`box-shadow` in `--signal-green` or `--green-olive`, not a border property.

**Shadow and blur.** Exactly one shadow in the whole file:
`0 4px 4px rgba(0,0,0,0.63)`, used only on large type sitting over
photography. Exactly one blur: `blur(4px)` behind a `rgba(0,0,0,0.3)` plate
carrying a location label. Elevation is otherwise expressed by colour, not
depth.

**Protection gradients over capsules.** Type over photography is protected by
a bottom-up scrim — `linear-gradient(0deg, rgba(0,0,0,0.5), rgba(0,0,0,0))`,
144px tall over a 874px screen, 277px over an inline 393px media block — never
by a pill or chip behind the text.

**Transparency and blend modes.** Used structurally, not decoratively. A
`rgba(0,104,55,0.3)` wash defines the open body of an accordion row. A solid
`--green-olive` layer in `mix-blend-mode: hard-light` tints grove photography
green. A white layer at 70% in `mix-blend-mode: color` desaturates the
"Testing & Quality" photo almost to monochrome. Muted body copy on dark is
`rgba(255,255,255,0.5)`; muted chart rules on light are `rgba(0,0,0,0.1)`.

**Imagery.** Warm, unstylised, documentary — hands in olive nets, groves at
dusk, a stone mill, the tin itself. No grain overlay, no duotone, no
illustration. Product renders sit on flat saturated green. The brand guide
also defines a *typographic* pattern as the only graphic device: the vertical
Origino logotype at 50% transparency, letters repeating, always starting from
the bottom.

**Layout rules.** Fixed elements are the 40px close glyph at `left:333,
top:40`, the 21px home-indicator strip at the bottom, and the story progress
rail at `left:32, top:809`. Everything else is absolutely positioned against
the 20px gutter. Long screens (up to 5213px) are one continuous scroll, not
paginated.

**Animation.** The source specifies none — no transitions, no prototype flows.
`tokens/space.css` therefore proposes a house convention rather than
documenting one: `--ease-standard: cubic-bezier(0.2,0,0,1)`,
`--dur-accordion: 280ms` for row open/close, `--dur-fade: 180ms` for
cross-fades. Treat these as the default to apply, and expect the brand team to
have opinions.

**Hover and press states.** Also unspecified — the source is a mobile design
with no hover surface. The convention to follow: on dark grounds, lighten the
accent toward `--signal-neon`; on light grounds, darken toward
`--green-deep`. Press states shift colour rather than scale, in keeping with a
system that has no shadows to compress.

---

## Iconography

Two systems, used for different jobs, and both are copied into this project
rather than approximated.

**1. A custom agriculture glyph set** carries the meaning. These are solid
single-colour SVG shapes at 32px (60px once, over a photo), drawn as filled
paths rather than strokes: olives on a branch (`013-olives-3`), an olive
branch (`001-olive-branch`), a stone mill (`006-stone-mill`), a packing crate,
an acidity dropper-and-flask, and a bespoke `O` used as the "Oxygen" mark on
the Storage page. They live in `assets/icons/` — the twelve pieces of the set
as lifted from the component-showcase frame are in `assets/icons/set/`, plus
`olives-a.svg`, `olives-b.svg`, `olive-branch.svg` and `oxygen-o.svg`. Because
they are authored as solid shapes with a baked fill, recolour them by swapping
the fill, not with `currentColor`. Several compose from two or three
overlapping paths — keep them together.

**2. Remix Icon (line, system)** carries the chrome: `close-line` at 40px,
`arrow-down-s-line` at 32px for the accordion chevron, `arrow-right-line` at
24px trailing action links, `arrow-right-s-line` at 32px as a drill-in caret.
These are shipped as real components (`RemixIconsLineSystemClose`,
`RemixIconsLineSystemArrow`, `…Arrow2`, `…Arrow3`) and paint with
`currentColor`, so they can be recoloured freely. Remix Icon is open source
(Apache 2.0) and CDN-available if more glyphs are needed — match the `line`
style, never mix in `fill`.

**3. Font Awesome 6 Pro** appears on the Storage page via a Figma library
component (`v6-icon`, `family=classic style=light`) for the *brightness* and
*temperature-half* glyphs. It is font-based and carries no extractable vector
geometry, so it could not be materialised. It is also a paid licence, so no
substitute is shipped. See Caveats.

No emoji. No unicode characters pressed into service as icons. The `®` and `©`
marks are typographic, not iconographic.

---

## Font status — read this before designing

| Token | Family specified | Status |
|---|---|---|
| `--font-core` | Neue Haas Grotesk Display Pro (55/65/75) | **Shipped**, self-hosted from `fonts/`. 8 cuts × roman + italic. Weight ladder: 100 XXThin · 200 XThin · 300 Thin · 400 Light · **500 Roman** · **600 Medium** · **700 Bold** · 900 Black — mapped so the numeric weights already in the components hit the faces the designer used. |
| `--font-logotype` | Matcha | **Missing.** Licensed; not supplied. Falls back to Didot → Times. |
| `--font-mono` | IBM Plex Mono | **Shipped** (open licence, Google Fonts). |
| *(no token)* | Kepler, Quasimodo | Brand-guide digital-media alternatives. Nothing in this system uses them, so no token is declared — adding one would create a font dependency with no consumer. Raise it if the alternatives are adopted. |

Tokens keep the real family names. Neue Haas Grotesk Display Pro is now
self-hosted, so every screen and specimen renders in the real face. Matcha is
still outstanding — uploading it will fix the logotype token in one move.
Nothing is silently substituted; the Matcha fallback stack is chosen to be
metrically sane, not to imitate.

## Logo status

**There is no logo asset in this project, and none was drawn.** The Figma file
contains no logo layer — the wordmark never appears as a component, image or
vector in any frame. The brand guide contains the real mark (pages 21–26:
logo form, the olive cradled in the belly of the `g`, the missing tittles on
the `i`s, the horizontal and spine lock-ups, and the don'ts), but as embedded
vector art that could not be extracted here.

Until an SVG or PNG is supplied, render the brand name as plain type — set in
`--font-logotype`, lowercase, slightly letter-spaced — as `thumbnail.html`
does. Do not reconstruct the mark.

---

## Index

**Root**
- `readme.md` — this file.
- `styles.css` — the global entry point. `@import` lines only.
- `thumbnail.html` — the homepage tile.
- `SKILL.md` — Agent Skills front-matter wrapper.
- `uploads/Origino Brand Guide_rev3.pdf` — the source brand guide.

**`tokens/`** — `fonts.css` · `colors.css` · `typography.css` · `space.css` ·
`base.css`. All `:root` custom properties; 131 tokens.

**`fonts/`** — Neue Haas Grotesk Display Pro, 16 `.ttf` files (8 weights ×
roman + italic), wired up in `tokens/fonts.css`.

**`assets/`** — `icons/` (agriculture glyph set + `oxygen-o.svg`),
`icons/set/` (the twelve pieces as extracted), `imagery/` (`grove-dusk.png`,
`harvest-hands.png`, `bottle-back.png`, `olive-tree-branch.png`).

**`guidelines/`** — 17 foundation specimen cards feeding the Design System tab,
grouped Colors · Type · Spacing · Brand.

**`components/journey/`** — the component library.

| Component | What it is |
|---|---|
| `Component3` | The journey accordion. 10 variants (`name` × `state`). |
| `Rectangle613` | Story progress segment. 2 variants. |
| `RemixIconsLineSystemClose` | `close-line`, 40px. |
| `RemixIconsLineSystemArrow` | `arrow-down-s-line`, 32px chevron. |
| `RemixIconsLineSystemArrow2` | `arrow-right-line`, 24px action arrow. |
| `RemixIconsLineSystemArrow3` | `arrow-right-s-line`, 32px caret. |

`Component3` keeps its Figma name deliberately: the source file never named
it, and renaming it to `JourneyAccordion` here would break the mapping back to
node `1:1162` that a designer needs when comparing. The same goes for
`Rectangle613`. See "Intentional additions" below for the full naming rationale.

**`ui_kits/unpacking/`** — the Origino Unpacking app. See its `README.md` for
the screen table. Screen components: `OriginoJourney`, `OriginoJourney2`,
`OriginoJourney3`, `OriginoJourney4`, `OriginoJourney5`, `OriginoJourney6`,
`OriginoJourney7`, `OriginoJourney8`, `Storage` — each named after its Figma
frame (`Origino - Journey`, eight times over, plus `Storage`).

### Intentional additions

No primitive was invented. Every component maps to something the source
defines, and no Button, Input, Card, Toast or Tabs primitive was authored,
because the source defines none — the app's two buttons are one-off pill
blocks inside screen 02 of the UI kit, and abstracting them into a `Button`
component would be an invention.

Eleven built components carry names that are not component-set names in the
Figma file. **All eleven are intentional, and all are named after something
real in the source.** Confirming each:

- `OriginoJourney`, `OriginoJourney2`, `OriginoJourney3`, `OriginoJourney4`,
  `OriginoJourney5`, `OriginoJourney6`, `OriginoJourney7`, `OriginoJourney8`,
  `Storage` — these are **screens, not primitives**. Each is named after its
  top-level Figma frame. Eight frames in the file are all literally named
  `Origino - Journey`, so they are numbered in file order; the ninth frame is
  named `Storage`. They live in `ui_kits/unpacking/` and exist so the app's
  nine designed screens are reachable as code. Renaming them to invented
  labels would break the mapping back to their frame ids, which is the one
  thing a designer needs when comparing against Figma.
- `RemixIconsLineSystemArrow2` and `RemixIconsLineSystemArrow3` — these *are*
  standalone components in the file, listed under "Standalone
  components/symbols" in its metadata as `remix-icons/line/system/arrow-right-line`
  and `remix-icons/line/system/arrow-right-s-line`. The numeric suffixes exist
  only because all four Remix glyph paths collapse to the same PascalCase stem
  (`RemixIconsLineSystemArrow…`) and the names have to stay unique. The mapping
  is documented in the component table above and in
  `RemixIconsLineSystemClose.prompt.md`.

`Component3` and `Rectangle613` keep their Figma names for the same reason:
the source file never gave them better ones, and renaming them here would
break the mapping back to nodes `1:1162` and `1:6`.

---

## Caveats

1. **`v6-icon` (Font Awesome 6 Pro) could not be materialised** — 480 variants,
   font-based, no vector geometry in the file. Two glyphs on the Storage screen
   are consequently absent. Supplying a Font Awesome Pro kit, or a decision to
   swap in an open alternative, would close this.
2. **The logo is missing** (see Logo status). This is the biggest gap.
3. **Matcha (the logotype face) is missing** (see Font status). Neue Haas
   Grotesk Display Pro has been supplied and is self-hosted, so the app
   screens and specimens now render in the real face.
4. **No colour palette hexes were read from the brand guide** — its six palette
   alternatives are vector swatches that could not be sampled in this
   environment. The colour tokens come from the Figma file instead, which is
   the later and more authoritative source, but the brand guide's named roles
   (olive / farmer / health / sea / sunset) are mapped by inference, not by
   measured value.
5. **The marketing site is not recreated.** Only flattened screenshots of
   `origino.co.uk` exist in the source.
6. **No motion, hover or press states are specified** in either source. What
   `tokens/space.css` carries are proposals.
7. **Screens are static recreations.** The source file has no prototype flows,
   so the UI kit's step rail is scaffolding this project added, not a
   navigation model the design specifies.
