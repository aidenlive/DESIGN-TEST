---
version: alpha
name: Acid Mono
description: >-
  A reusable, monochrome-first baseline design system. Neutral OKLCH grays carry
  the entire UI; a single acid-lime accent drives primary action, with reserved
  pink and violet secondaries. Defines both light and dark themes. Intended to be
  attached as a starting point and overridden per project. Derived from the
  crd.onl development standards (OKLCH color science, 4px grid, DM Sans +
  JetBrains Mono, mobile-first, 24-column fluid grid). All foreground/background
  pairs are verified to WCAG 2.1 AA.

colors:
  # ---- Neutral ramp (monochrome-first; pure grays, C=0) ----
  neutral-0:         "oklch(1.0 0.0 0)"  # #FFFFFF
  neutral-50:        "oklch(0.9851 0.0 0)"  # #FAFAFA
  neutral-100:       "oklch(0.9642 0.0 0)"  # #F3F3F3
  neutral-200:       "oklch(0.9219 0.0 0)"  # #E5E5E5
  neutral-300:       "oklch(0.8607 0.0 0)"  # #D1D1D1
  neutral-400:       "oklch(0.7604 0.0 0)"  # #B1B1B1
  neutral-500:       "oklch(0.6401 0.0 0)"  # #8C8C8C
  neutral-600:       "oklch(0.5313 0.0 0)"  # #6C6C6C
  neutral-700:       "oklch(0.4054 0.0 0)"  # #494949
  neutral-800:       "oklch(0.3012 0.0 0)"  # #2E2E2E
  neutral-900:       "oklch(0.2046 0.0 0)"  # #171717
  neutral-950:       "oklch(0.1591 0.0 0)"  # #0D0D0D
  neutral-1000:      "oklch(0.1149 0.0 0)"  # #050505

  # ---- Brand accents (use sparingly; neutrals carry the UI) ----
  acid:              "oklch(0.9281 0.2304 123.98)"  # #C8FF00  primary action / signature highlight
  acid-deep:         "oklch(0.7468 0.1854 124.0)"  # #95BF00  acid hover/pressed fill
  acid-soft:         "oklch(0.9679 0.0849 124.25)"  # #E8FFC0  pale acid tint (light-mode highlight bg)
  pill:              "oklch(0.662 0.2444 1.68)"  # #FF2E88  secondary accent (selection, special badges)
  ultra:             "oklch(0.5153 0.2787 280.52)"  # #5B2CFF  tertiary accent (light-mode links/focus)

  # ---- Status (semantic feedback; tuned distinct from brand accents) ----
  danger:            "oklch(0.6256 0.1933 23.03)"  # #E5484D  base (icon/border; dark-mode text)
  danger-strong:     "oklch(0.5849 0.1924 23.22)"  # #D63A41  light-mode text / solid fill (white text)
  danger-soft:       "oklch(0.9601 0.0196 21.36)"  # #FFEDEC  light-mode soft bg
  danger-soft-dark:  "oklch(0.2717 0.07 22.94)"  # #431616  dark-mode soft bg
  warning:           "oklch(0.7819 0.1585 72.33)"  # #F5A524  base (icon/border; dark-mode text)
  warning-strong:    "oklch(0.5605 0.1199 72.19)"  # #9F6700  light-mode text
  warning-soft:      "oklch(0.9598 0.0305 72.18)"  # #FFEFDC  light-mode soft bg
  warning-soft-dark: "oklch(0.2695 0.0574 72.88)"  # #372100  dark-mode soft bg
  success:           "oklch(0.6271 0.1699 149.21)"  # #16A34A  base (icon/border; dark-mode text)
  success-strong:    "oklch(0.5385 0.1515 149.13)"  # #008538  light-mode text
  success-soft:      "oklch(0.9604 0.0605 148.71)"  # #D7FEDC  light-mode soft bg
  success-soft-dark: "oklch(0.2689 0.0691 149.3)"  # #052F12  dark-mode soft bg
  info:              "oklch(0.6847 0.1479 237.32)"  # #0EA5E9  base (icon/border; dark-mode text)
  info-strong:       "oklch(0.5557 0.1217 237.18)"  # #007CB1  light-mode text
  info-soft:         "oklch(0.9593 0.0217 239.42)"  # #E5F4FF  light-mode soft bg
  info-soft-dark:    "oklch(0.2705 0.0598 237.78)"  # #002A40  dark-mode soft bg

  # ---- Semantic roles ----
  # Convention: the BASE token holds the LIGHT-theme value; the matching `*-dark`
  # token holds the DARK-theme override. Components below reference only base
  # tokens; a dark-theme build remaps each base -> its `*-dark` value.
  bg:                  "{colors.neutral-50}"     # app canvas
  bg-dark:             "{colors.neutral-1000}"
  surface:             "{colors.neutral-0}"      # card / raised panel
  surface-dark:        "{colors.neutral-900}"
  surface-2:           "{colors.neutral-0}"      # higher elevation (light: via shadow; dark: via lift)
  surface-2-dark:      "{colors.neutral-800}"
  surface-hover:       "{colors.neutral-100}"    # row/control hover
  surface-hover-dark:  "{colors.neutral-800}"
  text:                "{colors.neutral-900}"    # body text
  text-dark:           "{colors.neutral-50}"
  text-strong:         "{colors.neutral-1000}"   # headings / max emphasis
  text-strong-dark:    "{colors.neutral-0}"
  text-muted:          "{colors.neutral-600}"    # secondary text (>=4.5:1)
  text-muted-dark:     "{colors.neutral-400}"
  text-subtle:         "{colors.neutral-500}"    # placeholder/disabled label (non-essential, UI 3:1)
  text-subtle-dark:    "{colors.neutral-500}"
  border:              "{colors.neutral-200}"    # decorative divider / hairline
  border-dark:         "{colors.neutral-800}"
  border-strong:       "{colors.neutral-500}"    # interactive boundary (>=3:1, WCAG 1.4.11)
  border-strong-dark:  "{colors.neutral-600}"
  accent:              "{colors.acid}"           # same in both themes (fill)
  accent-dark:         "{colors.acid}"
  on-accent:           "{colors.neutral-1000}"   # text/glyph on acid fill (jet)
  on-accent-dark:      "{colors.neutral-1000}"
  accent-soft:         "{colors.acid-soft}"
  accent-soft-dark:    "oklch(0.3 0.08 124)"     # dark lime tint
  link:                "{colors.ultra}"          # interactive text (light: violet, readable)
  link-dark:           "{colors.acid}"           # interactive text (dark: acid, readable)
  focus:               "{colors.ultra}"          # focus ring (light)
  focus-dark:          "{colors.acid}"           # focus ring (dark)
  selection:           "{colors.acid-soft}"      # text selection bg
  selection-dark:      "oklch(0.3 0.08 124)"
  danger-text:         "{colors.danger-strong}"  # inline status text on page bg
  danger-text-dark:    "{colors.danger}"
  warning-text:        "{colors.warning-strong}"
  warning-text-dark:   "{colors.warning}"
  success-text:        "{colors.success-strong}"
  success-text-dark:   "{colors.success}"
  info-text:           "{colors.info-strong}"
  info-text-dark:      "{colors.info}"
  danger-bg:           "{colors.danger-soft}"    # status container bg (pair with neutral text)
  danger-bg-dark:      "{colors.danger-soft-dark}"
  warning-bg:          "{colors.warning-soft}"
  warning-bg-dark:     "{colors.warning-soft-dark}"
  success-bg:          "{colors.success-soft}"
  success-bg-dark:     "{colors.success-soft-dark}"
  info-bg:             "{colors.info-soft}"
  info-bg-dark:        "{colors.info-soft-dark}"

