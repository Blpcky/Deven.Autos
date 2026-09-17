---
name: Ballbackpedia
description: A faithful Wikipedia "notable person" article parody, applied to one man's self-mythologized legend.
colors:
  paper: "#ffffff"
  page-bg: "#f6f6f6"
  ink: "#202122"
  ink-muted: "#54595d"
  border: "#a2a9b1"
  border-light: "#eaecf0"
  panel: "#f8f9fa"
  link: "#0645ad"
  link-visited: "#0b0080"
  link-red: "#ba0000"
  amber-bg: "#fef6e7"
  amber-border: "#f0c66b"
  focus: "#3366cc"
typography:
  display:
    fontFamily: "'Linux Libertine', 'Source Serif 4', Georgia, 'Times New Roman', serif"
    fontSize: "2.2rem"
    fontWeight: 400
    lineHeight: 1.25
    letterSpacing: "normal"
  section-heading:
    fontFamily: "'Linux Libertine', 'Source Serif 4', Georgia, 'Times New Roman', serif"
    fontSize: "1.5rem"
    fontWeight: 400
    lineHeight: 1.3
  subsection-heading:
    fontFamily: "'Linux Libertine', 'Source Serif 4', Georgia, 'Times New Roman', serif"
    fontSize: "1.15rem"
    fontWeight: 700
  body:
    fontFamily: "Helvetica, 'Helvetica Neue', Arial, sans-serif"
    fontSize: "15px"
    fontWeight: 400
    lineHeight: 1.65
  label:
    fontFamily: "Helvetica, 'Helvetica Neue', Arial, sans-serif"
    fontSize: "12px"
    fontWeight: 700
    letterSpacing: "0.03em"
spacing:
  xs: "6px"
  sm: "10px"
  md: "16px"
  lg: "22px"
  xl: "28px"
rounded:
  none: "0px"
  hairline: "2px"
components:
  tab-active:
    backgroundColor: "{colors.paper}"
    textColor: "{colors.ink}"
    padding: "10px 16px"
  citation-flag:
    textColor: "{colors.link-red}"
    typography: "{typography.label}"
  ambox:
    backgroundColor: "{colors.amber-bg}"
    padding: "14px 16px"
    rounded: "{rounded.hairline}"
---

# Design System: Ballbackpedia

## Overview

**Creative North Star: "The Encyclopedia That Doubts You"**

Ballbackpedia is a one-page, single-file reproduction of a real Wikipedia "notable person" article — utility bar, article/talk/read/edit/history tabs, sidebar navigation and tools, a maintenance banner, a right-floated infobox, an auto-generated table of contents, inline bracketed citations, a wikitable, and a categories footer — applied without irony to one man's self-told legend. The system has exactly one joke and refuses to visually wink at it: every component is built to the real interface's own conventions, so the comedy comes entirely from an encyclopedia's dry, citation-hungry, skeptical voice reporting grandiose claims as contested fact, never from the chrome looking like a "gag site."

The build deliberately avoids the two adjacent failure modes: a sincere prestige-marketing landing page (hero/CTA/stat-bar/testimonial-grid), which is what this system replaced, and a loud, self-aware "haha look it's fake Wikipedia" pastiche with cartoonish exaggeration. Neither was built. What ships is the real thing, populated with an unreal subject.

**Key Characteristics:**
- Real Wikipedia visual grammar (Vector-skin proportions), not a stylized homage
- Flat, white, hairline-bordered — depth communicated by borders and tone, never shadow
- One functional signature interaction (heading search-jump) plus small delight moments (random-section jump with a highlight flash, copy-permalink toast), never scattered hover effects
- Every citation, "[citation needed]" tag, and reference entry is itself part of the joke

## Colors

Flat and restrained — near-total desaturation (grayscale ink and borders) with exactly one hue, Wikipedia's own link blue, carrying all interactive affordance, plus a single amber used only for the maintenance banner.

### Primary
- **Wiki Link Blue** (`#0645ad`): every interactive link and control. Nothing else in the system uses a saturated color — this is the entire "primary" budget, and its rarity outside links is what keeps the parody feeling like a real interface rather than a designed one.

### Neutral
- **Ink** (`#202122`): body text, headings.
- **Ink Muted** (`#54595d`): secondary text — short description, infobox labels, reference list, footer disclaimer, sidebar labels.
- **Paper** (`#ffffff`): article content surface.
- **Page Ground** (`#f6f6f6`): the area outside the article column (visible only if the viewport is wider than the max content width).
- **Panel** (`#f8f9fa`): infobox body, TOC, quote boxes, table headers, sidebar tool groups — Wikipedia's own "light gray recessed" surface.
- **Border** (`#a2a9b1`): structural rules — infobox border, table borders, tab-strip border, ambox border.
- **Border Light** (`#eaecf0`): quiet dividers — section-heading underlines, infobox row dividers, sidebar separator.

### Named Rules
**The One-Hue Rule.** Link blue is the only saturated color in the system. It never becomes a background, an accent border, or a decorative fill — only text and icon strokes on links and the focus ring. A second saturated color anywhere in this system is a defect, not a variant.

## Typography

**Display / Heading Font:** "Linux Libertine", "Source Serif 4", Georgia, "Times New Roman", serif — Wikipedia's own declared title stack. "Linux Libertine" is not actually served by Google Fonts and is left in the stack deliberately (it's what real Wikipedia's CSS does too); the self-hosted "Source Serif 4" is what actually renders, with system Georgia as the final fallback.
**Body / UI Font:** Helvetica, "Helvetica Neue", Arial, sans-serif — Wikipedia's real interface stack, kept as-is rather than replaced with a more "distinctive" AI-default sans. This is a deliberate exception to the general anti-genericism rule: the mechanism of the whole page is faithful reproduction of a specific, real interface, so its native fonts are the correct choice, not a placeholder for one.

