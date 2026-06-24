---
version: alpha
name: publicne.ws
description: >-
  Visual system for publicne.ws, an AI-accelerated news synthesis layer.
  Translated from the canonical Stylebook v.2026.04. Three colors (paper, ink,
  signal red), three type families (Sora, DM Sans, JetBrains Mono), a 4px
  spacing scale, and one easing curve. Light and dark modes both encoded.
  Tokens are normative; prose explains application. OKLCH is the source format
  (sRGB hex shown in comments as fallback). Values tagged "inferred" extend the
  system consistently but are not in the canonical source.

colors:
  # ── Key palette · roles per DESIGN.md convention ──
  primary: "oklch(12% 0.008 260)"        # Ink   · sRGB ≈ #040608 · core text, wordmark, identity
  secondary: "oklch(52% 0.008 260)"      # Slate · sRGB ≈ #66696e · metadata, captions, muted text
  tertiary: "oklch(60% 0.24 27)"         # Signal red · sRGB ≈ #ee0f1f · sole interaction accent
  neutral: "oklch(98% 0.003 100)"        # Paper · sRGB ≈ #f9f8f6 · page foundation

  # ── Surfaces · light (paper → tonal lift) ──
  surface: "{colors.neutral}"            # = Paper
  surface-2: "oklch(94% 0.003 100)"      # sRGB ≈ #ebebe9
  surface-3: "oklch(90% 0.004 100)"

  # ── Text on surface · light ──
  on-surface: "{colors.primary}"         # = Ink
  on-surface-soft: "oklch(30% 0.008 260)"  # sRGB ≈ #2b2e32
  on-surface-muted: "{colors.secondary}"   # = Slate

  # ── Lines / dividers · light (hairlines) ──
  outline: "oklch(88% 0.004 260)"
  outline-strong: "oklch(82% 0.005 260)" # sRGB ≈ #c2c4c7

  # ── Accent family · signal red ──
  accent: "{colors.tertiary}"            # base red
  accent-strong: "oklch(66% 0.26 27)"    # red-hi · WIDE-GAMUT (clips to sRGB #ff413c) · emphasis / dark contrast
  accent-ghost: "oklch(95% 0.04 27)"     # near-white red wash · full-bleed hover tint (light)

  # ── Surfaces · dark ──
  surface-dark: "oklch(9% 0.008 260)"        # canonical · inverse ink · sRGB ≈ #020204
  surface-2-dark: "oklch(13% 0.008 260)"     # inferred
  surface-3-dark: "oklch(17% 0.008 260)"     # inferred

  # ── Text on surface · dark ──
  on-surface-dark: "{colors.neutral}"        # canonical intent · Paper on Ink
  on-surface-soft-dark: "oklch(75% 0.006 260)"   # inferred
  on-surface-muted-dark: "oklch(58% 0.008 260)"  # inferred

  # ── Lines · dark ──
  outline-dark: "oklch(26% 0.006 260)"       # inferred
  outline-strong-dark: "oklch(32% 0.006 260)" # inferred

  # ── Accent · dark ──
  accent-dark: "{colors.accent-strong}"      # canonical · red-hi for dark-mode contrast
  accent-ghost-dark: "oklch(24% 0.07 27)"    # inferred · dark hover tint

typography:
  # Sizes are nominal Dimensions; the live scale is fluid via clamp() — see Typography prose.
  display:
    fontFamily: Sora
    fontSize: 7rem              # nominal; fluid up to clamp(4rem, 20vw, 18rem) at hero
    fontWeight: 800
    lineHeight: 0.95            # inferred (display tightening)
    letterSpacing: -0.055em
  headline-lg:
    fontFamily: Sora
    fontSize: 4rem              # --fs-2xl cap · clamp(2.25rem, 5vw, 4rem)
    fontWeight: 700
    lineHeight: 1.05            # inferred
    letterSpacing: -0.04em      # inferred (tracking scaled from hero)
  headline-md:
    fontFamily: Sora
    fontSize: 2.25rem           # --fs-xl cap · clamp(1.5rem, 2.5vw, 2.25rem)
    fontWeight: 700
    lineHeight: 1.1             # inferred
    letterSpacing: -0.02em      # inferred
  headline-sm:
    fontFamily: Sora
    fontSize: 1.375rem          # --fs-lg
    fontWeight: 600
    lineHeight: 1.2             # inferred
    letterSpacing: -0.01em      # inferred
  body-lg:
    fontFamily: DM Sans
    fontSize: 1.125rem          # --fs-md
    fontWeight: 400
    lineHeight: 1.5
  body-md:
    fontFamily: DM Sans
    fontSize: 1rem              # --fs-base
    fontWeight: 400
    lineHeight: 1.5
  body-sm:
    fontFamily: DM Sans
    fontSize: 0.82rem           # --fs-sm
    fontWeight: 400
    lineHeight: 1.5
  label-md:
    fontFamily: JetBrains Mono
    fontSize: 0.82rem           # --fs-sm · uppercase eyebrow / chip
    fontWeight: 500
    lineHeight: 1
    letterSpacing: 0.1em
  label-sm:
    fontFamily: JetBrains Mono
    fontSize: 0.72rem           # --fs-xs
    fontWeight: 500
    lineHeight: 1
    letterSpacing: 0.1em
  data:
    fontFamily: JetBrains Mono
    fontSize: 1rem              # telemetry, IDs, timestamps
    fontWeight: 400
    lineHeight: 1.4             # inferred
    fontFeature: "tnum"         # tabular-nums