typography:
  # Display: Space Grotesk, reserved for hero/statement type only.
  display-lg:
    fontFamily: Space Grotesk
    fontSize: 60px
    fontWeight: 600
    lineHeight: 1.05
    letterSpacing: -0.03em
  display-md:
    fontFamily: Space Grotesk
    fontSize: 44px
    fontWeight: 600
    lineHeight: 1.08
    letterSpacing: -0.02em
  # Headlines / titles: DM Sans semibold, tight tracking.
  headline-lg:
    fontFamily: DM Sans
    fontSize: 36px
    fontWeight: 600
    lineHeight: 1.1
    letterSpacing: -0.02em
  headline-md:
    fontFamily: DM Sans
    fontSize: 28px
    fontWeight: 600
    lineHeight: 1.15
    letterSpacing: -0.015em
  headline-sm:
    fontFamily: DM Sans
    fontSize: 22px
    fontWeight: 600
    lineHeight: 1.2
    letterSpacing: -0.01em
  title-md:
    fontFamily: DM Sans
    fontSize: 18px
    fontWeight: 500
    lineHeight: 1.3
    letterSpacing: -0.006em
  # Body: DM Sans regular. body-md is the base (16px).
  body-lg:
    fontFamily: DM Sans
    fontSize: 18px
    fontWeight: 400
    lineHeight: 1.6
  body-md:
    fontFamily: DM Sans
    fontSize: 16px
    fontWeight: 400
    lineHeight: 1.6
  body-sm:
    fontFamily: DM Sans
    fontSize: 14px
    fontWeight: 400
    lineHeight: 1.55
  # Labels: DM Sans medium, for UI controls.
  label-md:
    fontFamily: DM Sans
    fontSize: 14px
    fontWeight: 500
    lineHeight: 1.2
    letterSpacing: 0.005em
  label-sm:
    fontFamily: DM Sans
    fontSize: 12px
    fontWeight: 600
    lineHeight: 1.2
    letterSpacing: 0.02em
    fontFeature: '"tnum" 1'   # tabular figures (often set UPPERCASE via CSS)
  # Mono: JetBrains Mono, for data, code, timestamps, metadata.
  mono-md:
    fontFamily: JetBrains Mono
    fontSize: 14px
    fontWeight: 400
    lineHeight: 1.5
    fontFeature: '"tnum" 1'
  mono-sm:
    fontFamily: JetBrains Mono
    fontSize: 12px
    fontWeight: 400
    lineHeight: 1.5
    letterSpacing: 0.01em
    fontFeature: '"tnum" 1'
  caption:
    fontFamily: DM Sans
    fontSize: 12px
    fontWeight: 400
    lineHeight: 1.4

