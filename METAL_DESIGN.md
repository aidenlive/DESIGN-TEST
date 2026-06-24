---
version: alpha
name: Metal
description: >-
  An achromatic, machined neutral system for developer & infrastructure tooling.
  A pure gray ramp (zero chroma) carries the entire UI; a single high-chroma
  terminal green is the sole accent. Monospace overlines and a carbon terminal
  block evoke CLI precision. Derived from the GCP Provision planner.
colors:
  # --- Accent (the only chromatic family) ---
  primary: "oklch(0.72 0.19 155)"
  primary-dim: "oklch(0.52 0.14 155)"
  primary-soft: "oklch(0.72 0.19 155 / 0.10)"
  primary-glow: "oklch(0.72 0.19 155 / 0.25)"

  # --- Neutral ramp (achromatic, chroma 0) ---
  white: "oklch(0.99 0 0)"
  gray-50: "oklch(0.97 0 0)"
  gray-100: "oklch(0.94 0 0)"
  gray-200: "oklch(0.88 0 0)"
  gray-300: "oklch(0.80 0 0)"
  gray-400: "oklch(0.65 0 0)"
  gray-500: "oklch(0.55 0 0)"
  gray-600: "oklch(0.44 0 0)"
  gray-700: "oklch(0.35 0 0)"
  gray-800: "oklch(0.25 0 0)"
  gray-900: "oklch(0.18 0 0)"
  gray-950: "oklch(0.13 0 0)"
  black: "oklch(0.10 0 0)"

  # --- Status ---
  status-success: "oklch(0.72 0.19 155)"
  status-error: "oklch(0.63 0.20 25)"
  status-warning: "oklch(0.80 0.16 85)"
  status-info: "oklch(0.65 0.15 250)"

  # --- Semantic aliases ---
  surface-page: "{colors.white}"
  surface-card: "{colors.gray-50}"
  surface-terminal: "{colors.gray-950}"
  text-primary: "{colors.gray-900}"
  text-secondary: "{colors.gray-500}"
  text-tertiary: "{colors.gray-400}"
  border-subtle: "oklch(0.88 0 0 / 0.7)"
  border-default: "{colors.gray-200}"

typography:
  # Sizes are rem against a 16px root. px equivalents noted in prose.
  headline-display:        # project title @ desktop (2.25rem / 36px)
    fontFamily: DM Sans
    fontSize: 2.25rem
    fontWeight: 700
    lineHeight: 1.1
    letterSpacing: -0.03em
  headline-lg:             # project title @ mobile, large headings (1.75rem / 28px)
    fontFamily: DM Sans
    fontSize: 1.75rem
    fontWeight: 700
    lineHeight: 1.1
    letterSpacing: -0.03em
  headline-md:             # 1.375rem / 22px
    fontFamily: DM Sans
    fontSize: 1.375rem
    fontWeight: 700
    lineHeight: 1.25
    letterSpacing: -0.03em
  headline-sm:             # modal title (1.125rem / 18px)
    fontFamily: DM Sans
    fontSize: 1.125rem
    fontWeight: 700
    lineHeight: 1.25
    letterSpacing: -0.03em
  body-md:                 # default body (0.9375rem / 15px)
    fontFamily: DM Sans
    fontSize: 0.9375rem
    fontWeight: 400
    lineHeight: 1.55
    letterSpacing: -0.01em
  body-sm:                 # descriptions, secondary copy (0.8125rem / 13px)
    fontFamily: DM Sans
    fontSize: 0.8125rem
    fontWeight: 400
    lineHeight: 1.55
    letterSpacing: -0.01em
  label-strong:            # button text, card titles (0.8125rem / 13px)
    fontFamily: DM Sans
    fontSize: 0.8125rem
    fontWeight: 600
    lineHeight: 1.25
    letterSpacing: -0.01em
  label-md:                # form labels (0.6875rem / 11px)
    fontFamily: DM Sans
    fontSize: 0.6875rem
    fontWeight: 600
    lineHeight: 1.25
  overline:                # uppercase mono section labels (0.6875rem / 11px)
    fontFamily: DM Mono
    fontSize: 0.6875rem
    fontWeight: 500
    lineHeight: 1
    letterSpacing: 0.08em
  badge:                   # status chips, region badges (0.625rem / 10px)
    fontFamily: DM Mono
    fontSize: 0.625rem
    fontWeight: 500
    lineHeight: 1
    letterSpacing: 0.02em
  mono-code:               # terminal output lines (0.6875rem / 11px)
    fontFamily: DM Mono
    fontSize: 0.6875rem
    fontWeight: 400
    lineHeight: 1.8
  mono-meta:               # project path, item metadata (0.6875rem / 11px)
    fontFamily: DM Mono
    fontSize: 0.6875rem
    fontWeight: 400
    lineHeight: 1.55

