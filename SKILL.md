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
| **pptx / pdf / docx / xlsx** | Inter (not Metropolis) | `design-tokens.json → outputFormats.documents` | N/A — use doc color roles | N/A |
| **React / Next.js prototype** | Metropolis UI → Inter fallback | `design-tokens.json → colors.semantic` | `components.json` | `globals-css-template.md`, `project-setup-guide.md` |
| **HTML / Tailwind one-off** | Metropolis UI → Inter fallback | `design-tokens.json → cssVariables` | `components.json → codeExample.tailwind` | N/A |

**Step 2 — Apply these rules to EVERY output:**
1. Text color is always `#1D2632` — never `#000000`
2. Max font weight is SemiBold (600) — never Bold (700)
3. Yellow (`#FFCD00`) is CTA-only — max 1 per view/slide
4. Buttons are pill-shaped (radius 48px) — never square
5. Inputs have bottom-border only — never fully bordered boxes
6. Every interactive element needs 5 states: enabled, hovered, focused, pressed, disabled

**Step 3 — Validate before delivering:**
- Check `design-tokens.json → forbidden` for banned colors and patterns
- Never use Blis Digital colors (`#007776`, `#00CDB6`)
- Never use yellow text on white or white text on yellow (1.3:1 contrast = invisible)

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

**When generating presentations, reports, PDFs, or spreadsheets, use Inter and the simplified document palette.**

For machine-readable tokens: `design-tokens.json → outputFormats.documents`

## A1. Document Color Palette

| Role | Hex | pptxgenjs | When to use |
|------|-----|-----------|-------------|
| Heading/body text | `#1D2632` | `1D2632` | All text |
| Secondary text | `#4A515B` | `4A515B` | Captions, footnotes |
| Accent | `#6DA6B9` | `6DA6B9` | Borders, icons, charts |
| CTA highlight | `#FFCD00` | `FFCD00` | Max 1 per slide/page |
| Table header bg | `#E2EDF1` | `E2EDF1` | Header rows |
| Table alt row | `#F4F7F9` | `F4F7F9` | Alternating rows |
| Border/divider | `#C5DBE3` | `C5DBE3` | Rules, table borders |
| Background | `#F4F7F9` | `F4F7F9` | Slide/page bg |
| Success | `#04B698` | `04B698` | Positive indicators |
| Warning | `#FFA652` | `FFA652` | Attention indicators |
| Error | `#D15858` | `D15858` | Negative indicators |

## A2. Document Typography

| Element | Font | Weight | Size |
|---------|------|--------|------|
| Slide title | Inter | SemiBold (600) | 28-36pt |
| Section heading | Inter | SemiBold (600) | 20-24pt |
| Body text | Inter | Medium (500) | 12-16pt |
| Caption | Inter | Regular (400) | 10-12pt |
| Table header | Inter | SemiBold (600) | 11-14pt |
| Table cell | Inter | Regular (400) | 10-12pt |

**Why Inter?** Metropolis UI is the brand font but not available in Office/PDF. Inter is the designated fallback.

## A3. Document Rules

- Max 3 colors per slide: text + accent + 1 status color
- Max 1 yellow highlight per slide/page
- Max weight SemiBold (600) — never Bold (700)
- Use `#1D2632` for text — never `#000000`
- pptxgenjs hex values must NOT include `#` prefix
- Chart colors (in order): blue → yellow → green → orange → red → dark blue → dark yellow → dark green
- Full chart palette + table specs + slide layouts: `design-tokens.json → outputFormats.documents`

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
# Section A — Documents (pptx, pdf, docx, xlsx)

**When generating presentations, reports, PDFs, or spreadsheets, use Inter and the simplified document palette.**

For machine-readable tokens: `design-tokens.json → outputFormats.documents`

## A1. Document Color Palette

| Role | Hex | pptxgenjs | When to use |
|------|-----|-----------|-------------|
| Heading/body text | `#1D2632` | `1D2632` | All text |
| Secondary text | `#4A515B` | `4A515B` | Captions, footnotes |
| Accent | `#6DA6B9` | `6DA6B9` | Borders, icons, charts |
| CTA highlight | `#FFCD00` | `FFCD00` | Max 1 per slide/page |
| Table header bg | `#E2EDF1` | `E2EDF1` | Header rows |
| Table alt row | `#F4F7F9` | `F4F7F9` | Alternating rows |
| Border/divider | `#C5DBE3` | `C5DBE3` | Rules, table borders |
| Background | `#F4F7F9` | `F4F7F9` | Slide/page bg |
| Success | `#04B698` | `04B698` | Positive indicators |
| Warning | `#FFA652` | `FFA652` | Attention indicators |
| Error | `#D15858` | `D15858` | Negative indicators |