rounded:
  none: 0px
  xs: 2px
  sm: 4px
  md: 8px
  lg: 12px
  xl: 16px
  2xl: 24px
  full: 9999px

spacing:
  base: 4px           # grid base; all spacing is a multiple of 4px
  xs: 4px
  sm: 8px
  md: 16px
  lg: 24px
  xl: 40px
  2xl: 64px
  3xl: 96px
  gutter: 24px        # grid column gutter
  margin: 24px        # page margin (mobile may tighten to 16px)
  columns: 24         # 24-column fluid grid (unitless)
  container: 1280px   # max application width
  content: 1200px     # max content width inside the container
  measure: 42rem      # optimal reading width for prose (~66ch at body-md)
  tap-target: 44px    # minimum interactive target size (a11y)

# `shadows` is an extension group beyond the core schema (consumers that do not
# recognize it should preserve it). Shadows are deliberately subtle and tuned to
# jet (5,5,5). In dark mode prefer tonal lift + borders over shadow (see Elevation).
shadows:
  none: "none"
  sm: "0 1px 2px rgba(5,5,5,0.06), 0 1px 1px rgba(5,5,5,0.04)"
  md: "0 2px 4px rgba(5,5,5,0.05), 0 4px 12px rgba(5,5,5,0.08)"
  lg: "0 8px 16px rgba(5,5,5,0.08), 0 16px 32px rgba(5,5,5,0.10)"