rounded:
  none: 0px        # default for every rectangular element — sharp, engineered
  full: 9999px     # dots only — live pulse, status dots
  # No intermediate radii exist by design; see Shapes.

spacing:
  base: 4px
  s-1: 4px
  s-2: 8px
  s-3: 12px
  s-4: 16px
  s-5: 24px
  s-6: 32px
  s-8: 48px
  s-10: 72px
  s-12: 96px
  s-16: 144px
  gutter: "clamp(18px, 5vw, 56px)"   # fluid — stored as string
  grid-columns: 12                    # unitless
  max-width: 1600px

components:
  chip:                                # canonical
    backgroundColor: transparent
    textColor: "{colors.on-surface}"
    typography: "{typography.label-sm}"
    borderColor: "{colors.outline-strong}"   # non-standard prop (accepted w/ warning) — border defines the chip
    rounded: "{rounded.none}"
    padding: 6px                       # inferred
  chip-status-live:                    # canonical — dot + label, pulses on 1.8s
    textColor: "{colors.accent}"
    typography: "{typography.label-sm}"
  button-primary:                      # inferred — ink "black tile" applied to actions; default button
    backgroundColor: "{colors.primary}"
    textColor: "{colors.neutral}"
    typography: "{typography.label-md}"
    rounded: "{rounded.none}"
    padding: 12px
  button-primary-hover:                # inferred
    backgroundColor: "{colors.on-surface-soft}"
  button-accent:                       # inferred — single highest-emphasis/live action only; use sparingly
    backgroundColor: "{colors.accent}"
    textColor: "{colors.neutral}"      # ⚠ 4.2:1 — label must be large/bold to clear AA (see Contrast)
    typography: "{typography.label-md}"
    rounded: "{rounded.none}"
    padding: 12px
  button-accent-hover:                 # inferred
    backgroundColor: "{colors.accent-strong}"
  input:                               # inferred
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    typography: "{typography.body-md}"
    borderColor: "{colors.outline-strong}"   # ⚠ 1.7:1 vs paper — add a stronger cue for boundary/focus (see Contrast)
    rounded: "{rounded.none}"
    padding: 10px
---

# publicne.ws — Design System

*Translated from the canonical **Stylebook v.2026.04**. The YAML tokens above are normative; this prose explains how to apply them. The Stylebook documents color, type families, the type scale, spacing, grid, and motion explicitly — it does **not** specify corner radii, fully composed type levels, dark-mode intermediate steps, or button/input specs, so those are derived here and marked **inferred**. Confirm inferred values against the live build and fold them into the next revision (v.2026.05). Contrast figures are measured (WCAG 2.1).*

## Overview

publicne.ws is an **AI-accelerated news synthesis layer** — it reads the record other outlets keep and publishes a faster, cross-referenced, continuously re-audited index into it. The visual system exists to enforce that position: **technical, declarative, human-accountable**. Agent-operated, human-edited, every correction signed.

The product is built for two readers at once — a person scanning for the answer, and a machine extracting passages — so the UI is dense but disciplined: structured, legible, and honest about being run by disclosed agents. It should never read as a "serious journalism" broadsheet in costume, nor as a hidden AI farm. Precision over decoration; specificity over polish.

**Wordmark.** The mark is the domain name with its dot as a heartbeat: set in **JetBrains Mono, lowercase only**, `publicne` at weight 600 and `ws` at weight 500. The dot is **always Signal red** — the pulse of the publication — and is never recolored, outlined, stretched, or rotated. The lockup sits on one of three grounds: Paper, Ink, or a single Signal-red bleed.

## Colors

Three colors, not thirty. **Paper**, **Ink**, and one bright **Signal red**; everything else is a tonal step between them. Signal red is punctuation — the live dot, section accents, at most one full-bleed moment per page. It is never a large background.

