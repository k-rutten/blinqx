---
name: blinqx-brand
version: "2.2.0"
updated: "2026-03-19"
description: >
  Blinqx design system — colors, typography, spacing, component specs, and layout patterns.
  Use whenever generating output for the Blinqx product family (eBlinqx, WorQX, Blinqx portals).
  Trigger on: "Blinqx", "eBlinqx", "WorQX", "Blinqx style", "Blinqx design system", "Blinqx UI",
  "Blinqx huisstijl", "Blinqx branding", or Blinqx styleguide references.
  Blinqx is NOT Blis Digital — they share a parent company but have different brand identities.
  Read this skill ALONGSIDE format-specific skills (pptx, docx, pdf, xlsx, frontend-design).
---

# Blinqx Design System

> **Figma**: [Style Guide](https://www.figma.com/design/F5hNn1cAwIeKGJgEFJV64q) · [WorQX reference](https://www.figma.com/design/fJfu8EJysRTl8XFsNyXUF3)
> **Machine-readable**: `references/design-tokens.json` · `references/components.json`

---

## Blinqx Identity

Blinqx is financial software for mortgage advisors and homebuyers (NL). The design balances **trustworthy** (biggest purchase of their lives) with **approachable** (not intimidating like a bank). Every design choice serves this balance — pill buttons feel friendly, navy replaces harsh black, muted blue conveys calm expertise.

**When in doubt:** Would a mortgage advisor show this to a client? Would a first-time homebuyer feel comfortable? Is there one clear CTA per view?

**Full design rationale, do's/don'ts, color/font rules, component principles, and decision tree for new elements:** → `references/brand-identity.md`

---

## How to Apply This Skill

**Step 1 — Determine output format:**

| Creating... | Font | Color source | Component source | Setup templates |
|---|---|---|---|---|
| **pptx** | Metropolis (fallback: Inter/Calibri) | `design-tokens.json → outputFormats.documents` | N/A — use template layouts | See A5 |
| **pdf / docx / xlsx** | Inter (Metropolis not embeddable) | `design-tokens.json → outputFormats.documents` | N/A — use doc color roles | N/A |
| **React / Next.js prototype** | Metropolis UI → Inter fallback | `design-tokens.json → colors.semantic` | `components.json` | `globals-css-template.md`, `project-setup-guide.md` |
| **HTML / Tailwind one-off** | Metropolis UI → Inter fallback | `design-tokens.json → cssVariables` | `components.json → codeExample.tailwind` | N/A |

**Step 2 — Apply these rules to EVERY output:**
1. Text color is always `#1D2632` — never `#000000` (except: presentation slide backgrounds may use `#000000` per theme, see A4)
2. Max font weight is SemiBold (600) — never Bold (700)
3. Yellow (`#FFCD00`) is CTA-only — max 1 per view/slide
4. Buttons are pill-shaped (radius 48px) — never square
5. Inputs have bottom-border only — never fully bordered boxes
6. Every interactive element needs 5 states: enabled, hovered, focused, pressed, disabled

**Step 3 — Validate before delivering:**
- Check `design-tokens.json → forbidden` for banned colors and patterns
- Never use Blis Digital colors (`#007776`, `#00CDB6`)
- Never use yellow text on white or white text on yellow (1.3:1 contrast = invisible)

**Step 4 — Load reference files as needed:**

| File | When to load |
|------|-------------|
| `references/brand-identity.md` | **Read first** — design rationale, do's/don'ts, decision tree |
| `references/design-tokens.json` | **Always** — tokens, semantic mappings, format routing |
| `references/components.json` | **Always** — component specs, Figma links, shadcn mapping |
| `references/component-patterns.md` | Copy-paste TSX examples for all 14 component types |
| `references/page-templates.md` | Page layout templates with breakpoints |
| `references/project-setup-guide.md` | Next.js + shadcn project scaffolding |
| `references/globals-css-template.md` | Complete `app/globals.css` with all CSS variables |
| `references/shadcn-config-template.md` | `components.json` + PostCSS config |
| `references/ai-coding-rules.md` | Rule set (~150 rules) for AI code generators |

---

## TLDR — Quick Reference

### Colors (grab & go)
```
Primary:     #6DA6B9  (blue)     — buttons, links, focus, active switch
CTA/Accent:  #FFCD00  (yellow)   — max 1 CTA per view, active menu
Dark:        #1D2632  (navy)     — nav backgrounds, body text
Page bg:     #F4F7F9  (light)    — app background
Card bg:     #FFFFFF  (white)    — all cards, panels
Header bg:   #E2EDF1  (blue-20)  — page headers, surface-level-1
Border:      #C5DBE3  (blue-40)  — dividers, outlines
Help text:   #4A515B  (neutral)  — secondary text, tooltips
Placeholder: #777D84             — input placeholders
Error:       #D15858  (red)      — error states, destructive
Success:     #04B698  (green)    — positive states
Warning:     #FFA652  (orange)   — attention needed
```

### Typography (grab & go)
```
Font:   'Metropolis UI', 'Inter', Arial, sans-serif
        (use Inter for pptx/pdf where Metropolis unavailable)

H1:     45px / 52px / Medium 500   — page titles
H2:     28px / 36px / SemiBold 600 — section headings
H3:     22px / 28px / SemiBold 600 — card/modal titles
Body L: 16px / 24px / Medium 500   — body text, inputs
Body M: 14px / 20px / SemiBold 600 — buttons, tabs, emphasis
Body S: 12px / 16px / Medium 500   — captions, menu labels
```

### Layout (grab & go)
```
Spacing:     4px base (4, 8, 12, 16, 20, 24, 32, 40)
Radius:      16px cards/headers, 8px message bars, 4px tooltips, 48px buttons (pill)
Shadows:     card (resting), hovered (interactive), popup (overlay)
```

Full token data: `references/design-tokens.json`
Full component specs: `references/components.json`

---

# Section A — Documents (pptx, pdf, docx, xlsx)

**When generating presentations, use Metropolis (fallback: Inter/Calibri) and the template-first approach (see A5). For reports, PDFs, and spreadsheets, use Inter and the simplified document palette.**

For machine-readable tokens: `design-tokens.json → outputFormats.documents`

## A1. Document Color Palette

| Role | Hex | When to use |
|------|-----|-------------|
| Heading/body text | `#1D2632` | All text (docs). Presentations: white on dark, navy on light/yellow |
| Secondary text | `#4A515B` | Captions, footnotes |
| Accent | `#6DA6B9` | Borders, icons, charts |
| CTA highlight | `#FFCD00` | Max 1 per slide/page |
| Table header bg | `#E2EDF1` | Header rows |
| Table alt row | `#F4F7F9` | Alternating rows |
| Border/divider | `#C5DBE3` | Rules, table borders |
| Background | `#F4F7F9` | Page bg (docs). Presentations: see A4 theme colors |
| Success | `#04B698` | Positive indicators |
| Warning | `#FFA652` | Attention indicators |
| Error | `#D15858` | Negative indicators |

## A2. Document Typography

| Element | Font | Weight | Size | Notes |
|---------|------|--------|------|-------|
| Slide title | Metropolis | Thin/Regular | 60pt | Presentations only (see A4) |
| Slide heading | Metropolis | SemiBold (600) | 36-45pt | Presentations only |
| Slide body | Metropolis | Regular (400) | 14-16pt | Presentations only |
| Slide tag/label | Metropolis | SemiBold (600) | 12-14pt | Inside snip1Rect shapes |
| Report/doc heading | Inter | SemiBold (600) | 20-24pt | PDF, docx, xlsx |
| Report/doc body | Inter | Medium (500) | 12-16pt | PDF, docx, xlsx |
| Caption | Inter | Regular (400) | 10-12pt | All formats |
| Table header | Inter | SemiBold (600) | 11-14pt | All formats |
| Table cell | Inter | Regular (400) | 10-12pt | All formats |

**Font logic**: The .potx template embeds Metropolis (Semibold + Thin). python-pptx preserves this when loading the template. For pdf/docx/xlsx where Metropolis is not embeddable, use Inter as fallback.

## A3. Document Rules

- Max 3 colors per slide: text + accent + 1 status color
- Max 1 yellow highlight per slide/page
- Max weight SemiBold (600) — never Bold (700)
- Text color: `#1D2632` for body text. Exception: dark slide backgrounds use `#000000` (scheme:tx1), see A4
- **Presentations**: Always use python-pptx with the .potx template (see A5). Never recreate slides from scratch
- Chart colors (in order): teal/green palette for presentations (#CDF0EA, #6DA6B9, #04B698, #005C3E), standard palette for documents
- Full chart palette + table specs + slide layouts: `design-tokens.json → outputFormats.documents`

## A4. Presentation Design Language (from official Blinqx_Template-Basic.potx)

> **CRITICAL**: Always build presentations FROM the .potx template, never recreate slides from scratch.
> The template file is `Blinqx_Template-Basic.potx` (41 example slides, 87 layouts).
> Use python-pptx to load it, select slides, and fill placeholders. See A5 for the approach.

### Theme Color Scheme (from theme1.xml)

| Scheme slot | Hex | Role |
|-------------|-----|------|
| dk1 (tx1) | `#000000` | **Black** — primary dark slide backgrounds |
| lt1 (bg1) | `#FFFFFF` | White — light text on dark, light backgrounds |
| dk2 (tx2) | `#1D2632` | **Navy** — accent dark fills, snip1Rect cards, title slide bg |
| lt2 (bg2) | `#FFCD00` | **Yellow** — primary accent, yellow slides, tags |
| accent1 | `#EEE3C3` | Cream — decorative fills |
| accent2 | `#CAD5E3` | Light blue — decorative blob shapes (closing slide) |
| accent3 | `#6DA6B9` | **Blue** — hexagon fill, chart color |
| accent4 | `#04B698` | **Green** — hexagon fill, chart color |
| accent5 | `#FFF5CC` | Light yellow |
| accent6 | `#FFCD00` | Yellow (duplicate) |

**IMPORTANT CORRECTION**: Dark slide backgrounds are `#000000` (BLACK, scheme:tx1), NOT `#1D2632` (navy). Navy is used as fill color for accent shapes (snip1Rect cards, title slide background, decorative "Graphic 8" blobs). The .potx XML confirms: most dark layouts reference `scheme:tx1` (black) for background, while `scheme:tx2` (navy) is used for specific layouts like title slides and closing slides.

### Three Slide Themes

1. **Dark** — bg black (#000000) or navy (#1D2632), white/yellow text, yellow accents
2. **Yellow** — bg #FFCD00, navy (#1D2632) text, black/white accents
3. **Light** — bg white (#FFFFFF) or cream, navy text, yellow accents

### Hexagon Motif

The Blinqx hexagon (logo shape) is the core visual element. In the template, hexagons use `prstGeom="hexagon"` rotated 90° (pointy-top orientation):

- **Icon containers**: 3 colored hexagons (blue #6DA6B9, navy #1D2632, green #04B698) on dark slides. Size ~2.6"×2.3", with icon images (1.575"×1.575") centered inside. (Layout 34, slide 16)
- **Photo placeholders**: Hexagon shapes with `pattFill pct5` (5% crosshatch pattern). The diagonal-line/dot pattern IS the placeholder indicator — users replace with actual photos.
- **Decorative elements**: Oversized hexagon outlines (#FFCD00 stroke) on closing slides, small filled hexagons as accents.
- **Timeline nodes**: White hexagon freeform shapes (~1.3"×1.5") with icon images (~0.84"×0.84") centered inside.
- **"Graphic 8" blobs**: Large custom-geometry pentagon-like shapes used as decorative overlapping background elements. Fill: accent2 (#CAD5E3) with ~35% alpha. Found on closing slides, content slides.

### Label Tags (snip1Rect)

Tags use `prstGeom="snip1Rect"` (Rectangle: Single Corner Snipped), NOT plain rectangles:

- **Yellow tag**: Fill #FFCD00, navy text — for subtitles, section labels
- **Black/navy tag**: Fill #1D2632 or #000000, white text — for category labels, captions
- **KPI cards**: Paired snip1Rect shapes (outer fill + inner outline), rotated 90°, arranged in 2×3 grid. (Layout 22)

### Watermark Backgrounds

The "AMBITIOUS SMART REBELS HUMAN CENTERED" text is NOT rendered as text shapes — it's a **PNG background image** applied via `blipFill` on individual slides:

- `image6.png` (100KB) — dark watermark: outlined text on #1D2632 background → used on dark section dividers
- `image7.png` (123KB) — yellow watermark: outlined text on #FFCD00 background → used on yellow section dividers

### Logo

- **File**: `image2.png` from .potx (yellow hexagon + white "BLINQX" wordmark, transparent bg)
- **Dark slides**: Logo top-left, large: x=0.15" y=0.48" w=4.3" h=1.32" (title) or x=0.51" y=1.59" w=4.21" h=1.23" (closing)
- **Light/yellow slides**: Logo top-right, small: x=11.18" y=0.3" w=1.94" h=0.59"
- **Asset**: Also available as `assets/blinqx-logo.svg` for other formats

### Typography in Presentations

- **Font**: Metropolis Semibold & Metropolis Thin (confirmed by template XML guide text). Fallback: Calibri or Inter if Metropolis unavailable.
- Title slides: 60pt, Metropolis Thin or Regular
- Content headings: 36-45pt, Metropolis Semibold
- Body text: 14-16pt, Regular
- Category tags: 12-14pt, inside snip1Rect shape
- Page numbers: bottom-right x=12.54" y=6.95", 16pt

### Chart/Data Slides

- Charts use a teal/green gradient palette: #CDF0EA, #6DA6B9, #04B698, #005C3E
- NOT the blue primary palette — charts are distinctively green-family
- Bar/column charts: horizontal preferred for comparison

### Design Principles for Presentations

1. **Alternate themes** — don't use the same background for consecutive slides
2. **Yellow = emphasis** — use yellow bg or elements to highlight the most important slides
3. **Hexagons everywhere** — use the hexagon shape as icon container, decorative element, or visual motif
4. **Large typography** — titles are oversized (60pt) for impact
5. **Minimal text per slide** — body text is secondary, visuals and headings carry the message
6. **Photo placeholders = crosshatch hexagons** — diagonal-line patterns in the template are photo slots
7. **Green for data** — charts use teal/green palette, NOT the primary blue

## A5. Presentation Template: Layout Catalog & Build Approach

> **Always build from the .potx template** using python-pptx. Never recreate slides with pptxgenjs.

### Build Approach (python-pptx)

```python
from pptx import Presentation

# 1. Convert .potx → .pptx (fix content type in [Content_Types].xml)
# 2. Load the converted file
prs = Presentation('template-base-fixed.pptx')

# 3a. REUSE existing slides: fill placeholders by idx
slide = prs.slides[0]  # Access existing template slide
for ph in slide.placeholders:
    if ph.placeholder_format.idx == 0:  # Title
        ph.text_frame.paragraphs[0].runs[0].text = "Your Title"

# 3b. CREATE new slides from layout
layout = prs.slide_layouts[3]  # "Title Slide Dark - 2"
new_slide = prs.slides.add_slide(layout)
new_slide.placeholders[0].text = "New Title"

# 4. Delete unwanted slides (reverse order, via XML manipulation)
# 5. Save
prs.save('output.pptx')
```

### Layout Index Catalog (87 layouts, grouped by purpose)

**Title Slides** — for opening/cover:

| Layout # | Name | Theme | Placeholders |
|----------|------|-------|-------------|
| 0 | Title Slide Yellow - 1 | Yellow | PICTURE(15), TITLE(0), BODY(20) |
| 1 | Title Slide Dark - 1 | Dark | PICTURE(14), TITLE(0), BODY(20) |
| 2 | Title Slide Yellow - 2 | Yellow | PICTURE(15), TITLE(0), BODY(20), SLIDE_NUM |
| 3 | Title Slide Dark - 2 | Dark | PICTURE(16), TITLE(0), BODY(20) |
| 4 | Title Slide Yellow - 3 | Yellow | PICTURE(14), TITLE(0), BODY(20) |
| 5 | Title Slide Dark - 3 | Dark | PICTURE(14), TITLE(0), BODY(20), FOOTER |

**Section Dividers / Quote Slides** — for transitions:

| Layout # | Name | Theme | Placeholders |
|----------|------|-------|-------------|
| 6 | Quote Slide Dark | Dark | TITLE(0) |
| 7 | Quote Slide Yellow | Yellow | TITLE(0) |
| 8 | Quote Slide + Media | Mixed | PICTURE(14), CENTER_TITLE(0) |

**Content Text-Only** — for text-heavy slides:

| Layout # | Name | Theme | Key Placeholders |
|----------|------|-------|-----------------|
| 9 | Content Text Only 1 - Dark | Dark | TITLE(0), BODY(21) |
| 10 | Content Text Only 1 - White | White | TITLE(0), BODY(21) |
| 11 | Content Text Only 1 - Yellow | Yellow | TITLE(0), BODY(21) |
| 12-14 | Content Text Only 2 - Blue/Green/Yellow | Various | TITLE(0), 4-5× BODY |
| 15-18 | Content Text Only 3 - White/Blue/Green/Yellow | Various | TITLE(0), 3× BODY |
| 19-21 | Content Text Only 4 - Dark/White/Yellow | Various | TITLE(0), BODY(10) |
| 34 | Content Text Only 5 - Dark | Dark | TITLE(0), 3× BODY — **hexagon icon grid** |
| 35 | Content Text Only 5 - White | White | TITLE(0), 3× BODY — **hexagon icon grid** |
| 36-41 | Content Text Only 6 variants | Various | TITLE(0), 2× BODY |

**Data / KPI Slides**:

| Layout # | Name | Theme | Key Placeholders |
|----------|------|-------|-----------------|
| 22 | Content Data 1 - White | White | TITLE(0), 12× BODY — **2×3 KPI grid** |
| 23-24 | Content Data variants | White | Various data layouts |
| 30-33 | Content Data 3/4 | White | Simplified data layouts |

**Content + Media** — text with photo placeholders:

| Layout # | Name | Theme | Key Placeholders |
|----------|------|-------|-----------------|
| 42 | Text + Media 1 - White | White | PICTURE(16), TITLE(0), 2× BODY |
| 43 | Text + Media 2 - White | White | 3× PICTURE, TITLE(0), BODY |
| 44-45 | Text + Media 3 | White/Yellow | PICTURE(10), TITLE(0), 2-3× BODY |
| 58-61 | Text + Media 4 variants | White/Yellow | Multiple photos, TITLE, BODY |
| 64-65 | Text + Media 6 | White/Yellow | TITLE(0), 4× PICTURE — **multi-photo layout** |
| 66-68 | Text + Media 7-9 | White | Various text+photo combos |

**Timeline Slides**:

| Layout # | Name | Theme | Key Placeholders |
|----------|------|-------|-----------------|
| 46-47 | Timeline + Media 1 - White | White | TITLE(0), PICTURES, milestone text |
| 48-51 | Timeline + Media 2 - White | White | Multiple photos + milestones |
| 52-54 | Timeline + Media 2 - Yellow | Yellow | Milestone text, descriptions |
| 55-56 | Timeline Text 1 - White | White | Text-only timeline, many BODY |

**Mockup Slides** — device screenshots:

| Layout # | Name | Theme | Key Placeholders |
|----------|------|-------|-----------------|
| 69-70 | Mockup - Combi | White | 2× PICTURE, TITLE, BODY |
| 71 | Mockup - Laptop | White | PICTURE(10), TITLE(0), BODY(20) |
| 72 | Mockup - Combi 3 | White | 2× PICTURE, TITLE, BODY |
| 73 | Mockup - Tablet | White | PICTURE(10), TITLE, BODY |
| 74 | Mockup - Laptop 2 | White | PICTURE(10), TITLE, 2× BODY |
| 75 | Mockup - Mobile | White | PICTURE(11), TITLE, 2× BODY |
| 76 | Mockup - Tablet 2 | White | PICTURE(11), TITLE, 2× BODY |
| 77 | Mockup - Desktop | White | PICTURE(10), TITLE, 2× BODY |
| 78-81 | Mockup variants | White | Various device combos |

**Utility Slides**:

| Layout # | Name | Theme | Placeholders |
|----------|------|-------|-------------|
| 82 | Blanco + Header (alt) | — | TITLE(0) |
| 83 | Blanco + Header | — | TITLE(0), BODY(10) |
| 84 | Blanco Slide | — | (none) |
| 85 | End Slide - Yellow | Yellow | TITLE(0) |
| 86 | End Slide - Dark | Dark | TITLE(0) |

### Recommended Pitch Deck Selection

For a standard 10-slide pitch, use these template slides (0-indexed from the 41 example slides):

| # | Template slide | Layout | Purpose |
|---|---------------|--------|---------|
| 1 | S1 (idx 0) | Title Slide Dark - 2 | Opening / cover |
| 2 | S3 (idx 2) | Quote Slide Dark | Section divider |
| 3 | S5 (idx 4) | Content Text Only 1 - White | Body content |
| 4 | S9 (idx 8) | Content Data 1 - White | KPI / metrics |
| 5 | S16 (idx 15) | Content Text Only 5 - Dark | Icon grid (hexagons) |
| 6 | S8 (idx 7) | Content Text Only 4 - Yellow | Data/chart context |
| 7 | S26 (idx 25) | Timeline + Media 2 - Yellow | Roadmap |
| 8 | S21 (idx 20) | Content Text + Media 6 - White | Team / photos |
| 9 | S31 (idx 30) | Mockup - Laptop | Product demo |
| 10 | S41 (idx 40) | End Slide - Dark | Closing |

---

# Section B — Prototypes (web/app)

**When generating React, HTML, CSS, or Tailwind code.**

## B1. Tech Stack

| Layer | Technology |
|-------|-----------|
| Framework | Next.js (App Router) + React |
| Language | TypeScript |
| Styling | Tailwind CSS v4 (`@theme inline` in CSS, no `tailwind.config.ts`) |
| Components | shadcn/ui (New York style, neutral base, CSS variables) |
| Primitives | Radix UI |
| Icons | Lucide React |
| Class utils | `class-variance-authority` + `clsx` + `tailwind-merge` |
| Font | Inter via `next/font/google` (Metropolis UI if self-hosted) |
| Locale | Dutch (`lang="nl"`) |

```tsx
import { Inter } from "next/font/google"
const inter = Inter({ subsets: ["latin"], variable: "--font-inter", display: "swap" })
```

Full project setup: `references/project-setup-guide.md`
Full globals.css: `references/globals-css-template.md`
shadcn config: `references/shadcn-config-template.md`

## B2. Color System

Full palette (8 families, 96 hex values) and 68 CSS custom properties (46 surface, 14 text, 7 border, 1 background): `references/design-tokens.json`

**Key semantic tokens (Figma-confirmed CSS variable names):**
```
var(--surface/surface-blue-default, #6DA6B9)   → primary button bg, switch ON
var(--surface/surface-yellow-default, #FFCD00)  → CTA button bg
var(--text/text-default, #1D2632)               → all body text
var(--text/text-blue-dark, #316A7D)             → alert titles, info text
var(--text/text-red-dark, #951C1C)              → error/warning text
var(--text/text-green-dark, #005C3E)            → success text
var(--border/border-default, #C5DBE3)           → card borders, chip borders
var(--surface/surface-help, #4A515B)            → tooltip bg
var(--background/background-default, #F4F7F9)   → page bg
```

**Status message patterns (copy these directly):**
```
Warning:  bg var(--surface/surface-badge, #EDBCBC)         text var(--text/text-red-dark, #951C1C)
Info:     bg var(--surface/surface-pull-down-menu, #EFF2F7) text var(--text/text-blue-dark, #316A7D)
Success:  bg var(--surface/surface-green-light, #CDF0EA)   text var(--text/text-green-dark, #005C3E)
Error:    bg var(--surface/surface-red-light, #F6DEDE)     text var(--text/text-red-dark, #951C1C)
```

Color do's/don'ts, contrast ratios, forbidden combinations: → `references/brand-identity.md` §4

## B3. Component Quick Reference

> Full specs + Figma links: `references/components.json`

> Copy-paste TSX examples for all components: `references/component-patterns.md`

### Buttons ([Figma](https://www.figma.com/design/F5hNn1cAwIeKGJgEFJV64q/?node-id=4426-745&m=dev))
```
Shape: pill (border-radius: 48px) — NEVER square
Primary:   bg #6DA6B9, text #1D2632       Danger:  bg #D15858, text #FFFFFF
CTA:       bg #FFCD00, text #1D2632       Outlined: border #C5DBE3, text #1D2632
Sizes: large 48px, medium 40px, small 32px, x-small 28px
```

### Inputs ([Figma](https://www.figma.com/design/F5hNn1cAwIeKGJgEFJV64q/?node-id=4215-1586&m=dev))
```
Bottom-border ONLY — never fully bordered. Background: #F4F7F9.
States: default N40, hover N80, focus B100, error R100
Label floats from center to top on focus. Sizes: 56px / 44px.
```

### Navigation ([Figma](https://www.figma.com/design/F5hNn1cAwIeKGJgEFJV64q/?node-id=4215-1585&m=dev))
```
Sidebar: 80px wide, bg #1D2632
Inactive: transparent, icon #D2D4D6    Active: bg #FFE680, icon dark, label #FFCD00
Selected: bg #343C47, icon white       Hover: subtle bg shift per state
```

### Cards · Alerts · Modals · Tabs · Switches · Chips · Tooltips · Date Picker
```
Cards:    white bg, 16px radius, shadow-card, border-bottom #C5DBE3
Alerts:   w-400, white bg, 16px radius, shadow-popup, title H3 color #316A7D
Modals:   w-520, white bg, 16px radius, shadow-popup, overlay rgba(0,0,0,0.5)
Tabs:     active border-bottom 2px #6DA6B9, inactive text #777D84
Switches: ON track #6DA6B9 thumb white, OFF track border #CAD5E3 thumb #CAD5E3
Chips:    pill shape, 32px height, default white+border #C5DBE3
Tooltips: bg #4A515B, white text, 4px radius, shadow-hovered
Picker:   white bg, 16px radius, shadow-popup, selected day bg #6DA6B9
Message bars: 8px radius (NOT 16px), warning #EDBCBC, info #EFF2F7
```

## B5. Layout Patterns

### Pattern 1: Top Nav + Content (WorQX)
```
┌──────────────────────────────────────────────┐
│ [Logo 124×40] [Nav items] [Org picker] [User]│  90px nav
├──────────────────────────────────────────────┤
│              ┌──────────────┐                │
│              │ Content 1120px│                │
│              │ bg: #F4F7F9  │                │
│              └──────────────┘                │
└──────────────────────────────────────────────┘
```

### Pattern 2: Sidebar + Content
```
┌──────┬──────────────────────────────────────┐
│ 80px │  Header (title + tabs + actions)     │
│ dark ├──────────────────────────────────────┤
│      │  Content area, bg: #F4F7F9          │
└──────┴──────────────────────────────────────┘
```

### Content Grid Patterns
```
Dashboard:  [KPI cards 3-col] + [Main 70% | Side 30%]
List/Table: [Toolbar: search + filters] + [Table card]
Detail:     [Content 60-70%] + [Side panel 30-40%]
Form:       [Form card, max-w 640px, centered]
```

---

# Section D — Assets

| File | Use case |
|------|----------|
| `assets/worqx-logo.svg` | White text logo → dark backgrounds (header) |
| `assets/eblinqx-worqx-logo.svg` | Dark text logo → light backgrounds (login card) |
| `assets/icon.svg` | VX monogram → browser tab favicon |
| `assets/blinqx-logo.svg` | Hexagon + wordmark → general brand use |

Logo rules: min 24×24 (favicon), standard 124×40 (nav). Dark on light bg, white on dark bg. Never stretch. Place in `public/images/`, favicon at `public/icon.svg`.

The **yellow hexagonal chevron** (`#FFCD00`) is the shared Blinqx brand element across all products.