## A2. Document Typography

| Element | Font | Weight | Size |
|---------|------|--------|------|
| Slide title | Inter | SemiBold (600) | 28-36pt |
| Section heading | Inter | SemiBold (600) | 20-24pt |
| Body text | Inter | Medium (500) | 12-16pt |
| Caption | Inter | Regular (400) | 10-12pt |
| Table header | Inter | SemiBold (600) | 11-14pt |
| Table cell | Inter | Regular (400) | 10-12pt |

**Why Inter?** Metropolis UI is the brand font but not available in Office/PDF. Inter is the designated fallback.

## A3. Document Rules

- Max 3 colors per slide: text + accent + 1 status color
- Max 1 yellow highlight per slide/page
- Max weight SemiBold (600) — never Bold (700)
- Use `#1D2632` for text — never `#000000`
- pptxgenjs hex values must NOT include `#` prefix
- Chart colors (in order): blue → yellow → green → orange → red → dark blue → dark yellow → dark green
- Full chart palette + table specs + slide layouts: `design-tokens.json → outputFormats.documents`

## A4. Presentation Design Language (from official .potx template)

### Three Slide Themes
The template alternates between three background themes:
1. **Dark** — bg `#1D2632` (navy), white text, yellow (#FFCD00) accents
2. **Yellow** — bg `#FFCD00`, black (#1D2632) text, black accents
3. **Light** — bg white or cream (#FEF9E4), black text, yellow accents

Use dark for: title slides, section dividers, icon grids, closing slides
Use yellow for: emphasis slides, quote slides, timelines, KPI slides, section dividers (alternate)
Use light for: content slides, charts, two-column layouts, image+text slides

### Hexagon Motif
The yellow hexagon is the core visual element across ALL presentations:
- **Icon containers**: Icons sit inside colored hexagons (blue #6DA6B9, yellow #FFCD00, green #04B698) on dark slides
- **Decorative elements**: Oversized hexagon outlines (#FFCD00 stroke) on closing slides
- **Small floating hexagons**: Solid yellow hexagons as decorative accents near images/quotes
- **Timeline nodes**: White hexagons with icons on dashed connector lines
- **KPI shapes**: Chevron/pentagon shapes for stat callouts (not standard rectangles)

### Label Tags
Two tag styles for subtitles and category markers:
- **Yellow tag**: Yellow (#FFCD00) background, black text — used for section subtitles, attributions
- **Black tag**: Black (#1D2632) background, white text — used for category labels, overlay captions

### Quote Slides
- Large quotation marks (") as decorative element, black, top-left of quote text
- Quote text: large (28-36pt), black, bold/semibold
- Attribution: "- Naam & Achternaam" in yellow tag below quote
- Image placeholder on left (with small yellow hexagon floating near top)

### Chart/Data Slides
- Charts use a teal/green gradient palette: light sage → medium teal → deep teal → dark teal
- NOT the blue primary palette — charts are distinctively green-family
- Chart colors (from template): approximately #CDF0EA, #6DA6B9, #04B698, #005C3E
- Pie charts: exploded segments, labels inside
- Bar/column charts: horizontal preferred for comparison
- Area charts: stacked, green gradient series

### Slide Layouts (from template)
| Layout | Theme | Description |
|--------|-------|-------------|
| Title (split) | Dark+Light | Left half dark navy, right half diagonal lines. Title large, yellow subtitle tag. |
| Title (split alt) | Light+Yellow | Left half diagonal lines, right half yellow. Title large, black subtitle tag. |
| Section divider (dark) | Dark | Full navy bg, repeating text watermark ("AMBITIOUS SMART REBELS HUMAN CENTERED"), centered yellow title |
| Section divider (yellow) | Yellow | Full yellow bg, same watermark, centered black title |
| Content (white) | Light | White bg, centered title, body text two-column or full-width |
| Content (yellow highlight) | Yellow+Light | Yellow tag above title, two-column: text left + bullets right |
| Quote (light) | Light | Image left, large quote right, yellow attribution tag |
| Quote (yellow) | Yellow | Yellow bg, image right, large quote left, black attribution tag |
| Data/KPI (white) | Light | Large chevron-shaped yellow KPI cards in 2x3 or 3-col grid |
| Data/Chart (white) | Light | Chart left or center, text right, yellow category tag |
| Icon grid (dark) | Dark | 3-4 colored hexagons in row, icon inside each, labels below |
| Timeline (light) | Light | Dashed line with hexagon nodes, numbered yellow tags, descriptions below |
| Timeline (yellow) | Yellow | Same layout, white hexagons, black end-marker hexagon |
| Image+text (light) | Light | Image placeholder left, text block right |
| Device mockup (light) | Light | Laptop/tablet mockup with screenshot, text left |
| Closing (yellow) | Yellow | Yellow bg with overlapping hexagon shapes, logo top-left, "Thank you" |
| Closing (dark) | Dark | Navy/grey bg with yellow hexagon outlines, logo top-left, "Thank you" white text |

### Logo Placement
- **Position**: always top-right corner
- **Variant**: dark logo (hexagon + "BLINQX" wordmark) on light/yellow slides, yellow+white on dark slides
- **Size**: approximately 120×40px equivalent

### Typography in Presentations
- Font: Inter (confirmed by template)
- Title slides: 44-52pt, Regular or Medium weight (NOT bold)
- Content headings: 28-36pt, Regular
- Body text: 14-16pt, Regular
- Category tags: 12-14pt, Medium, inside colored rectangle
- Page numbers: bottom-right, small (10pt)

### Design Principles for Presentations
1. **Alternate themes** — don't use the same background for consecutive slides
2. **Yellow = emphasis** — use yellow bg or elements to highlight the most important slides
3. **Hexagons everywhere** — use the hexagon shape as icon container, decorative element, or visual motif
4. **Large typography** — titles are oversized (44pt+) for impact
5. **Minimal text per slide** — body text is secondary, visuals and headings carry the message
6. **Diagonal accents** — subtle diagonal line patterns and angled geometric shapes add texture
7. **Green for data** — charts use teal/green palette, NOT the primary blue

| File | When to load |
|------|-------------|
| `references/brand-identity.md` | **Read first** — design rationale, principes, do's/don'ts, scherm-compositie, beslisboom |
| `references/design-tokens.json` | **Always** — tokens, semantic mappings, format routing, forbidden patterns, shadcn mapping |
| `references/components.json` | **Always** — component specs, Figma links, shadcn mapping, composition rules, imports |
| `references/component-patterns.md` | Copy-paste TSX examples for all 14 component types |
| `references/page-templates.md` | Page layout templates with breakpoints |
| `references/project-setup-guide.md` | Next.js + shadcn project scaffolding |
| `references/globals-css-template.md` | Complete `app/globals.css` with all 68 Figma CSS variables |
| `references/shadcn-config-template.md` | `components.json` + PostCSS config |
| `references/ai-coding-rules.md` | Comprehensive rule set (~150 rules) for v0, Claude Code, Cursor, and other AI code generators |

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

---

# Cheat Sheet — 20 Most Used Values

> For quick reference by v0, Claude Code, or any AI code generator. No need to load reference files for these basics.

```
COLORS
──────────────────────────────────────────────
Navy (text/bg):     #1D2632    N100
Dark surface:       #343C47    N90
Help text:          #4A515B    N80
Placeholder:        #777D84    N60
Primary blue:       #6DA6B9    B100
Dark blue (headings):#316A7D   B120
CTA yellow:         #FFCD00    Y100
Yellow hover:       #FFD631
Page background:    #F4F7F9    L20
Card background:    #FFFFFF    W100
Header background:  #E2EDF1    B20
Border default:     #C5DBE3    B40
Error:              #D15858    R100
Success:            #04B698    G100
Warning:            #FFA652    O100

TYPOGRAPHY
──────────────────────────────────────────────
Font: Inter (Metropolis UI if self-hosted)
Max weight: SemiBold (600) — NEVER Bold (700)
H1: 45px, H2: 28px, H3: 22px, Body: 16/14/12px

COMPONENTS
──────────────────────────────────────────────
Buttons:  rounded-full (pill 48px) — NEVER square
Inputs:   bottom-border only, bg #F4F7F9
Cards:    rounded-xl, shadow-sm, border #C5DBE3
Tabs:     border-b-2 #6DA6B9 (active), no bg change
Switches: ON=#6DA6B9, OFF=border #CAD5E3

RULES
──────────────────────────────────────────────
• Text = #1D2632, never #000000
• Max 1 yellow CTA per view
• 5 states: enabled/hovered/focused/pressed/disabled
• Spacing: multiples of 4px only
• Locale: Dutch (lang="nl")
```