# Components reference only BASE semantic tokens; a dark build remaps base -> *-dark.
# `borderColor`, `borderWidth`, and `boxShadow` are extension properties (accepted
# with a warning by strict consumers).
components:
  button-primary:
    backgroundColor: "{colors.accent}"
    textColor: "{colors.on-accent}"
    typography: "{typography.label-md}"
    rounded: "{rounded.md}"
    padding: "10px 16px"
    height: 40px
  button-primary-hover:
    backgroundColor: "{colors.acid-deep}"
  button-primary-active:
    backgroundColor: "{colors.acid-deep}"
  button-primary-disabled:
    backgroundColor: "{colors.neutral-200}"
    textColor: "{colors.neutral-500}"
  button-secondary:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.text}"
    borderColor: "{colors.border-strong}"
    borderWidth: 1px
    typography: "{typography.label-md}"
    rounded: "{rounded.md}"
    padding: "10px 16px"
    height: 40px
  button-secondary-hover:
    backgroundColor: "{colors.surface-hover}"
  button-ghost:
    backgroundColor: "transparent"
    textColor: "{colors.text}"
    typography: "{typography.label-md}"
    rounded: "{rounded.md}"
    padding: "10px 16px"
    height: 40px
  button-ghost-hover:
    backgroundColor: "{colors.surface-hover}"
  button-danger:
    backgroundColor: "{colors.danger-strong}"
    textColor: "{colors.neutral-0}"
    typography: "{typography.label-md}"
    rounded: "{rounded.md}"
    padding: "10px 16px"
    height: 40px
  input:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.text}"
    borderColor: "{colors.border-strong}"
    borderWidth: 1px
    typography: "{typography.body-md}"
    rounded: "{rounded.sm}"
    padding: "10px 12px"
    height: 40px
  input-focus:
    borderColor: "{colors.focus}"   # plus a 2px ring of {colors.focus}; see Components prose
  input-error:
    borderColor: "{colors.danger}"
  input-disabled:
    backgroundColor: "{colors.neutral-100}"
    textColor: "{colors.text-subtle}"
  chip:
    backgroundColor: "{colors.surface-hover}"
    textColor: "{colors.text}"
    typography: "{typography.label-sm}"
    rounded: "{rounded.full}"
    padding: "6px 12px"
    height: 28px
  chip-selected:
    backgroundColor: "{colors.accent}"
    textColor: "{colors.on-accent}"
  checkbox:
    backgroundColor: "{colors.surface}"
    borderColor: "{colors.border-strong}"
    borderWidth: 1.5px
    rounded: "{rounded.xs}"
    size: 18px
  checkbox-checked:
    backgroundColor: "{colors.accent}"
    textColor: "{colors.on-accent}"   # checkmark glyph
    borderColor: "{colors.accent}"
  radio:
    backgroundColor: "{colors.surface}"
    borderColor: "{colors.border-strong}"
    borderWidth: 1.5px
    rounded: "{rounded.full}"
    size: 18px
  radio-selected:
    borderColor: "{colors.accent}"
    textColor: "{colors.accent}"      # inner dot
  tooltip:
    backgroundColor: "{colors.neutral-900}"
    textColor: "{colors.neutral-50}"
    typography: "{typography.label-sm}"
    rounded: "{rounded.sm}"
    padding: "6px 8px"
  card:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.text}"
    borderColor: "{colors.border}"
    borderWidth: 1px
    rounded: "{rounded.lg}"
    padding: "24px"
    boxShadow: "{shadows.sm}"
  list-item:
    backgroundColor: "transparent"
    textColor: "{colors.text}"
    typography: "{typography.body-md}"
    padding: "12px 16px"
  list-item-hover:
    backgroundColor: "{colors.surface-hover}"
  badge:
    backgroundColor: "{colors.neutral-900}"
    textColor: "{colors.neutral-50}"
    typography: "{typography.label-sm}"
    rounded: "{rounded.sm}"
    padding: "2px 8px"
  badge-accent:
    backgroundColor: "{colors.accent}"
    textColor: "{colors.on-accent}"
---

# Acid Mono — Baseline Design System

A general-purpose, reusable `DESIGN.md` intended to be **attached as a baseline** at
the start of a design or build session and then **overridden per project**. The
tokens in the front matter are normative; the prose below explains intent and how to
apply them. The system is derived from the crd.onl development standards — OKLCH color
science, monochrome-first palette, a 4px grid, DM Sans + JetBrains Mono, mobile-first
layout, and a 24-column fluid grid.

**How to use it.** Keep the neutral ramp, type system, spacing, and component grammar
as-is for consistency across projects. Per project, you typically change only: the
`name`, the accent trio (`acid` / `pill` / `ultra`) if the brand calls for different
hues, and any component padding/sizing the product needs. Re-run a contrast check
after changing any color that carries text.