spacing:
  base: 16px
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
  "20": 80px
  container-max: 1120px
  nav-height: 56px
  nav-inset: 12px

rounded:
  sm: 6px
  md: 10px
  lg: 16px
  xl: 24px
  full: 9999px

components:
  # --- Buttons ---
  button-primary:
    backgroundColor: "{colors.gray-900}"
    textColor: "{colors.white}"
    typography: "{typography.label-strong}"
    rounded: "{rounded.md}"
    padding: "12px 20px"
    height: 40px
  button-primary-hover:
    backgroundColor: "{colors.black}"
  button-secondary:
    backgroundColor: transparent
    textColor: "{colors.text-primary}"
    borderColor: "{colors.gray-200}"
    borderWidth: 1.5px
    typography: "{typography.label-strong}"
    rounded: "{rounded.md}"
    padding: "12px 20px"
    height: 40px
  button-secondary-hover:
    borderColor: "{colors.gray-400}"
  button-ghost:
    backgroundColor: transparent
    textColor: "{colors.text-secondary}"
    typography: "{typography.label-strong}"
    rounded: "{rounded.md}"
    padding: "12px 20px"
    height: 40px
  button-ghost-hover:
    backgroundColor: "{colors.gray-100}"
    textColor: "{colors.text-primary}"
  button-accent:
    backgroundColor: "{colors.primary}"
    textColor: "oklch(0.15 0.05 155)"
    typography: "{typography.label-strong}"
    rounded: "{rounded.md}"
    padding: "12px 20px"
    height: 40px
  button-accent-hover:
    backgroundColor: "oklch(0.68 0.19 155)"
  button-danger:
    backgroundColor: "oklch(0.63 0.20 25 / 0.08)"
    textColor: "oklch(0.53 0.18 25)"
    typography: "{typography.label-strong}"
    rounded: "{rounded.md}"
    padding: "12px 20px"
    height: 40px
  button-danger-hover:
    backgroundColor: "oklch(0.63 0.20 25 / 0.15)"
  button-sm:               # size modifier, applies to any variant
    typography: "{typography.badge}"
    rounded: "{rounded.sm}"
    padding: "8px 12px"
    height: 32px

  # --- Inputs ---
  input:
    backgroundColor: "{colors.white}"
    textColor: "{colors.text-primary}"
    typography: "{typography.mono-meta}"
    borderColor: "{colors.gray-200}"
    borderWidth: 1.5px
    rounded: "{rounded.md}"
    padding: "0 16px"
    height: 40px
  input-focus:
    borderColor: "{colors.gray-900}"
  select:
    backgroundColor: "{colors.white}"
    textColor: "{colors.text-primary}"
    typography: "{typography.body-sm}"
    borderColor: "{colors.gray-200}"
    borderWidth: 1.5px
    rounded: "{rounded.md}"
    padding: "0 36px 0 16px"
    height: 40px
  select-focus:
    borderColor: "{colors.gray-900}"

  # --- Resource catalog card ---
  resource-card:
    backgroundColor: "{colors.white}"
    borderColor: "{colors.border-subtle}"
    borderWidth: 1px
    rounded: "{rounded.lg}"
    padding: 20px
    width: 180px
  resource-card-hover:
    borderColor: "{colors.gray-300}"
    shadow: "0 4px 24px oklch(0 0 0 / 0.06)"
  resource-icon:
    backgroundColor: "{colors.gray-100}"
    textColor: "{colors.gray-600}"
    rounded: "{rounded.md}"
    size: 36px

  # --- Provisioning queue ---
  queue-item:
    backgroundColor: "{colors.white}"
    borderColor: "{colors.border-subtle}"
    borderWidth: 1px
    rounded: "{rounded.md}"
    padding: 16px
  queue-item-hover:
    borderColor: "{colors.gray-300}"
  queue-status:
    backgroundColor: "{colors.primary-soft}"
    textColor: "{colors.primary-dim}"
    typography: "{typography.badge}"
    rounded: "{rounded.full}"
    padding: "3px 10px"

  # --- Chrome ---
  nav:
    backgroundColor: "oklch(0.99 0 0 / 0.82)"
    borderColor: "{colors.border-subtle}"
    borderWidth: 1px
    rounded: "{rounded.lg}"
    height: 56px
    padding: "0 16px"
  nav-count:
    backgroundColor: "{colors.gray-900}"
    textColor: "{colors.white}"
    rounded: "{rounded.full}"
    height: 20px
  nav-count-empty:
    backgroundColor: "{colors.gray-200}"
    textColor: "{colors.gray-500}"
  tab:
    backgroundColor: transparent
    textColor: "{colors.text-tertiary}"
    typography: "{typography.body-sm}"
    padding: "12px 16px"
  tab-active:
    textColor: "{colors.text-primary}"
    borderColor: "{colors.gray-900}"
    borderWidth: 2px
  region-badge:
    backgroundColor: "{colors.gray-100}"
    textColor: "{colors.gray-600}"
    typography: "{typography.badge}"
    rounded: "{rounded.full}"
    padding: "3px 10px"

  # --- Overlays ---
  modal-overlay:
    backgroundColor: "oklch(0.10 0 0 / 0.4)"
  modal-panel:
    backgroundColor: "{colors.white}"
    rounded: "{rounded.xl}"
    padding: 24px
  toast:
    backgroundColor: "{colors.gray-900}"
    textColor: "{colors.white}"
    typography: "{typography.body-sm}"
    rounded: "{rounded.full}"
    padding: "12px 20px"

  # --- Terminal block ---
  terminal:
    backgroundColor: "{colors.gray-950}"
    rounded: "{rounded.lg}"
    padding: 20px
  terminal-line:
    textColor: "{colors.gray-400}"
    typography: "{typography.mono-code}"
  terminal-line-comment:
    textColor: "{colors.gray-600}"
  terminal-line-command:
    textColor: "oklch(0.85 0 0)"
  terminal-line-flag:
    textColor: "oklch(0.65 0.12 155)"