- **Paper** (`neutral` / `surface`, `oklch(98% 0.003 100)`) — a barely-warm off-white founding every page and card. Lifts to `surface-2` / `surface-3` for layered containment.
- **Ink** (`primary` / `on-surface`, `oklch(12% 0.008 260)`) — a barely-cool near-black for body text, the wordmark, and inverted backgrounds. Softens through `on-surface-soft` and the `secondary` slate for metadata and captions.
- **Signal red** (`tertiary` / `accent`, `oklch(60% 0.24 27)`) — the sole driver of interaction and liveness. `accent-strong` (red-hi) raises contrast for dark mode and emphasis; `accent-ghost` is a near-white wash for full-bleed hover tints.
- **Hairlines** (`outline`, `outline-strong`) — borders and dividers do the structural work shadows would do elsewhere.

The neutral ladder is deliberately near-hueless: surfaces sit on hue 100 (faintly warm), text and lines on hue 260 (faintly cool). No hue-shifting grays.

**Why OKLCH.** The format is the source of truth, not a stylistic choice — `accent-strong` (red-hi) is a wide-gamut color that falls outside sRGB and only clips down to ≈`#ff413c`. Keeping OKLCH preserves the intended chroma on P3 displays; the hex values in the token comments are sRGB fallbacks.

**Light and dark.** Dark mode inverts the relationship: the base surface becomes inverse Ink (`surface-dark`, `oklch(9% 0.008 260)`), text becomes Paper (`on-surface-dark`), and the accent shifts to red-hi (`accent-dark`). Raised surfaces get *lighter*, never shadowed. The intermediate dark steps (raised surfaces, soft/muted text, outlines) are **inferred** by mirroring the light ladder around the dark base — verify against the live dark theme.

**Forbidden.** Never introduce orange (hue 40–60), teal (160–200), blue (220–260), or purple (280–320) as a brand color. If a second accent is ever needed, it must be a second red — warmer or cooler — not a new hue.

**Contrast (measured, WCAG 2.1).** The monochrome base is excellent; the red is the constraint.

- Ink ↔ Paper — **19:1 (AAA)** both directions. Body text and primary (ink) buttons are unconstrained.
- `on-surface-soft` on Paper — **12.9:1 (AAA)**. `secondary` slate on Paper — **5.2:1 (AA)**, fine for metadata at body size.
- **Signal red on Paper — 4.2:1.** Passes AA for **large/bold text only** (≥24px, or ≥18.66px bold). Do not set small red body text or small red links on Paper; reserve red for the dot, large numerals, bold emphasis, and accents.
- **Paper text on a red accent button — 4.2:1.** Same constraint: the label must be large/bold, otherwise it fails AA. Because mono labels are typically small, prefer the **ink `button-primary`** (19:1) for text actions and keep `button-accent` for sparing, high-emphasis use.
- Dark mode — Paper on inverse Ink **19.5:1 (AAA)**; red-hi on `surface-dark` **5.9:1 (AA)**; red on Ink **4.6:1 (AA)**.
- Hairlines (`outline` / `outline-strong`) sit ≈**1.7:1** on Paper — intentionally subtle and below the 3:1 non-text threshold. Fine as dividers, but where a border is the *only* indicator of an interactive boundary or focus (e.g., `input`), pair it with a stronger cue (darker outline or the accent focus ring) to reach 3:1.

## Typography

Three voices, each with one job, and they don't trade places. **Sora** carries display weight; **DM Sans** explains; **JetBrains Mono** holds the data.

- **Display & headlines — Sora** (`display`, `headline-lg/md/sm`): weights 700–800, tracking tightens at scale, down to `-0.055em` at hero. Section titles, big numerals, question-headlines.
- **Body — DM Sans** (`body-lg/md/sm`): weights 400–700, line-height 1.5 for long-form readability. All explanatory prose.
- **Data — JetBrains Mono** (`data`, `label-md/sm`): weights 400–600 with **tabular numerals**, reserved for telemetry, timestamps, IDs, and chips. Labels are uppercase with `0.1em` tracking. Never body prose; no serif italic standing in for editorial drama.

**Scale.** Sizes are **fluid**, built with `clamp()` on roughly a 1.25 ratio. The `fontSize` tokens record a static nominal per level; the live ladder is:

`--fs-hero` clamp(4rem, 20vw, 18rem) · `--fs-3xl` clamp(3rem, 8vw, 7rem) · `--fs-2xl` clamp(2.25rem, 5vw, 4rem) · `--fs-xl` clamp(1.5rem, 2.5vw, 2.25rem) · `--fs-lg` 1.375rem · `--fs-md` 1.125rem · `--fs-base` 1rem · `--fs-sm` 0.82rem · `--fs-xs` 0.72rem

DESIGN.md dimensions can't hold a `clamp()` expression, so each level's `fontSize` is the nominal value and the fluid range lives here. Per-level line-heights and the scaled letter-spacing on headlines are **inferred**; only the hero tracking (`-0.055em`), body line-height (1.5), and mono tracking (`0.1em`) are canonical. The composed levels themselves are a synthesis — the Stylebook documents family, weight, and size as independent axes rather than pre-bundled levels.

