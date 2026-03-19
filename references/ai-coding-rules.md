# Blinqx AI Coding Rules

> For AI code generators: v0, Claude Code, Cursor, Copilot, or any LLM generating Blinqx UI.
> Cursor users: copy to `.cursor/rules/blinqx.md` for automatic enforcement.

## 1. IDENTITY

Blinqx is a fintech UI library for Dutch mortgage advisors and homebuyers. 
- **NOT Blis Digital** (parent company, different brand)
- Never use Blis colors (#007776, #00CDB6)
- Tone: Trustworthy (financial decisions) ← → Approachable (not banking-sterile)
- Font: Metropolis UI (web/app), Inter (docs). Never Arial, Roboto, system fonts.

## 2. COLORS — COMPLETE PALETTE

### Core Palette
- **Text**: #1D2632 (navy) — ALWAYS. Never #000000.
- **Primary**: #6DA6B9 (B100) — buttons, links, focus, active tabs
- **CTA**: #FFCD00 (yellow) — exactly 1 per view MAXIMUM
- **Page bg**: #F4F7F9 | **Card bg**: #FFFFFF | **Header bg**: #E2EDF1
- **Border**: #C5DBE3 (B40) or #D3E4EA (B30 for shadcn)
- **Helper text**: #4A515B (gray)

### Status Colors (always use as pairs: bg + text)
- **Error**: bg #F6DEDE, text #951C1C (also for warnings)
- **Warning**: bg #EDBCBC, text #951C1C
- **Info**: bg #EFF2F7, text #316A7D
- **Success**: bg #CDF0EA, text #005C3E

### Forbidden Combinations
- Yellow text on white | White text on yellow (1.3:1 contrast — invisible)
- Blue (#6DA6B9) text on light bg (2.4:1 — too low)
- #000000, #007776, #00CDB6 anywhere

## 3. TYPOGRAPHY

### Type Scale (all in Inter or Metropolis UI)
- **H1**: 45px / 52px line-height, Medium (500)
- **H2**: 28px / 36px line-height, SemiBold (600)
- **H3**: 22px / 28px line-height, SemiBold (600)
- **Body L**: 16px / 24px line-height, Medium (500) or SemiBold (600)
- **Body M**: 14px / 20px line-height, Medium or SemiBold
- **Body S**: 12px / 16px line-height, Medium or SemiBold
- **Caption/Badge**: 11px / 16px line-height, Medium

### Weight Rules
- **Max weight: SemiBold (600)**. Never Bold (700) — too authoritarian.
- Hierarchy by size + color, NOT weight.
- Text always #1D2632 or #4A515B. Never colored body text.

## 4. COMPONENTS — DETAILED SPECS

### Button
- Shape: `rounded-full` (48px radius) ALWAYS — NEVER `rounded-md` or square
- States: enabled → hovered → focused → pressed → disabled
- Variant colors: primary #6DA6B9, CTA #FFCD00, outlined border-#C5DBE3
- Max 1 CTA (yellow) button per view
- Icon-only buttons: must have tooltip

### Input
- Border: **bottom-border ONLY**, never full box
- Background: #F4F7F9
- Border colors: #A5A8AD (default) → #4A515B (hover) → #6DA6B9 (focus) → #D15858 (error)
- Label: floating, moves from center to top on focus
- States: default → hover → focus → filled → error/disabled

### Card
- Background: #FFFFFF
- Radius: `rounded-xl` (16px)
- Shadow: `shadow-card` (subtle elevation)
- Title bar: H3, border-bottom #C5DBE3, padding 24px
- Content: padding 24px

### Modal / Dialog
- Background: #FFFFFF
- Radius: `rounded-xl`
- Overlay: `rgba(0,0,0,0.5)`
- Shadow: `shadow-popup` (heavy)
- Max width: 440px (login) or content-responsive
- Focus trap: enabled
- Close button: top-right (modal) or hidden (alert)

### Alert Dialog
- Icon circle (per status): error #F6DEDE with red icon, info #EFF2F7 with blue, etc.
- Title: H3, color #316A7D
- Buttons: max 2 (outlined left + filled right)
- No close button

### Tabs
- Active: `border-b-2 border-[#6da6b9]` — NOT bg change
- Inactive: transparent
- Text: Body M SemiBold, #1D2632
- Underline only, no background

### Switch
- ON state: track #6DA6B9 (B100), thumb white
- OFF state: border #C5DBE3, track transparent, thumb white

### Chip / Badge
- Shape: `rounded-full` (48px radius)
- Padding: 4px-8px (compact) or 8px-12px (medium)
- Colors: status color pair or #E2EDF1 bg + #1D2632 text
- Dismissible: optional X icon

### Message Bar
- Radius: `rounded-lg` (8px) — NOT `rounded-xl`
- Padding: 12px 16px
- Colors: status color pairs (bg + text)
- Icon: optional, left-aligned
- Dismissible: optional X icon

### Tooltip
- Background: #4A515B
- Text: white, Body S Medium
- Radius: `rounded` (4px)
- Padding: 6px 8px
- Appears on hover/focus, never on click

## 5. LAYOUT & SPACING

### Spacing Grid
All spacing: 4px multiples ONLY.
- 4px, 8px, 12px, 16px, 20px, 24px, 32px, 40px

### Navigation
- **Top bar OR sidebar — NEVER both**
- Sidebar: 80px dark (#1D2632), logo top, nav items with icons
- Top bar: 90px dark (#1D2632), logo left, nav items right
- Active item: #FFE680 background with #FFCD00 label
- Inactive: #D2D4D6 icon/label on transparent

### Content Area
- Page background: #F4F7F9
- Cards: white (#FFFFFF) with shadows
- Padding: 24px-40px depending on screen width
- Stack below 1024px (mobile-first responsive)

### Split Layouts
- 30-70 (sidepanel-main)
- 40-60 (sidebar-content)
- 50-50 (two panels)
- 70-30 (main-sidepanel)
- Below 1024px: stack vertically

## 6. STATES — 5 STATES FOR ALL INTERACTIVE ELEMENTS

Every interactive element (button, input, switch, chip, tab, card) must have:
1. **Enabled/Default** — normal state
2. **Hovered** — subtle bg shift or shadow lift (150ms transition)
3. **Focused** — 2px focus ring #6DA6B9 (accessible)
4. **Pressed/Active** — darker or emphasized variant
5. **Disabled** — gray text #D2D4D6, no cursor, opacity 0.6

Min touch target: **44×44px**. Transitions: **150ms ease**.

## 7. ACCESSIBILITY

- Min touch target: 44×44px (buttons, inputs, clickable areas)
- Focus rings: 2px solid #6DA6B9 on all interactive elements
- Color not sole indicator: always pair color with icon/text
- Contrast: min 4.5:1 for text (WCAG AA)
  - ✅ #1D2632 on #FFFFFF (12.8:1)
  - ✅ #1D2632 on #F4F7F9 (11.2:1)
  - ❌ #6DA6B9 on #F4F7F9 (2.4:1 — never for body text)
- ARIA roles: button, dialog, alert, tab, switch on all interactive elements
- Keyboard nav: Tab → focus visible, Enter/Space → activate
- Form labels: always explicit, never placeholders alone

## 8. shadcn/ui OVERRIDES

- `Button`: add `rounded-full`, primary uses primary blue not default
- `Input`: apply bottom-border pattern (custom, not stock shadcn)
- `Dialog`: add `rounded-xl`, shadow-popup, overlay rgba(0,0,0,0.5)
- `AlertDialog`: custom icon circle per status, H3 title #316A7D
- `Tabs`: active = `border-b-2 border-primary`, not bg change
- `Switch`: ON track primary blue, OFF border #C5DBE3
- `Badge`: use as chip with pill shape (48px radius) + status colors
- `Card`: add 16px radius, card shadow, no default border

## 9. CONTENT & LOCALE

- **Language**: Dutch (lang="nl")
- **Case**: sentence case (only first word capitalized, unless proper noun)
- **Button labels**: active verbs ("Opslaan", "Bewerken", "Verwijderen")
- **Error messages**: plain language, actionable ("Vul je e-mailadres in" not "Email invalid")
- **Decimals**: comma (1,50) not period (1.50) — Dutch locale
- **Dates**: DD-MM-YYYY or "15 maart 2026"

## 10. QUICK DECISION TREE FOR NEW ELEMENTS

1. **Is it clickable?** → Use `rounded-full` (button/chip) or `rounded-xl` (container)
2. **Does it contain data?** → White bg, `rounded-xl`, card shadow
3. **Is it status/feedback?** → Use status color pair (bg + text)
4. **Is it an overlay?** → White bg, `rounded-xl`, overlay #000 0.5, popup shadow
5. **Else?** → Navy text #1D2632 on white or light-blue bg, 16px radius if contained

---

**Version**: 2.0 | **Last updated**: 2026-03-19 | **Locale**: Dutch (NL)