---

# Metal

A design system for developer and infrastructure tooling. Precise, achromatic,
and quiet — built so the interface reads like well-machined hardware and gets
out of the way of the work.

## Overview

**Metal** is the visual identity of an engineering control surface — the kind of
tool where a person assembles infrastructure and reads machine output. Its
personality is *calm precision*: confident, neutral, and unembellished, the
opposite of decorative. Nothing competes for attention except the one thing that
matters at any moment.

The defining move is restraint with color. The entire UI is built from a single
**purely achromatic gray ramp** — twelve neutral steps with zero chroma, so the
product never picks a "warm" or "cool" temperature. Against that machined gray,
exactly one chromatic voice is allowed: **Signal Green**, a high-chroma terminal
green reserved for live state and the primary action. The effect is a screen
that feels engineered rather than styled — and where green always means
"something is active."

A second register runs underneath: **monospace**. Section labels, paths, status
chips, and command output are all set in DM Mono, lending the interface the
cadence of a CLI. The product is light and spacious by default, but its center
of gravity is a dark **carbon terminal block** where generated commands live —
the one place the system goes dark, because that's where the real output is.

Target audience: developers, SREs, and platform engineers. The desired feeling
is *trust through precision* — spacious, legible, and never loud.

## Colors

The palette is a strict separation of duties: a neutral ramp does all the
structural work, and a single accent owns all interactivity and live state.