Hierarchy in context runs **Eyebrow (mono label) → Title (Sora) → Body (DM Sans) → Data (mono)**.

## Layout

A **4px base unit**, a **fluid 12-column grid**, and a willingness to break the grid when the content earns it — asymmetry earns attention; randomness doesn't.

The spacing scale runs `s-1` (4px) → `s-16` (144px), non-linear past `s-6`: it skips to s-8, s-10, s-12, s-16 for larger rhythm. T-shirt equivalents for portability: `s-1`≈xs, `s-2`≈sm, `s-4`≈md, `s-6`≈lg, `s-8`≈xl. The grid uses a fluid `gutter` of `clamp(18px, 5vw, 56px)` and caps at `max-width` 1600px.

## Elevation & Depth

Depth comes from **tonal layers and hairlines, not shadows** — there are no shadow tokens. A page founds on `surface` (Paper); raised or contained content steps up through `surface-2` and `surface-3`, separated by `outline` / `outline-strong` hairlines. The metadata strip and operator cards are built entirely from borders and tonal contrast. In dark mode the same logic runs in reverse: raised surfaces get lighter.

## Shapes

The shape language is **sharp and orthogonal**. Tiles, cards, chips, inputs, and buttons use a **0px radius** (`rounded.none`) — engineered, not soft. The Stylebook specifies no radius scale, which is itself the decision: there are no intermediate rounded steps. The only round form is the **dot** — the live pulse and status dots — expressed with `rounded.full`. (A small `2px` softening is intentionally omitted; if one is ever introduced, add it as a single named step, not a ladder.)

## Components

Connective tissue is tiny, repeated, and mono-voiced. **Chips are canonical**; **buttons and inputs are inferred** from observed admin usage plus the existing tokens, and should be confirmed against the live components.

- **Chip** (`chip`): a 1px hairline border, transparent fill, uppercase JetBrains Mono at `0.1em` tracking. Type chips, filter chips, and metadata share this skeleton. *(`borderColor` is a non-standard DESIGN.md property — consumers accept it with a warning; it's included because the border is the chip's defining feature.)*
- **Status chip** (`chip-status-live`): a dot plus label; the live variant uses Signal red and pulses on a 1.8s cycle.
- **Primary button** (`button-primary`, *inferred*): Ink fill, Paper text, sharp corners — the "black tile" identity applied to actions, and the default for text actions (19:1 contrast). Hover lifts the fill toward `on-surface-soft`.
- **Accent button** (`button-accent`, *inferred*): Signal-red fill for the single highest-emphasis or live action on a view — used sparingly, never as the default. Its label must be **large or bold** to clear AA (4.2:1); hover goes to `accent-strong`.
- **Input** (`input`, *inferred*): Paper surface, Ink text, a hairline `outline-strong` border, sharp corners, DM Sans at body size. The border alone is ~1.7:1 — add a darker outline or an accent focus ring so the boundary meets 3:1.

## Motion

Motion moves with intent — nothing animates without a reason.

- **Easing:** `cubic-bezier(0.16, 1, 0.3, 1)` ("decelerate") — fast start, long settle. The default for all reveals, hovers, and state changes.
- **Durations:** Micro **200ms** (hover, focus rings, toggles) · Component **500ms** (card reveals, underline sweeps, theme switch) · Section **900ms** (hero type rise, page entry, ambient pulses).
- **Meaning:** live pulses confirm an agent is alive, reveals introduce sections, stat fades confirm updates. Everything else stays still.
- **Always honor `prefers-reduced-motion`** — ship a dignified static variant for every animated element.

## Do's and Don'ts

- **Do** reserve Signal red for one purpose at a time — the live dot, a section accent, or at most one full-bleed moment per page.
- **Don't** use red as a large background, set small red text on Paper, or recolor / outline / stretch / rotate the wordmark dot.
- **Do** keep each type family in its lane: Sora for display, DM Sans for body, JetBrains Mono for data and IDs.
- **Don't** introduce a non-red accent hue, mix in hue-shifting grays, or set body prose in mono.
- **Do** keep corners sharp throughout — never mix rounded and orthogonal shapes in one view.
- **Do** treat space as a tool: use the 4px scale, and break the 12-column grid only when content earns it (asymmetry, not randomness).
- **Do** honor `prefers-reduced-motion`, and use the single easing curve and three duration tiers for anything that moves.
- **Do** write to the house rules: answer the question in the first 200 words, phrase headings as questions, prefer specific numbers, keep every paragraph extractable, sign every correction — and never call anything "AI-powered" or open with "in today's fast-paced world."
- **Do** hold WCAG AA (4.5:1 body): Ink/Paper clears it at 19:1; verify any text set in `secondary` slate, and treat Signal red as large/bold-only on Paper.
