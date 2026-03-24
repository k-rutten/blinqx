---
name: blinqx-brand
version: "3.1.0"
updated: "2026-03-24"
description: >
  Blinqx design system — colors, typography, spacing, component specs, and layout patterns.
  Use whenever generating output for the Blinqx product family (eBlinqx, WorQX, Blinqx portals).
  Trigger on: "Blinqx", "eBlinqx", "WorQX", "Blinqx style", "Blinqx design system", "Blinqx UI",
  "Blinqx huisstijl", "Blinqx branding", or Blinqx styleguide references.
  Blinqx is NOT Blis Digital — they share a parent company but have different brand identities.
  This skill OVERRIDES format-specific skills (pptx, docx, pdf, xlsx) for all visual choices
  (colors, fonts, spacing). The format skill handles file mechanics; this skill handles the look.
---

# Blinqx Design System

> **Figma**: [Style Guide](https://www.figma.com/design/F5hNn1cAwIeKGJgEFJV64q) · [WorQX reference](https://www.figma.com/design/fJfu8EJysRTl8XFsNyXUF3)

---

## Blinqx Identity

Blinqx is financial software for mortgage advisors and homebuyers (NL). The design balances **trustworthy** (biggest purchase of their lives) with **approachable** (not intimidating like a bank). Navy replaces harsh black, muted blue conveys calm expertise, pill buttons feel friendly.

**When in doubt:** Would a mortgage advisor show this to a client? Would a first-time homebuyer feel comfortable? Is there one clear CTA per view?

**Full design rationale, do's/don'ts, decision tree:** → `references/shared/brand-identity.md`

---

## How to Apply This Skill

**Step 1 — Read the right guide for your output format:**

| Creating... | Read this guide | Font |
|---|---|---|
| **pptx** | → `references/pptx-guide.md` | Metropolis (embedded in .potx template at `assets/Blinqx_Template-Basic.potx`) |
| **pdf / docx / xlsx** | → (use doc palette below) | Inter |
| **React / Next.js / HTML prototype** | → `references/prototype/guide.md` | Metropolis UI → Inter fallback |

**Step 2 — Universal rules (all formats):**
1. Text color: `#1D2632` (navy) — never pure `#000000` (exception: pptx dark slide backgrounds, see pptx-guide)
2. Max font weight: SemiBold (600) — never Bold (700)
3. Yellow (`#FFCD00`) is CTA-only — max 1 per view/slide/page
4. Never use Blis Digital colors (`#007776`, `#00CDB6`) — different brand
5. Never use yellow text on white or white text on yellow (1.3:1 contrast = invisible)

**Step 3 — Load reference files as needed:**

> **Auto-discovery**: The reference folders may contain files not listed below. Before starting work, scan `references/shared/`, `references/pptx/` (if making presentations), or `references/prototype/` (if making web/app) for any additional files. New reference files are added over time to improve output quality — always check what's available.

| File | When to load |
|------|-------------|
| `references/pptx-guide.md` | **Presentations** — template, layouts, build approach |
| `references/prototype/guide.md` | **Web/app** — tech stack, components, layout patterns |
| `references/shared/brand-identity.md` | Design rationale, do's/don'ts, decision tree |
| `references/shared/design-tokens.json` | Full token data (only when TLDR below is insufficient) |
| `references/prototype/components.json` | **Prototypes only** — Blinqx UI Kit from Style Guide Figma |
| `references/prototype/component-patterns.md` | Copy-paste TSX examples for 14 component types |
| `references/prototype/page-templates.md` | Page layout templates with breakpoints |
| `references/prototype/project-setup-guide.md` | Next.js + shadcn project scaffolding |
| `references/prototype/globals-css-template.md` | Complete `app/globals.css` with all CSS variables |
| `references/prototype/shadcn-config-template.md` | shadcn `components.json` + PostCSS config |
| `references/prototype/ai-coding-rules.md` | Rule set (~150 rules) for AI code generators |

> **Note**: The table above documents the core files. If you find additional `.md`, `.json`, or `.txt` files in any `references/` subfolder, read them — they contain relevant context for the task at hand.

---

## TLDR — Quick Reference

> **This section contains the most-used values. For most tasks, this is sufficient — only load `design-tokens.json` when you need the full 96-color palette or CSS variable mappings.**

### Colors
```
Primary:     #6DA6B9  (blue)     — buttons, links, focus, active switch
CTA/Accent:  #FFCD00  (yellow)   — max 1 CTA per view, active menu
Dark:        #1D2632  (navy)     — nav backgrounds, body text, headings
Page bg:     #F4F7F9  (light)    — app/page background
Card bg:     #FFFFFF  (white)    — all cards, panels
Header bg:   #E2EDF1  (blue-20)  — page headers, table header rows
Border:      #C5DBE3  (blue-40)  — dividers, outlines, table borders
Help text:   #4A515B  (neutral)  — secondary text, tooltips
Placeholder: #777D84             — input placeholders
Error:       #D15858  (red)      — error states, destructive
Success:     #04B698  (green)    — positive states
Warning:     #FFA652  (orange)   — attention needed
```

### Typography
```
pptx presentations:  Metropolis (embedded in .potx template)
pdf / docx / xlsx:   Inter (Metropolis not embeddable)
web / app:           'Metropolis UI', 'Inter', Arial, sans-serif

H1:     45px / 52px / Medium 500   — page titles
H2:     28px / 36px / SemiBold 600 — section headings
H3:     22px / 28px / SemiBold 600 — card/modal titles
Body L: 16px / 24px / Medium 500   — body text, inputs
Body M: 14px / 20px / SemiBold 600 — buttons, tabs, emphasis
Body S: 12px / 16px / Medium 500   — captions, menu labels
```

### Layout
```
Spacing:     4px base (4, 8, 12, 16, 20, 24, 32, 40)
Radius:      16px cards/headers, 8px message bars, 4px tooltips, 48px buttons (pill)
Shadows:     card (resting), hovered (interactive), popup (overlay)
Charts:      teal/green palette: #CDF0EA → #6DA6B9 → #04B698 → #005C3E
```

---

## Document Styling (pdf, docx, xlsx)

> For presentations (.pptx), skip this section — read `references/pptx-guide.md` instead.

### Document Typography

| Element | Font | Weight | Size |
|---------|------|--------|------|
| Heading | Inter | SemiBold (600) | 20-24pt |
| Body text | Inter | Medium (500) | 12-16pt |
| Caption | Inter | Regular (400) | 10-12pt |
| Table header | Inter | SemiBold (600) | 11-14pt |
| Table cell | Inter | Regular (400) | 10-12pt |

### Document Rules

- Max 3 colors per page: text + accent + 1 status color
- Max 1 yellow highlight per page
- Table header rows: bg `#E2EDF1`, alt rows: `#F4F7F9`
- Chart colors (in order): `#CDF0EA`, `#6DA6B9`, `#04B698`, `#005C3E`

---

## Assets

| File | Use case |
|------|----------|
| `assets/Blinqx_Template-Basic.potx` | **PowerPoint template** — 41 slides, 87 layouts. Always use for pptx |
| `assets/blinqx-logo.svg` | Hexagon + wordmark → general brand use |
| `assets/worqx-logo.svg` | White text logo → dark backgrounds (header) |
| `assets/eblinqx-worqx-logo.svg` | Dark text logo → light backgrounds (login card) |
| `assets/icon.svg` | VX monogram → browser tab favicon |

Logo rules: min 24×24 (favicon), standard 124×40 (nav). Dark on light bg, white on dark bg. Never stretch.

The **yellow hexagonal chevron** (`#FFCD00`) is the shared Blinqx brand element across all products.