- **Signal Green (`primary`, `oklch(0.72 0.19 155)`):** The sole accent. Used
  only for active status, "live" indicators, and the accent action. **Signal
  Green Dim** (`primary-dim`) is its text-safe variant on light surfaces;
  **Signal Green Soft** (`primary-soft`, 10% alpha) tints status-chip
  backgrounds.
- **Gunmetal ramp (`gray-50`–`gray-950`):** A pure achromatic scale (chroma 0)
  that carries every surface, border, and text level. `gray-900` is the
  workhorse ink for primary text and the dark default button; `gray-500` and
  `gray-400` handle secondary and tertiary text; `gray-100`/`gray-200` handle
  fills and borders.
- **Carbon (`gray-950`, `oklch(0.13 0 0)`):** The terminal surface — the only
  large dark field in the product.
- **Surfaces:** Pages and cards sit on **White** (`surface-page`) and the faint
  **gray-50** (`surface-card`); borders use a translucent **border-subtle**
  (`oklch(0.88 0 0 / 0.7)`) for a hairline that reads as etched rather than
  drawn.
- **Status:** `success` is Signal Green itself (state and accent share a hue by
  design); `error` is a muted red, `warning` an amber, `info` a desaturated
  blue. Status colors appear as small chips and dots, never as fills.

All values are authored in `oklch` for perceptual evenness across the ramp; they
convert to sRGB for contrast checking.

## Typography

Two families, two jobs. **DM Sans** is the human voice — headings, body, button
labels. **DM Mono** is the machine voice — overlines, metadata, status chips,
and terminal output. The split is semantic, not decorative: if it's data the
system produced or a system-level label, it's mono.

- **Headlines** (DM Sans, weight 700) run from a 36px display down to 18px, all
  set tight (`-0.03em` tracking, 1.1–1.25 line height) for a dense, engineered
  feel.
- **Body** (DM Sans, weight 400) sits at 15px (`body-md`) and 13px (`body-sm`)
  with relaxed 1.55 line height for comfortable reading of descriptions.
- **Labels** (DM Sans, weight 600) at 13px/11px carry button text and card
  titles.
- **Overlines** (DM Mono, weight 500, 11px) are the signature: **uppercase**
  with wide `0.08em` tracking, they title every section like a terminal prompt.
- **Badges & metadata** (DM Mono, 10–11px) handle status chips and paths;
  badges are **uppercase** with light `0.02em` tracking.
- **Terminal lines** (DM Mono, 11px, 1.8 line height) give command output room
  to breathe and stay scannable.

Sizes are expressed in `rem` against a 16px root. Casing (uppercase on overlines
and badges) is applied via `text-transform` in implementation — it is described
here in prose since it is not a typographic token field.

## Layout

A single centered column, **max-width 1120px**, with generous side padding
(16px on mobile, 32px on desktop). There is no multi-column grid; content
stacks vertically and breathes.

Spacing follows a **4px base scale** (4 · 8 · 12 · 16 · 20 · 24 · 32 · 40 · 48 ·
64 · 80) used consistently for gaps, padding, and rhythm. Cards use 20px
internal padding; sections are separated by 40px; major view blocks by 64px.

The navigation is a **floating frosted bar** — fixed 12px from each edge, 56px
tall — rather than a full-width header, reinforcing the sense of a tool layered
over a workspace. Horizontal catalog rows scroll on mobile and wrap to a
4–5-up flex layout on wider screens.