**Theming.** Both light and dark themes are defined. Each semantic role has a base
token (light value) and a `*-dark` override (dark value). A dark build resolves every
base token to its `*-dark` counterpart; components reference only base tokens, so the
swap is mechanical. See the role table under Colors.

## Overview

The personality is **engineered, precise, and high-contrast** — a quiet monochrome
substrate with one electric jolt of color. Think instrument panel, not poster: the
interface is mostly Jet, Carbon, and Paper, and the Acid Lime appears only where the
product wants the eye to go. Restraint is the brand. The accent earns its impact
because it is rare; if everything is acid, nothing is.

The intended feel is calm and legible under dense information, with personality
delivered through typographic discipline (tight headline tracking, tabular mono for
data) rather than decoration. It suits tools, dashboards, developer products, and
data-forward apps for a technically literate audience. When a specific rule or token
is not defined, prefer the choice that is more neutral, more legible, and more
systematic — and spend boldness in exactly one place per screen.

## Colors

The palette is **monochrome-first**: a perceptually even neutral ramp (built in OKLCH,
chroma 0) does almost all the work, anchored by **Jet (#050505)** at one end and
**Paper (#FFFFFF)** at the other. Color is reserved.

- **Jet (`neutral-1000`, #050505) → Paper (`neutral-0`, #FFFFFF):** the full grayscale
  ramp. Surfaces, text, borders, and dividers are all drawn from it. Stops are spaced
  for even perceived contrast, so adjacent steps read as deliberate tiers.
- **Acid Lime (`acid`, #C8FF00):** the single signature accent and the only color used
  for the primary action on a screen. It is a *fill* color paired with Jet text — it is
  intentionally too light to use as text on a light surface (see Don'ts).
- **Hot Pill (`pill`, #FF2E88):** reserved secondary accent for selection states,
  special badges, and a second categorical series in data viz. Used sparingly.
- **Ultraviolet (`ultra`, #5B2CFF):** tertiary accent. It doubles as the light-mode
  interactive color (links, focus ring) because, unlike Acid, it is dark enough to read
  as text on white.
- **Status — Signal Red, Amber, Green, Sky:** semantic feedback only (error, warning,
  success, info). Hues were tuned to stay visually distinct from the brand accents, so
  "success green" never reads as "acid" and "info sky" never reads as "ultra."

### Interactive color, by theme

Acid is the brand's highlight but is only readable as text/marks on dark surfaces, so
the interactive (link/focus) color flips by theme: **Ultraviolet in light mode**,
**Acid in dark mode**. The primary-button *fill* is Acid in both themes (always with
Jet text).

### Semantic role → token (light / dark)

| Role | Light (base token → value) | Dark (`*-dark` → value) |
|---|---|---|
| `bg` (canvas) | `neutral-50` · #FAFAFA | `neutral-1000` · #050505 |
| `surface` (card) | `neutral-0` · #FFFFFF | `neutral-900` · #171717 |
| `surface-2` (raised) | `neutral-0` + shadow | `neutral-800` · #2E2E2E |
| `surface-hover` | `neutral-100` · #F3F3F3 | `neutral-800` · #2E2E2E |
| `text` | `neutral-900` · #171717 (17.9:1) | `neutral-50` · #FAFAFA (19.5:1) |
| `text-strong` | `neutral-1000` · #050505 | `neutral-0` · #FFFFFF |
| `text-muted` | `neutral-600` · #6C6C6C (5.25:1) | `neutral-400` · #B1B1B1 (9.5:1) |
| `text-subtle` | `neutral-500` · #8C8C8C (3.36:1, non-essential) | `neutral-500` · #8C8C8C (6.06:1) |
| `border` (divider) | `neutral-200` · #E5E5E5 | `neutral-800` · #2E2E2E |
| `border-strong` (control) | `neutral-500` · #8C8C8C (3:1) | `neutral-600` · #6C6C6C (3:1) |
| `accent` (fill) | `acid` · #C8FF00 | `acid` · #C8FF00 |
| `on-accent` | `neutral-1000` · #050505 (17.2:1) | `neutral-1000` · #050505 |
| `link` / `focus` | `ultra` · #5B2CFF (6.46:1) | `acid` · #C8FF00 (15.2:1 on surface) |
| `danger-text` | `danger-strong` · #D63A41 (4.6:1) | `danger` · #E5484D (5.2:1) |
| `warning-text` | `warning-strong` · #9F6700 (4.8:1) | `warning` · #F5A524 (10:1) |
| `success-text` | `success-strong` · #008538 (4.8:1) | `success` · #16A34A (6.2:1) |
| `info-text` | `info-strong` · #007CB1 (4.7:1) | `info` · #0EA5E9 (7.4:1) |

Contrast ratios in parentheses are against that theme's canvas/surface and meet WCAG
2.1 AA (4.5:1 body text; 3:1 large text, UI boundaries, and non-essential text).

**Status containers.** A status message uses the soft background (`danger-bg`, etc.)
with **neutral `text`** for the message body and the status `*-text` color for the icon,
leading element, or border. Colored text directly on a soft tint can dip below 4.5:1, so
reserve the colored `*-text` tokens for status text on the page canvas.

## Typography

Three roles, each with a deliberate job. The type is meant to be a visible part of the
identity, not a neutral delivery vehicle.

- **Display — Space Grotesk (Semi-Bold):** reserved for hero and statement type only
  (`display-lg`, `display-md`). Its geometric character gives big moments personality;
  using it below ~40px dilutes that, so it does not appear in body or UI.
- **Headlines, titles, body, labels — DM Sans:** the workhorse. Headlines are Semi-Bold
  with tight negative tracking for an engineered, confident voice. Body is Regular at a
  **16px base** with a 1.6 line height for long-form readability. UI labels are Medium.
- **Data, code, timestamps, metadata — JetBrains Mono:** all technical and numeric
  content. Tabular figures (`"tnum"`) keep columns aligned; small mono (`mono-sm`,
  `label-sm`) is often set UPPERCASE with added tracking for metadata rows.

The scale runs `display-lg → caption` (14 levels). Keep weight usage disciplined:
Regular and Semi-Bold for DM Sans, plus Medium for labels — avoid stacking more weights
on a single screen. Set headings in `text-strong`, body in `text`, and secondary
content in `text-muted`.

## Layout

A **mobile-first**, **24-column fluid grid**. Lay out for the narrow viewport first,
then add columns as space allows; the 24-column count divides cleanly into 2/3/4/6/8/12
tracks for flexible composition. Gutters are `24px`; page margins are `24px` (tightening
to `16px` on small screens). Application width is capped at `container` (1280px), main
content at `content` (1200px), and running prose at `measure` (~42rem / ~66 characters)
for readability.

All spacing derives from a strict **4px grid** (`base`), using the `xs…3xl` steps; reach
for the 4px increments rather than arbitrary values to keep vertical and horizontal
rhythm consistent. Related elements are grouped into cards with generous internal
padding (`24px`).

**No flex-wrap.** Do not rely on `flex-wrap` for responsive reflow — wrapped flex items
produce uneven, unpredictable breaks. Use the grid (with explicit column counts per
breakpoint) or deliberate, controlled overflow instead. Reserve at least `tap-target`
(44px) for any interactive target. Align optically: trust the eye over raw numbers for
icons, punctuation, and mixed cap-height rows.

## Elevation & Depth

Depth is conveyed primarily through **tonal layers**, with shadows kept subtle — never
heavy or colored.

- **Light theme:** the canvas is a soft off-white (`bg`, #FAFAFA) and content sits on
  pure white cards (`surface`, #FFFFFF). That tonal step provides the first level of
  lift; higher elevation (menus, popovers) adds a soft neutral shadow (`shadows.sm` →
  `lg`) rather than going lighter, since white is already the ceiling.
- **Dark theme:** elevation is expressed by **getting lighter**. The canvas is Jet
  (#050505); surfaces step up through `neutral-900` → `neutral-800` as they rise. Shadows
  largely disappear on near-black, so depth comes from these tonal steps plus a hairline
  `border-dark`. Apply shadow only for true overlays, and keep it faint.

Use one elevation step at a time; do not combine a large shadow with a strong tonal jump.

## Shapes

The shape language is **precise with a touch of softness**. The default corner radius is
`sm` (4px) for inputs and small controls and `md` (8px) for buttons; cards use `lg`
(12px). Pills, avatars, chips, and toggles use `full`. Keep radii consistent within a
view — mixing sharp 0px corners and soft radii in the same surface reads as accidental.
Data-dense surfaces (tables, code blocks, terminals) may use `none`/`xs` for a more
engineered, gridded feel, applied consistently across that surface.

## Components

Components reference semantic tokens, so they theme automatically when base tokens are
remapped to their `*-dark` values. Standard control height is `40px`; standard control
radius is `md` for buttons and `sm` for inputs.

- **Buttons.** *Primary* is the Acid fill with Jet text — at most one per screen, for the
  single most important action. *Secondary* is a surface fill with a `border-strong`
  outline and `text`. *Ghost* is transparent with `text`, for low-emphasis actions.
  *Danger* uses the solid `danger-strong` fill with white text for destructive actions.
  Hover shifts primary to `acid-deep` and secondary/ghost to `surface-hover`.
- **Inputs.** Resting state is a `surface` field with a `border-strong` outline (meets the
  3:1 boundary requirement). Focus sets the border to the `focus` color **and** adds a 2px
  ring of that color (offset by the surface) — the focus ring carries the primary,
  high-contrast affordance and must always remain visible. Error state borders use
  `danger`; show helper/error text below in `body-sm`.
- **Chips.** Pill-shaped (`full`). Unselected chips use `surface-hover`; selected chips
  use the Acid fill with Jet text. Filter/selection chips may use `pill` for a second
  selection dimension.
- **Checkboxes & radios.** 18px, with a `border-strong` outline at rest. The checked /
  selected state fills with Acid; the checkmark or inner dot is `on-accent` (Jet) for
  contrast.
- **Tooltips.** Inverse and compact: a `neutral-900` surface with `neutral-50` text,
  `sm` radius, `label-sm` type. Keep copy to a short phrase.
- **Lists.** Rows use `body-md` with `12px / 16px` padding and a `surface-hover`
  background on hover; separate rows with a `border` hairline, not heavy rules.
- **Badges.** Default badge is `neutral-900` on light text for neutral metadata; the
  `badge-accent` variant uses Acid + Jet for emphasis. Use the accent badge sparingly.

Define additional, domain-specific components by following the same grammar (a base key
plus `-hover` / `-active` / `-selected` / `-disabled` variants) and referencing existing
tokens rather than introducing new raw values.

## Do's and Don'ts

- **Do** let neutrals carry the interface; treat Acid as punctuation, not paragraph.
- **Do** use the Acid accent for only the single most important action per screen.
- **Don't** use Acid (`#C8FF00`) as text or icons on a light surface — it fails contrast.
  It is a fill paired with Jet text, or an accent on dark surfaces only.
- **Do** use Ultraviolet for links/focus in light mode and Acid for links/focus in dark
  mode; keep the focus ring visible at all times (2px, offset).
- **Do** maintain WCAG AA: 4.5:1 for body text, 3:1 for large text, UI boundaries, and
  meaningful graphics. Re-check any color you change that sits under text.
- **Don't** put colored status text on a soft status tint; pair soft backgrounds with
  neutral `text` and reserve the colored `*-text` tokens for the page canvas.
- **Do** keep everything on the 4px grid and prefer the named spacing steps.
- **Don't** use `flex-wrap` for responsive layout — use the 24-column grid or controlled
  overflow.
- **Do** convey depth with tonal layers first (lighter = higher in dark mode); keep
  shadows subtle and neutral.
- **Don't** mix sharp (0px) and soft (8–12px) corners within the same surface.
- **Don't** exceed Regular + Semi-Bold (plus Medium for labels) on one screen, and don't
  use Space Grotesk below ~40px.
- **Do** meet a quality floor without announcing it: responsive to mobile, visible
  keyboard focus, 44px targets, and reduced-motion respected.
