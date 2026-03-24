# Blinqx Prototype Guide (React / Web / App)

> **Read this file when generating React, HTML, CSS, or Tailwind code for Blinqx.**
> Parent skill: `SKILL.md` — read that first for universal brand rules.
> Full token data: `../shared/design-tokens.json` · Full component specs: `components.json`
> This guide assumes **Next.js + shadcn/ui + Tailwind v4**. For other frameworks, apply the same design tokens and component specs but adapt the tooling.

---

## Prototype-Specific Rules

These rules apply to web/app prototypes only (not documents or presentations):
1. Buttons are **pill-shaped** (border-radius: 48px) — never square
2. Inputs have **bottom-border only** — never fully bordered boxes
3. Every interactive element needs **5 states**: enabled, hovered, focused, pressed, disabled
4. Font stack: `'Metropolis UI', 'Inter', Arial, sans-serif` via CSS `--font-sans`
5. Locale: Dutch (`lang="nl"`)

---

## Tech Stack

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

Full project setup: `project-setup-guide.md`
Full globals.css: `globals-css-template.md`
shadcn config: `shadcn-config-template.md`

---

## Color System

Full palette (8 families, 96 hex values) and 68 CSS custom properties (46 surface, 14 text, 7 border, 1 background): `../shared/design-tokens.json`

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

Color do's/don'ts, contrast ratios, forbidden combinations: → `../shared/brand-identity.md` §4

---

## Component Quick Reference

> Full specs + Figma links: `components.json` (Blinqx UI Kit — Style Guide)
> Copy-paste TSX examples for all components: `component-patterns.md`

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

---

## Layout Patterns

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
