---
version: alpha
name: Studio
description: >-
  A single-product design system for a personal library / collection app, built
  on the iOS 26 "floating glass" vocabulary: a cool-neutral palette tuned for one
  electric lime accent, a wide geometric display face (Bounded), an editorial
  serif used only for a two-tone italic accent (Instrument Serif), a tight
  grotesk for the interface (Inter Tight), and a mono for captions and data
  (JetBrains Mono). One accent, one material, restraint as the brand. Token
  values below are the light theme; dark is documented in the Colors section.
colors:
  # — Primary: LIME, the single brand hue (the sole driver for interaction) —
  primary: "oklch(78% 0.22 138)"
  on-primary: "oklch(18% 0.06 145)"
  primary-soft: "oklch(78% 0.22 138 / 0.16)"
  primary-line: "oklch(64% 0.2 142)"
  primary-glow: "oklch(78% 0.22 138 / 0.5)"
  # — Surfaces (back → front). A single cool neutral ramp, hue 270. —
  background: "oklch(98% 0.003 270)"
  background-edge: "oklch(95% 0.004 270)"
  surface: "oklch(100% 0 0)"
  surface-2: "oklch(96.2% 0.004 270)"
  surface-3: "oklch(93% 0.005 270)"
  # — On-surface text inks (1 = primary → 4 = faint) —
  on-surface: "oklch(14% 0.012 270)"
  on-surface-2: "oklch(40% 0.009 270)"
  on-surface-3: "oklch(56% 0.007 270)"
  on-surface-4: "oklch(72% 0.006 270)"
  # — Outline (hairline borders; -strong on hover) —
  outline: "oklch(88% 0.006 270)"
  outline-strong: "oklch(78% 0.008 270)"
  # — Status —
  error: "oklch(58% 0.23 22)"
  success: "oklch(64% 0.16 150)"
  # — Material / scrim —
  scrim: "oklch(14% 0.01 270 / 0.34)"
  glass-surface: "oklch(100% 0 0 / 0.72)"
  glass-outline: "oklch(100% 0 0 / 0.65)"
typography:
  # — Display: Bounded, the wide geometric brand face. Negative tracking,
  #   near-1.0 line-height. Pair with a serif-italic <em> (see prose). —
  headline-display:
    fontFamily: Bounded
    fontWeight: 500
    fontSize: 72px        # responsive: clamp(40px, 6vw, 72px)
    lineHeight: 0.98
    letterSpacing: -0.03em
  headline-lg:
    fontFamily: Bounded
    fontWeight: 500
    fontSize: 56px        # responsive: clamp(34px, 4.5vw, 56px)
    lineHeight: 1.0
    letterSpacing: -0.03em
  headline-md:
    fontFamily: Bounded
    fontWeight: 500
    fontSize: 26px
    lineHeight: 1.12
    letterSpacing: -0.025em
  headline-sm:
    fontFamily: Bounded
    fontWeight: 500
    fontSize: 22px
    lineHeight: 1.12
    letterSpacing: -0.022em
  # — Body: Inter Tight —
  body-lg:
    fontFamily: Inter Tight
    fontWeight: 400
    fontSize: 17px
    lineHeight: 1.65
    fontFeature: "'ss01'"
  body-md:
    fontFamily: Inter Tight
    fontWeight: 400
    fontSize: 15px
    lineHeight: 1.55
    letterSpacing: -0.005em
  # — Labels: Inter Tight, interface text, slightly tight, weight 500 —
  label-lg:
    fontFamily: Inter Tight
    fontWeight: 500
    fontSize: 14px
    lineHeight: 1.2
    letterSpacing: -0.008em
  label-md:
    fontFamily: Inter Tight
    fontWeight: 500
    fontSize: 13px
    lineHeight: 1.2
    letterSpacing: -0.005em
  # — Captions: JetBrains Mono. ALWAYS uppercase + wide tracking (see prose;
  #   text-transform is not a token property). Kickers, group labels, metadata. —
  caption-lg:
    fontFamily: JetBrains Mono
    fontWeight: 500
    fontSize: 10.5px
    lineHeight: 1
    letterSpacing: 0.16em
  caption-md:
    fontFamily: JetBrains Mono
    fontWeight: 600
    fontSize: 10px
    lineHeight: 1
    letterSpacing: 0.16em
  caption-sm:
    fontFamily: JetBrains Mono
    fontWeight: 500
    fontSize: 10px
    lineHeight: 1
    letterSpacing: 0.08em
  # — Inline mono data: emails, counts, kbd. Not uppercase; tabular numerals. —
  mono-inline:
    fontFamily: JetBrains Mono
    fontWeight: 400
    fontSize: 11px
    lineHeight: 1.4
    letterSpacing: 0.04em
    fontFeature: "'tnum'"
