---
name: blinqx-brand
version: "3.0.0"
updated: "2026-03-23"
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
> **Machine-readable**: `references/shared/design-tokens.json` · `references/prototype/components.json`

---

## Blinqx Identity

Blinqx is financial software for mortgage advisors and homebuyers (NL). The design balances **trustworthy** (biggest purchase of their lives) with **approachable** (not intimidating like a bank). Every design choice serves this balance — pill buttons feel friendly, navy replaces harsh black, muted blue conveys calm expertise.

**When in doubt:** Would a mortgage advisor show this to a client? Would a first-time homebuyer feel comfortable? Is there one clear CTA per view?

**Full design rationale, do's/don'ts, color/font rules, component principles, and decision tree for new elements:** → `references/shared/brand-identity.md`

---

## How to Apply This Skill

**Step 1 — Determine output format and read the right guide:**

| Creating... | Read this guide | Font | Color source |
|---|---|---|---|
| **pptx** | → `references/pptx-guide.md` | Metropolis (embedded in .potx) | `design-tokens.json → outputFormats.documents` |
| **pdf / docx / xlsx** | → (use doc palette below) | Inter (Metropolis not embeddable) | `design-tokens.json → outputFormats.documents` |
| **React / Next.js prototype** | → `references/prototype/guide.md` | Metropolis UI → Inter fallback | `design-tokens.json → colors.semantic` |
| **HTML / Tailwind one-off** | → `references/prototype/guide.md` | Metropolis UI → Inter fallback | `design-tokens.json → cssVariables` |

**Step 2 — Apply these rules to EVERY output:**
1. Text color is always `#1D2632` — never `#000000` (except: presentation slide backgrounds may use `#000000` per theme)
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
| `references/pptx-guide.md` | **Presentations** — template layouts, build approach, design language |
| `references/prototype/guide.md` | **Web/app** — tech stack, components, layout patterns |
| `references/shared/brand-identity.md` | **Read first** — design rationale, do's/don'ts, decision tree |
| `references/shared/design-tokens.json` | **Always** — tokens, semantic mappings, format routing |
| `references/prototype/components.json` | **Prototypes** — Blinqx UI Kit specs, Figma links, shadcn mapping |
| `references/prototype/component-patterns.md` | Copy-paste TSX examples for all 14 component types |
| `references/prototype/page-templates.md` | Page layout templates with breakpoints |
| `references/prototype/project-setup-guide.md` | Next.js + shadcn project scaffolding |
| `references/prototype/globals-css-template.md` | Complete `app/globals.css` with all CSS variables |
| `references/prototype/shadcn-config-template.md` | `components.json` + PostCSS config |
| `references/prototype/ai-coding-rules.md` | Rule set (~150 rules) for AI code generators |

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
        pptx: Metropolis (embedded in .potx template)
        pdf/docx/xlsx: Inter (Metropolis not embeddable)

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

Full token data: `references/shared/design-tokens.json`
Full component specs: `references/prototype/components.json`

---

## Document Color Palette (pdf, docx, xlsx)

| Role | Hex | When to use |
|------|-----|-------------|
| Heading/body text | `#1D2632` | All text (docs). Presentations: white on dark, navy on light/yellow |
| Secondary text | `#4A515B` | Captions, footnotes |
| Accent | `#6DA6B9` | Borders, icons, charts |
| CTA highlight | `#FFCD00` | Max 1 per slide/page |
| Table header bg | `#E2EDF1` | Header rows |
| Table alt row | `#F4F7F9` | Alternating rows |
| Border/divider | `#C5DBE3` | Rules, table borders |
| Background | `#F4F7F9` | Page bg (docs) |
| Success | `#04B698` | Positive indicators |
| Warning | `#FFA652` | Attention indicators |
| Error | `#D15858` | Negative indicators |

## Document Typography (pdf, docx, xlsx)

| Element | Font | Weight | Size |
|---------|------|--------|------|
| Report/doc heading | Inter | SemiBold (600) | 20-24pt |
| Report/doc body | Inter | Medium (500) | 12-16pt |
| Caption | Inter | Regular (400) | 10-12pt |
| Table header | Inter | SemiBold (600) | 11-14pt |
| Table cell | Inter | Regular (400) | 10-12pt |

**Font logic**: For pdf/docx/xlsx where Metropolis is not embeddable, use Inter as fallback. For presentations, see `references/pptx-guide.md`.

## Document Rules

- Max 3 colors per slide: text + accent + 1 status color
- Max 1 yellow highlight per slide/page
- Max weight SemiBold (600) — never Bold (700)
- Text color: `#1D2632` for body text
- Chart colors (in order): teal/green palette (#CDF0EA, #6DA6B9, #04B698, #005C3E)
- Full chart palette + table specs: `design-tokens.json → outputFormats.documents`
- **Presentations**: Read `references/pptx-guide.md` for template-first approach

---

## Assets

| File | Use case |
|------|----------|
| `assets/worqx-logo.svg` | White text logo → dark backgrounds (header) |
| `assets/eblinqx-worqx-logo.svg` | Dark text logo → light backgrounds (login card) |
| `assets/icon.svg` | VX monogram → browser tab favicon |
| `assets/blinqx-logo.svg` | Hexagon + wordmark → general brand use |

Logo rules: min 24×24 (favicon), standard 124×40 (nav). Dark on light bg, white on dark bg. Never stretch. Place in `public/images/`, favicon at `public/icon.svg`.

The **yellow hexagonal chevron** (`#FFCD00`) is the shared Blinqx brand element across all products.