## Elevation & Depth

Depth is conveyed primarily through **borders and tonal contrast**, not heavy
shadows — consistent with the machined, flat aesthetic. Most surfaces are
distinguished by a single hairline (`border-subtle`) and a small tonal step
between `white` and `gray-50`.

Three deliberate exceptions add dimension:

- **Frosted glass** on the floating nav: `backdrop-filter: blur(20px)
  saturate(1.4)` over an 82%-opaque white, so the workspace shows through.
- **A single lift shadow** on card hover only: `0 4px 24px oklch(0 0 0 / 0.06)`
  paired with a 2px upward translate — the one place the UI rises off the page.
- **The modal scrim**: `oklch(0.10 0 0 / 0.4)` with a soft `blur(4px)` to push
  the page back behind dialogs.

Shadows are otherwise absent. If you reach for one outside these cases,
reconsider — use a border or a tonal step instead.

## Shapes

Soft, consistent rounding throughout — this is *not* a sharp-cornered system.
Radii scale with element size: **6px** for small controls (compact buttons,
icons), **10px** for standard buttons, inputs, and list items, **16px** for
cards, the nav, and the terminal block, and **24px** for modals (which become
bottom sheets on mobile, rounding only their top corners). Pills and status
chips use the **full** radius. Mixing sharp and round corners in one view is off
the table — the language is uniformly soft.

## Components

- **Buttons** come in five variants at a fixed 40px height (32px for the `sm`
  size): **primary** (dark `gray-900` fill — the default), **secondary**
  (transparent with a 1.5px border), **ghost** (text-only, fills `gray-100` on
  hover), **accent** (Signal Green fill — reserved for the single most live
  action), and **danger** (translucent red). All use 10px radius (6px when
  small).
- **Inputs & selects** are 40px tall with a 1.5px `gray-200` border that
  darkens to `gray-900` on focus. Text inputs use **mono** (they hold paths and
  identifiers); selects use sans and carry a chevron.
- **Resource cards** are white, hairline-bordered, 16px-radius tiles with an
  icon chip, name, description, and a mono tag. They lift on hover (border
  darkens, soft shadow, −2px translate).
- **Queue items** are compact white rows with an icon, name, mono metadata, and
  a **status chip** (Signal Green soft fill, mono uppercase) signaling live
  state.
- **The terminal block** is the carbon (`gray-950`) centerpiece: a faux window
  header with red/yellow/green dots, then mono command lines color-coded by role
  — comments dim (`gray-600`), commands bright (`oklch(0.85 0 0)`), flags green.
- **Chrome:** a frosted floating **nav** with a wordmark, a mono project path,
  and a pill **count badge** (dark when populated, gray when empty);
  **underline tabs** for switching views; **pill region badges**; a centered
  dark **toast** for confirmations.

Variants for interactive states (`-hover`, `-active`, `-focus`, `-empty`) are
defined alongside their base tokens.

## Do's and Don'ts

- **Do** reserve Signal Green for live state and the single accent action per
  screen; if everything is green, nothing is.
- **Don't** introduce a second accent hue — the system's identity is one color
  against neutral gray.
- **Do** keep the neutral ramp achromatic; resist warming or cooling the grays.
- **Do** use DM Mono for anything machine-authored or system-labeled (paths,
  status, commands, overlines) and DM Sans for human prose.
- **Don't** mix sharp and rounded corners in the same view — rounding is uniform
  and scales only with element size.
- **Do** convey hierarchy with borders and tonal steps before reaching for a
  shadow; shadows are limited to the three documented cases.
- **Do** set headings tight (`-0.03em`) and overlines uppercase with wide
  tracking — that contrast is the typographic signature.
- **Don't** lighten the carbon terminal block; its darkness is what frames the
  output as the product's payload.
- **Do** maintain WCAG AA contrast (4.5:1 for body text); verify Signal Green
  text uses the dimmed variant (`primary-dim`) on light surfaces.