rounded:
  xs: 6px       # source --r-xs; note: accent tags / focus ring use a 4px hardcode
  sm: 10px
  md: 14px
  lg: 20px
  xl: 28px
  full: 999px   # source --r-pill
spacing:
  # 4px base scale. Key = ×4 multiplier (1 → 4px, 16 → 64px).
  "1": 4px
  "2": 8px
  "3": 12px
  "4": 16px
  "5": 20px
  "6": 24px
  "8": 32px
  "10": 40px
  "12": 48px
  "16": 64px
  # Fixed layout metrics
  sidebar: 256px
  sidebar-rail: 76px
  header: 72px
  float-inset: 14px       # floating chrome offset from viewport edges
components:
  # Extended properties used beyond the base set (borderColor, borderWidth,
  # shadow, gap, size) are permitted by the spec on an accept-with-warning basis.
  # `shadow` values name a tier defined in "Elevation & Depth".

  # — Buttons —
  button-primary:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    borderColor: "{colors.primary-line}"
    borderWidth: 0.5px
    rounded: "{rounded.md}"
    height: 42px
    padding: 20px         # horizontal; vertical is 0 (height-controlled)
    typography: "{typography.label-lg}"   # rendered at weight 600 / 13.5px
    shadow: raised-primary
  button-primary-hover:
    shadow: raised-primary-strong         # + translateY(-1px)
  button-primary-active: {}               # scale(0.97)
  button-cta:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    borderColor: "{colors.primary-line}"
    borderWidth: 0.5px
    rounded: "{rounded.full}"
    height: 38px
    padding: 16px
    typography: "{typography.label-md}"   # weight 600 / 13px
    shadow: raised
  button-neutral:
    backgroundColor: "{colors.on-surface}"
    textColor: "{colors.background}"
    rounded: "{rounded.md}"
    height: 42px
    padding: 20px
    typography: "{typography.label-lg}"   # weight 600 / 13.5px
    shadow: raised
  button-icon:
    backgroundColor: "{colors.surface-2}"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.full}"             # circular
    height: 40px
    width: 40px
    size: 18px            # glyph size
  button-icon-hover:
    backgroundColor: "{colors.surface-3}"
  button-icon-active: {}                  # scale(0.90)
  button-ghost:
    backgroundColor: "{colors.surface-2}"
    textColor: "{colors.on-surface}"
    rounded: "{rounded.full}"
    height: 34px
    padding: 16px
    typography: "{typography.label-md}"
  button-ghost-danger:
    textColor: "{colors.error}"

  # — Chips (filter) —
  chip:
    backgroundColor: transparent
    textColor: "{colors.on-surface-2}"
    borderColor: "{colors.outline}"
    borderWidth: 0.5px
    rounded: "{rounded.full}"
    height: 32px
    padding: 14px
    typography: "{typography.label-md}"
  chip-active:                            # inverts to solid ink
    backgroundColor: "{colors.on-surface}"
    textColor: "{colors.background}"
    borderColor: "{colors.on-surface}"

  # — Badges, tags, type-pills (mono micro-labels) —
  badge:
    backgroundColor: "{colors.surface-2}"
    textColor: "{colors.on-surface-3}"
    rounded: "{rounded.full}"
    height: 18px
    padding: 6px
    typography: "{typography.caption-md}"
  badge-accent:
    backgroundColor: "{colors.primary-soft}"
    textColor: "{colors.primary-line}"
  tag:                                    # accent corner tag
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    rounded: "{rounded.xs}"               # source: 4px (between none and xs)
    padding: 8px
    typography: "{typography.caption-sm}" # weight 600 / 9.5px / 0.12em
  type-pill:
    backgroundColor: "{colors.surface-2}"
    textColor: "{colors.on-surface-2}"
    rounded: "{rounded.xs}"               # source: 4px
    padding: 6px
    typography: "{typography.caption-md}"

  # — Input / search field —
  input:
    backgroundColor: "{colors.surface-2}"
    textColor: "{colors.on-surface}"
    borderColor: "{colors.outline}"
    borderWidth: 0.5px
    rounded: "{rounded.md}"
    height: 42px
    padding: 14px         # +26px left when a leading icon is present
    typography: "{typography.body-md}"    # 14px
  input-focus:
    backgroundColor: "{colors.surface}"
    borderColor: "{colors.primary-line}"
    shadow: focus-ring                    # 3px primary-glow ring

  # — Segmented control (view switcher) —
  segmented:
    backgroundColor: "{colors.surface-2}"
    borderColor: "{colors.outline}"
    borderWidth: 0.5px
    rounded: "{rounded.md}"
    padding: 3px
  segmented-item:
    textColor: "{colors.on-surface-3}"
    rounded: "{rounded.sm}"
    height: 32px
    width: 40px
    size: 15px
  segmented-item-active:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    shadow: flat

  # — Theme picker (spring pill) —
  theme-toggle:
    backgroundColor: "{colors.surface-2}"
    borderColor: "{colors.outline}"
    borderWidth: 0.5px
    rounded: "{rounded.full}"
    padding: 3px
  theme-toggle-item:
    textColor: "{colors.on-surface-3}"
    rounded: "{rounded.full}"
    height: 30px
    padding: 16px
    typography: "{typography.label-md}"
  theme-toggle-item-active:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.on-surface}"
    shadow: flat

  # — Toggle switch —
  toggle:
    backgroundColor: "{colors.surface-3}"
    rounded: "{rounded.full}"
    height: 26px
    width: 44px           # knob 22px, spring travel 18px (see Motion)
  toggle-on:
    backgroundColor: "{colors.primary}"

  # — Dropdown / menu (glass) —
  menu:
    backgroundColor: "{colors.glass-surface}"
    borderColor: "{colors.glass-outline}"
    borderWidth: 0.5px
    rounded: "{rounded.md}"
    padding: 6px
    width: 200px          # min-width
    shadow: glass
  menu-item:
    textColor: "{colors.on-surface}"
    rounded: "{rounded.sm}"
    padding: 12px         # source: 9px 12px
    typography: "{typography.label-lg}"   # 13.5px
  menu-item-active:                       # hover/selected
    backgroundColor: "{colors.surface-2}"
  menu-item-danger:
    textColor: "{colors.error}"

  # — Toast (glass) —
  toast:
    backgroundColor: "{colors.glass-surface}"
    borderColor: "{colors.glass-outline}"
    borderWidth: 0.5px
    textColor: "{colors.on-surface}"
    rounded: "{rounded.full}"
    padding: 14px         # source: 10px 16px 10px 14px
    typography: "{typography.label-md}"   # 13.5px; leading icon in {colors.primary}
    shadow: glass

  # — Multi-select action bar (glass) —
  action-bar:
    backgroundColor: "{colors.glass-surface}"
    borderColor: "{colors.glass-outline}"
    borderWidth: 0.5px
    rounded: "{rounded.full}"
    padding: 6px
    gap: 4px
    shadow: glass

  # — FAB (floating action button) —
  fab:
    backgroundColor: "{colors.primary}"
    textColor: "{colors.on-primary}"
    borderColor: "{colors.primary-line}"
    borderWidth: 0.5px
    rounded: "{rounded.full}"             # circular
    height: 60px          # 52px on tablet rail
    width: 60px
    size: 24px            # glyph
    shadow: raised-primary
  fab-hover:
    shadow: raised-primary-strong         # + translateY(-2px), glyph rotates 90deg
  fab-active: {}                          # scale(0.92)

  # — Settings row —
  settings-row:
    borderColor: "{colors.outline}"       # 0.5px bottom divider
    borderWidth: 0.5px
    padding: 14px         # vertical; source 14px 4px
    gap: 16px
    typography: "{typography.label-lg}"   # title 14.5px; sub in caption/on-surface-3

  # — Cards (shared base for row / tile / card shapes; see prose) —
  card:
    backgroundColor: "{colors.surface}"
    borderColor: "{colors.outline}"
    borderWidth: 0.5px
    rounded: "{rounded.lg}"
    shadow: flat
  card-hover:
    borderColor: "{colors.outline-strong}"
    shadow: raised
  card-selected:
    backgroundColor: "{colors.primary-soft}"
    borderColor: "{colors.primary-line}"