**Character:** Old-style serif titles over a plain, workhorse UI sans — exactly the plain/ornate split that makes real Wikipedia legible at encyclopedia scale, reused here so nothing about the typography itself telegraphs "joke."

### Hierarchy
- **Display** (400, 2.2rem, 1.25 line-height): the article title only ("Deven Ballback").
- **Section heading** (400, 1.5rem, 1.3, hairline-underlined): the numbered top-level sections (Early life, Notable incidents, Awards and honors, etc.).
- **Subsection heading** (700, 1.15rem): incident sub-headers (The river landing, The standoff, ...).
- **Body** (400, 15px, 1.65 line-height, ~74ch max measure): all prose.
- **Label** (700, 12px, 0.03em tracking, uppercase): sidebar box headers (NAVIGATION, TOOLS).
- **Fine print** (12.5–13px): infobox rows, reference list, categories footer, site footer — kept at or above 12px everywhere; nothing in the system renders under that floor even where the real product would.

## Layout

Two-column grid: a 190px fixed sidebar (Navigation, Tools) beside a fluid content column, inside a 1120px max-width shell. Below 900px the grid collapses to one column with the sidebar stacked above the content, border-bottom instead of border-right. The infobox floats right within the lead paragraph at 260px wide and clears to full width below 640px. The table of contents sits beside the infobox in normal flow (not force-cleared) so short lead copy doesn't strand it below a tall float. Section headings (`h2`) always start a fresh block; only the very first one (`#early-life`) forces a float-clear, since it is the one heading that reliably still shares vertical space with the infobox.

## Elevation & Depth

Flat by design — this is a direct constraint of the source interface, not an omission. Structure is communicated entirely by 1px borders and tonal panel backgrounds (`--panel` vs `--paper`), never by shadow. The one exception is the search-suggestions dropdown, which needs to visually separate from page content behind it and carries a soft `0 2px 6px rgba(0,0,0,0.15)` — the system's only shadow, reserved for a genuinely floating/overlapping element.

### Named Rules
**The No-Shadow Rule.** Nothing that sits in normal document flow gets a shadow. Depth exists only for elements that visually float above content (currently: the search-results dropdown).

## Shapes

Square corners throughout (`border-radius: 0`, formalized as `rounded.none`), except a 2px hairline radius reserved for the ambox banner (`rounded.hairline`), matching the source product's own restraint — Wikipedia essentially has no rounded-corner language, and introducing one here would be the first visual tell that the page isn't real.

## Components

### Tabs (Article / Talk / Read / Edit / View history)
- **Shape:** square, 1px border on the active tab only, no border-radius.
- **Active:** paper background, bordered on three sides, sits flush against the content panel's top border (no gap) — the defining tab-strip cue.
- **Inactive:** muted ink, underline on hover.
- **Disabled** (View history): 0.55 opacity, no hover feedback — still clickable for its joke toast, but reads as inert.

### Infobox
- **Shape:** square-cornered card, 1px border, panel-gray header/photo bands over a white body.
- **Photo:** authentic Wikipedia "no free image available" convention — a drawn person-silhouette icon, never a placeholder photo pretending to be real.
- **Rows:** label/value grid, hairline dividers between rows, label in muted ink.

### Ambox (maintenance banner)
- **Shape:** 2px-radius bordered box, amber-tinted background (`#fef6e7`), warning-triangle SVG icon.
- **Content:** bold lead line + bulleted issue list, each issue dated — the system's one intentionally "loud" component, and it's load-bearing for the joke (it's what tells the reader something is off before they've read a word of the article).

### Blockquote / Quote box
- **Style:** panel-gray background, no border, serif italic quote text, muted small-caps-weight citation line. Deliberately not a colored-left-border callout (a banned default pattern for this system) — real Wikipedia quote templates don't use one, and neither does this.

### Table (wikitable)
- **Style:** full-grid 1px borders on every cell, panel-gray header row, generous 7×10px cell padding so grid lines never crowd text.

### Table of Contents
- **Style:** panel-gray box, hairline border, collapsible via a text "hide/show" control (never an icon-only toggle) — numbered nested list matching the real numbering the section headings use (`2`, `2.1`, `2.2`, ...).

### Navigation (sidebar)
- **Style:** two label-headed groups (Navigation, Tools), plain link list, no icons, no active-state indicator beyond underline-on-hover — matches the source's minimal wayfinding, since this is a one-page article and only anchor-jumps exist.

## Do's and Don'ts

### Do:
- **Do** keep every component inside Wikipedia's real visual conventions (borders, panel grays, link blue) even when a "nicer" treatment is tempting — fidelity to the source is what makes the joke land.
- **Do** keep the one-hue rule: link blue only, no secondary accent color ever introduced.
- **Do** keep fine print at 12px or above; the source product's real type scale would go smaller, but this system's accessibility floor overrides it.
- **Do** route every future addition (new section, new component) through the same flat/bordered/serif-heading grammar already established.

### Don't:
- **Don't** add rounded corners, shadows, or gradients anywhere outside the two named exceptions above (ambox radius, dropdown shadow).
- **Don't** add a second saturated accent color, however small.
- **Don't** style the joke — no winking captions, no "look how fake this is" visual tells. The comedy lives entirely in the encyclopedia's dry copy voice, never in the chrome.
- **Don't** present any car photo, quote, or citation as verified fact outside the article's own skeptical framing; the footer disclaimer and inline "[citation needed]"/"[dubious – discuss]" tags are load-bearing, not decorative.