---

# Studio.

A studio of patterns, primitives, and editorial moments — built on the iOS 26
floating-glass system and tuned for the lime.

## Overview

Studio is a single-product design system: a personal **library / collection app**
in the spirit of iOS 26's "Liquid Glass." Floating glass panels hover over an
editorial canvas; a cool-neutral palette is punctuated by one electric **lime**
accent; an editorial serif sets the tone while a tight grotesk carries the
interface and a mono handles captions and data.

The whole system is opinionated and small on purpose — one accent hue, four
typefaces, one material (glass), four core corner-radius steps. **Restraint is
the brand.**

**Personality.** Editorial, confident, quiet. The UI should read like a design
journal, not a SaaS dashboard — spacious, precise, materially honest. It is
device-aware and physical: surfaces float, motion springs, depth comes from
glass and shadow rather than color washes.

**Voice & content.** Copy is impersonal and object-focused ("The floating tab
bar is a container, not a tab strip"); second person appears only to describe a
gesture or benefit; never first-person "we." Sentence case for everything
human-readable — titles, body, buttons (`Compose`, `Inspect`, `Sign out`).
UPPERCASE is reserved for mono — kickers, group labels, metadata, tags. Numbers
are real and exact ("3 detents", "0.4s spring"); never vague. **No emoji,
anywhere.** Two signature copy moves recur: a trailing period used as
punctuation-as-logo on the wordmark and hero titles (`Studio.`, `Library.`,
`collection.`), and the **two-tone headline** — the key word in a display title
set in serif italic and dropped to a muted gray ("A working *collection.*").

## Colors

The palette is a single cool neutral ramp (a faint blue-violet cast, **hue 270**
in OKLCH, so whites read crisp rather than warm) punctuated by **one** saturated
accent. Status colors appear only for their semantic purpose. Color names below
follow semantic roles; the descriptive name is in parentheses.

- **Primary — Lime (`oklch(78% 0.22 138)`):** the single brand hue and the sole
  driver for interaction — the compose button, active states, the kicker dot,
  focus rings, selection. Never introduce a second accent. `on-primary` is a
  near-black lime-tinted ink for text/icons sitting on lime; `primary-soft` is
  the 16%-alpha selection fill; `primary-line` is the accent border / hover ink;
  `primary-glow` is the colored shadow on lime buttons.
- **Surfaces (`surface` → `surface-3`, plus `background`/`background-edge`):** the
  canvas is a near-white `background`; the edge behind floating panels steps one
  level deeper to `background-edge`; content sits on pure-white `surface` cards.
  `surface-2` and `surface-3` are the progressive hover-fill steps (a surface
  fills one step on hover: `transparent → surface-2 → surface-3`).
- **On-surface inks (`on-surface` → `on-surface-4`):** a four-level text ramp
  from a deep ink for headlines and core text (`on-surface`) down to faint
  (`on-surface-4`). Metadata and quieter UI use `on-surface-3`.
- **Outline (`outline`, `outline-strong`):** hairline borders define the system;
  `outline` is the resting `0.5px` border, stepping to `outline-strong` on hover.
- **Status (`error`, `success`):** semantic only — destructive actions and
  confirmations. Never decorative.
- **Material (`glass-surface`, `glass-outline`, `scrim`):** the translucent glass
  fill and border (see Elevation & Depth) and the modal scrim.

### Dark mode

Dark is **first-class, not an afterthought** — the same hue family pushed to a
cool carbon, with lime brightened. Toggled via `data-theme="dark"` on a root
element (the browser `theme-color` meta updates with it). The token values in
the frontmatter are the light theme; the dark equivalents, by the same role
name, are:

| Role | Light | Dark |
|---|---|---|
| `primary` | `oklch(78% 0.22 138)` | `oklch(86% 0.23 138)` |
| `on-primary` | `oklch(18% 0.06 145)` | `oklch(14% 0.06 145)` |
| `primary-soft` | `oklch(78% 0.22 138 / 0.16)` | `oklch(86% 0.23 138 / 0.18)` |
| `primary-line` | `oklch(64% 0.2 142)` | `oklch(72% 0.21 142)` |
| `primary-glow` | `oklch(78% 0.22 138 / 0.5)` | `oklch(86% 0.23 138 / 0.5)` |
| `background` | `oklch(98% 0.003 270)` | `oklch(12% 0.008 270)` |
| `background-edge` | `oklch(95% 0.004 270)` | `oklch(8% 0.006 270)` |
| `surface` | `oklch(100% 0 0)` | `oklch(16% 0.008 270)` |
| `surface-2` | `oklch(96.2% 0.004 270)` | `oklch(20% 0.009 270)` |
| `surface-3` | `oklch(93% 0.005 270)` | `oklch(24% 0.01 270)` |
| `on-surface` | `oklch(14% 0.012 270)` | `oklch(97% 0.004 270)` |
| `on-surface-2` | `oklch(40% 0.009 270)` | `oklch(72% 0.006 270)` |
| `on-surface-3` | `oklch(56% 0.007 270)` | `oklch(54% 0.007 270)` |
| `on-surface-4` | `oklch(72% 0.006 270)` | `oklch(40% 0.008 270)` |
| `outline` | `oklch(88% 0.006 270)` | `oklch(27% 0.01 270)` |
| `outline-strong` | `oklch(78% 0.008 270)` | `oklch(36% 0.011 270)` |
| `error` | `oklch(58% 0.23 22)` | `oklch(68% 0.22 22)` |
| `success` | `oklch(64% 0.16 150)` | `oklch(74% 0.18 150)` |
| `scrim` | `oklch(14% 0.01 270 / 0.34)` | `oklch(4% 0.005 270 / 0.6)` |
| `glass-surface` | `oklch(100% 0 0 / 0.72)` | `oklch(16% 0.008 270 / 0.72)` |
| `glass-outline` | `oklch(100% 0 0 / 0.65)` | `oklch(100% 0 0 / 0.08)` |

> Note on naming: Studio is deliberately a one-accent system with a single
> neutral ramp, so there is no `secondary`/`tertiary` palette — `primary` (lime)
> plus the semantic `surface` / `on-surface` / `outline` neutral roles cover the
> system. All values are preserved from `colors_and_type.css` (OKLCH, hue 270).

## Typography

Four families, strict roles. Display sizes use negative tracking and near-1.0
line-height for a packed, editorial column.

- **Display — Bounded** (`headline-display` … `headline-sm`): a wide, geometric,
  self-hosted variable grotesque at weight ~500; the brand headline face for
  heroes, page titles, card titles, and the wordmark / avatar glyphs.
- **Two-tone accent — Instrument Serif:** the system's most recognizable
  type+copy move. The key word inside a `headline-*` title is set in delicate
  serif italic (weight 400, `letter-spacing: -0.01em`) and dropped to
  `on-surface-3`, so a heavy geometric sans cradles a light editorial serif
  ("Floating *glass* navigation"). This is a treatment applied within a headline,
  not a standalone level.
- **Body — Inter Tight** (`body-lg`, `body-md`): carries long-form text and
  sub-decks, tracked slightly tight. Feature settings `ss01 cv11 tnum` are on by
  default across the interface.
- **Labels — Inter Tight** (`label-lg`, `label-md`): default interface text on
  buttons, rows, and menus, weight 500.
- **Captions — JetBrains Mono** (`caption-lg`, `caption-md`, `caption-sm`, and
  inline `mono-inline`): kickers, group labels, metadata, counts, emails. Always
  **UPPERCASE** with wide tracking (0.08–0.16em). `mono-inline` is the one mono
  exception that is not uppercased — inline data with tabular numerals.

> The responsive display sizes are clamped in source — `headline-display` is
> `clamp(40px, 6vw, 72px)` and `headline-lg` is `clamp(34px, 4.5vw, 56px)`. The
> tokens record the maximum (desktop) size, since the spec's `Dimension` type
> does not express `clamp()`. `text-transform: uppercase` on the caption tiers is
> likewise documented here rather than carried as a token property.

## Layout

A **4px base unit** governs all rhythm. The shell is an adaptive grid that is
device-aware and `dvh`-anchored, respecting `env(safe-area-inset-*)` everywhere.

- **Responsive shell:** full **256px** sidebar (`spacing.sidebar`) on desktop →
  **76px** rail (`spacing.sidebar-rail`) on tablet → a bottom tab pill + FAB on
  mobile. Header height is **72px** (`spacing.header`).
- **Floating chrome** (sidebar, the two topbar pills, FAB, bottom tabs, toasts,
  action bar) is inset **14px** (`spacing.float-inset`) from viewport edges and
  never spans edge-to-edge — glass floats with margins on *all* sides.
- **Content columns** are padded 32px (`spacing.8`) on desktop, 20px
  (`spacing.5`) on mobile. Related items are grouped into cards with generous
  internal padding.
- **Spacing scale:** `1`–`16` map to 4–64px (the key is the ×4 multiplier).
  Safe-area insets are resolved at runtime via `env()` and so are not tokens.

## Elevation & Depth

Depth comes from **glass + shadow**, never from color washes or gradients on
backgrounds. There are three resting tiers plus a few component-specific shadows;
component tokens reference these by name.

- **`flat`** — resting surfaces and cards: a hairline `0.5px` `outline` border +
  `0 1px 2px oklch(0% 0 0 / 0.04)`. Borders define; shadows lift.
- **`raised`** — primary buttons and hovered cards: `0 6px 16px oklch(0% 0 0 /
  0.1)` plus a tight contact shadow (`0 2px 4px oklch(0% 0 0 / 0.05)`).
- **`glass`** — the floating material (sidebar, topbar pills, dropdowns, toasts,
  action bar): a layered `box-shadow` of an inset top highlight, a hairline ring,
  a soft drop, and a tight contact shadow:
  `0 1px 0 0 oklch(100% 0 0 / 0.95) inset, 0 0 0 0.5px oklch(0% 0 0 / 0.06), 0 12px 32px oklch(20% 0.01 270 / 0.14), 0 2px 8px oklch(0% 0 0 / 0.05)`.
  In dark mode the ring and drop deepen substantially and the inset highlight
  drops to `/ 0.08`.

**The glass material** (the heart of the system) is `glass-surface` fill +
`backdrop-filter: blur(28px) saturate(180%)` + a `0.5px` `glass-outline` border +
the `glass` shadow. Blur is used **only** for glass floating over scrollable
content — never decoratively on static surfaces. Item overlay controls on photos
use a smaller 8px blur to stay legible; the modal scrim adds a light 2px blur.

Component-specific shadows referenced by the tokens:
- **`raised-primary`** — lime buttons / FAB: an inset white highlight, a raised
  drop, and the colored `primary-glow` (`0 1px 0 0 oklch(100% 0 0 / 0.35) inset,
  0 6px 16px oklch(0% 0 0 / 0.1), 0 2px 4px var(--primary-glow)`).
  **`raised-primary-strong`** is the hovered variant (deeper drop + lift).
- **`focus-ring`** — focused inputs: a 3px `primary-glow` ring plus a solid
  `surface` fill and a `primary-line` border. General focus is a 2px
  `primary-line` outline at 2px offset.

## Motion

Three easings, each with a job, at quick durations (0.18–0.42s).

- **`ease` — `cubic-bezier(0.4, 0, 0.2, 1)`:** general transitions, hovers,
  background changes.
- **`ease-out` — `cubic-bezier(0.16, 1, 0.3, 1)`:** decelerating reveals and page
  pushes (≈0.42s).
- **`ease-spring` — `cubic-bezier(0.34, 1.56, 0.64, 1)`:** anything that should
  feel physical — the view / theme pills sliding, the toggle knob, toasts, and
  press feedback.

**Page hierarchy** uses a horizontal **push**: a detail page slides in from the
right with a deepening left shadow; the topbar brand mark becomes a back chevron.
Tabs **cross-fade** with a 4px rise. **Press feedback is universal shrink** —
elements scale down on `:active` (icon buttons `0.90`, buttons `0.96–0.97`, cards
`0.992`); springy and quick. Hover gently zooms photography (`scale(1.03–1.04)`).
Honor `prefers-reduced-motion`.

## Shapes

The shape language pairs **hairline borders** with a tight radius ladder. Bigger
elements get bigger radii.

- **Radii** (`rounded`): `xs 6 · sm 10 · md 14 · lg 20 · xl 28 · full 999`. Cards
  use `lg`; heroes and the account card use `xl`; all chips and buttons-as-pills
  use `full`; inputs, menus, and segmented containers use `md`; segmented items
  use `sm`. (Source uses a 4px hardcode for accent tags and the focus ring,
  slightly tighter than `xs`.)
- **Borders:** `0.5px solid outline` is the system default, stepping to
  `outline-strong` on hover. Borders define structure; shadows provide lift.

## Iconography

- **System:** [Phosphor Icons](https://phosphoricons.com/) in three weights —
  **regular** (default UI), **fill** (active tab bar + status glyphs), and
  **bold** (small affordances: the `+` on compose, carets, the more-menu dots,
  arrows). Sizes run 12–22px; icon color follows text (`on-surface` /
  `on-surface-3`), going `primary` only when active.
- **No custom SVG set, sprite, or PNG icons** — rely entirely on the Phosphor
  web font rather than hand-rolling glyphs.
- **No emoji or unicode as iconography.** The only non-Phosphor "glyphs" are the
  **lime dot** (a 5px CSS circle in kickers) and the **brand / avatar "S"** (a
  Bounded letter, not an icon).

## Components

The frontmatter `components` map carries the tokens; this section adds structure
and behavior. A few token properties extend the base set (`borderColor`,
`borderWidth`, `shadow`, `gap`, `size`); `shadow` values name a tier from
Elevation & Depth. Empty variant maps (e.g. `button-primary-active`) signal a
transform-only state described here.

- **Buttons.** `button-primary` is the lime compose button (42px tall, `md`
  radius, inset highlight + `primary-glow`); `button-cta` is its pill form;
  `button-neutral` is a solid-ink alternative. `button-icon` is a 40px circle
  that fills one surface step on hover. `button-ghost` is a low-emphasis pill
  (with a `danger` variant in `error`). Hover lifts primary buttons
  `translateY(-1px)` with a stronger shadow; press shrinks every button.
- **Chips.** Filter chips rest as a transparent hairline pill; the active chip
  **inverts to solid ink** (`on-surface` fill, `background` text). Counts ride
  alongside in `mono-inline`.
- **Badges, tags, pills.** `badge` is a mono count chip (with an `accent`
  variant on `primary-soft`); `tag` is the accent corner label (lime fill, mono
  uppercase); `type-pill` is a neutral mono pill for type labels.
- **Input / search.** A `surface-2` field with a hairline border; on focus it
  fills to solid `surface`, takes a `primary-line` border, and gains the 3px
  `focus-ring`. Placeholder is `on-surface-3`; a leading icon insets the text.
- **Segmented control & theme picker.** A `surface-2` track with a `0.5px`
  border and 3px padding; the active item lifts onto a `surface` chip with the
  `flat` shadow. The theme picker is the pill-shaped variant whose indicator
  slides on `ease-spring`.
- **Toggle.** A 44×26 pill; off is `surface-3`, on is `primary`; the 22px knob
  travels 18px on `ease-spring`.
- **Dropdown / menu.** Glass material, `md` radius, 6px padding; rows fill to
  `surface-2` on hover, destructive rows render in `error`, separators are a
  `0.5px` `outline` hairline. Opens with a small spring scale from the top-right.
- **Toast & action bar.** Both are pill-shaped glass that float up from the
  bottom (safe-area aware) on `ease-spring`; the toast carries a leading
  `primary` status icon. Entering multi-select reveals the action bar and tucks
  the FAB away.
- **FAB.** A 60px (52px on tablet) lime circle with the `raised-primary` shadow;
  hover lifts it and rotates the glyph 90°, press shrinks to `0.92`. Hidden on
  full desktop (where compose lives in the sidebar).
- **Settings row.** A two-column grid (label + trailing control) with a `0.5px`
  bottom divider, a `label`-weight title, and a `caption` / `on-surface-3` sub.
- **Cards.** One base (`surface` fill, `0.5px` `outline`, `lg` radius, `flat`
  shadow, clipped overflow) shared by three item shapes: **row** (64px thumb +
  title + mono meta), **tile** (square photo + two-line title), and **card**
  (16:10 photo with a bottom-up dark protection gradient + mono kicker + serif
  title + mono meta). Hover lifts to `raised` and strengthens the border;
  selected swaps to a `primary-line` border and `primary-soft` fill. Photography
  is full-bleed, muted/cool, inside `lg`/`xl` radii, and gently zooms on hover.

## Do's and Don'ts

- **Do** use lime (`primary`) surgically — one clear interaction target per
  context: compose, active state, selection, focus, the kicker dot.
- **Don't** introduce a second accent, or use lime as decoration. One hue only.
- **Do** float glass with margins on all sides and reserve `blur(28px)` for glass
  over scrollable content.
- **Don't** let any floating surface span edge-to-edge, and don't blur static
  surfaces decoratively.
- **Do** keep sentence case for everything human-readable; reserve UPPERCASE for
  mono captions, kickers, and metadata.
- **Don't** uppercase the serif, and never set the serif anywhere except the
  two-tone italic accent word.
- **Do** use hairline `0.5px` `outline` borders to define structure and reserve
  shadow for lift; step to `outline-strong` on hover.
- **Don't** convey depth with background gradients, textures, or noise — depth is
  glass + shadow. The only gradients are image protection scrims and the single
  soft accent glow behind the account card.
- **Do** make press feedback shrink and reveals decelerate; keep durations quick
  (0.18–0.42s) and honor `prefers-reduced-motion`.
- **Do** treat dark mode as first-class — design and verify both themes.
- **Don't** use emoji or hand-rolled SVG icons anywhere; iconography is Phosphor,
  emphasis is type and the lime dot.
- **Do** keep numbers real and exact, and end the wordmark and hero titles with a
  period — but not every label.
