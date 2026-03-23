# Blinqx Page Templates

Locked page layouts for the Blinqx product family. Two shell patterns exist:
- **Top Nav Shell** (WorQX production) — horizontal nav bar, used for most app pages
- **Sidebar Shell** (style guide) — vertical sidebar, used for admin/settings views

---

## 1. App Shells

### 1A. Top Nav Shell (WorQX — primary)

```
┌──────────────────────────────────────────────────┐
│ [Logo 124×40] [Nav items] [Org picker] [User]    │  90px
├──────────────────────────────────────────────────┤
│  ←140px→  ┌────────────────────┐  ←140px→        │
│           │  Content area      │                 │
│           │  1120px wide       │                 │
│           │  bg: #F4F7F9       │                 │
│           └────────────────────┘                 │
└──────────────────────────────────────────────────┘
Viewport: 1400px, nav: #1D2632 dark, content margins: 140px
```

- **Nav bar**: 1400×90px, dark bg `N100`, logo left, nav center, user right
- **Content**: 1120px wide, centered, `bg L20`
- **Section pattern**: heading text + white card below (30px card padding)

### 1B. Sidebar Shell (Admin/Settings)

```
┌──────┬──────────────────────────────────────────┐
│ Side │  [Header]                                │
│ bar  ├──────────────────────────────────────────┤
│ 80px │  [Content Area]                          │
│ N100 │  bg: L20 (#F4F7F9)                      │
│      │  padding: 24px                           │
└──────┴──────────────────────────────────────────┘
```

- **Sidebar**: fixed, 80px, `N100` dark, `100vh`
- **Content area**: `flex-1`, `overflow-auto`, bg `L20`
- **Header**: inside content area, `rounded-16px`, bg `B20`

---

## 2. Dashboard Page

```
┌──────┬──────────────────────────────────────────┐
│      │  Header: "Dashboard"  [+ actions]        │
│ Side │  ─ Tab bar (optional) ──────────────     │
│ bar  ├──────────────────────────────────────────┤
│      │  ┌─────────┐ ┌─────────┐ ┌─────────┐   │
│      │  │ KPI Card│ │ KPI Card│ │ KPI Card│   │
│      │  └─────────┘ └─────────┘ └─────────┘   │
│      │  ┌──────────────────┐ ┌──────────────┐  │
│      │  │ Chart / Table    │ │ Side widget  │  │
│      │  │ (70%)            │ │ (30%)        │  │
│      │  └──────────────────┘ └──────────────┘  │
└──────┴──────────────────────────────────────────┘
```

**Specs:**
- KPI cards: 3-column grid, `gap-16px`, each card `bg W100`, `rounded-16px`, `shadow-card`
- Main content: 70-30 split below KPI row
- Cards: `padding 24px`, title in `Body M SemiBold`

**Responsive:**
- `≥1024px`: 3 columns KPI, 70-30 split
- `768–1023px`: 2 columns KPI, stack main/side vertically
- `<768px`: 1 column, all stacked

---

## 3. List / Table Page

```
┌──────┬──────────────────────────────────────────┐
│      │  Header: "Items"  [+ New Item]           │
│ Side │  ─ Tab bar ─────────────────────────     │
│ bar  ├──────────────────────────────────────────┤
│      │  [Search] [Filter] [Sort]                │
│      │  ┌──────────────────────────────────┐    │
│      │  │ Table / List                     │    │
│      │  │ row: bg W100, hover bg L20       │    │
│      │  │ header: bg B20, text N100        │    │
│      │  │ border-bottom: B40              │    │
│      │  └──────────────────────────────────┘    │
│      │  [Pagination]                            │
└──────┴──────────────────────────────────────────┘
```

**Specs:**
- Filter bar: `gap-8px`, aligned left, full width
- Table: `bg W100`, `rounded-16px`, `shadow-card`
- Table header: `bg B20`, `Body M SemiBold`, `text N100`
- Table rows: `Body M Medium`, `border-bottom 1px B40`
- Row hover: `bg L20`
- Pagination: bottom-right, `gap-8px`

**Responsive:**
- `≥1024px`: Full table with all columns
- `768–1023px`: Hide non-essential columns, show on expand
- `<768px`: Card-based list view instead of table

---

## 4. Detail Page (with Side Panel)

```
┌──────┬──────────────────────────────────────────┐
│      │  Header: "Item Name"  [Edit] [Delete]    │
│ Side ├──────────────────────────────────────────┤
│ bar  │  ┌───────────────────┐ ┌────────────┐   │
│      │  │ Main content      │ │ Side panel │   │
│      │  │ 60-70%            │ │ 30-40%     │   │
│      │  │                   │ │            │   │
│      │  │ Form / Details    │ │ Info /     │   │
│      │  │                   │ │ Related    │   │
│      │  └───────────────────┘ └────────────┘   │
└──────┴──────────────────────────────────────────┘
```

**Split ratios** (use Figma-defined ratios):
- `70-30`: Default for detail + metadata panel
- `60-40`: For balanced content + context panel
- `50-50`: For comparison views

**Specs:**
- Main content: `bg W100`, `rounded-16px`, `shadow-card`, `padding 24px`
- Side panel: `bg W100`, `rounded-16px`, `shadow-card`, `padding 24px`
- Gap between panels: `16px`

**Responsive:**
- `≥1024px`: Side-by-side
- `<1024px`: Stack vertically, side panel below

---

## 5. Form Page

```
┌──────┬──────────────────────────────────────────┐
│      │  Header: "Create Item"  [Cancel] [Save]  │
│ Side ├──────────────────────────────────────────┤
│ bar  │  ┌──────────────────────────────────┐    │
│      │  │ Form card                        │    │
│      │  │ max-width: 640px                 │    │
│      │  │ center-aligned                   │    │
│      │  │                                  │    │
│      │  │ [Section title - H3]             │    │
│      │  │ [Input] [Input]                  │    │
│      │  │ [Input] [Input]                  │    │
│      │  │ [Section title - H3]             │    │
│      │  │ [Input] [Input]                  │    │
│      │  └──────────────────────────────────┘    │
└──────┴──────────────────────────────────────────┘
```

**Specs:**
- Form card: `bg W100`, `rounded-16px`, `shadow-card`, `max-width 640px`, centered
- Section titles: `H3` (22px/28px SemiBold), `text B120`, `margin-bottom 16px`
- Input grid: 2-column, `gap-16px` horizontal, `gap-24px` vertical
- CTA button (Save): `Y100`, right-aligned in header
- Cancel button: `W100` outlined, left of Save

**Responsive:**
- `≥768px`: 2-column input grid
- `<768px`: 1-column, full-width inputs

---

## 6. Login Page

```
┌──────────────────────────────────────────────────┐
│                                                  │
│  ┌────────────────────┐  ┌───────────────────┐  │
│  │                    │  │                   │  │
│  │  Background image  │  │  Login card       │  │
│  │  or brand visual   │  │  bg: W100         │  │
│  │  50-60%            │  │  rounded-16px     │  │
│  │                    │  │  shadow-card      │  │
│  │                    │  │  max-w: 440px     │  │
│  │                    │  │                   │  │
│  │                    │  │  [Logo]           │  │
│  │                    │  │  [Title]          │  │
│  │                    │  │  [Email input]    │  │
│  │                    │  │  [Password input] │  │
│  │                    │  │  [CTA Button]     │  │
│  │                    │  │                   │  │
│  └────────────────────┘  └───────────────────┘  │
│                                                  │
└──────────────────────────────────────────────────┘
```

**Note**: Login page does NOT use the sidebar — it's a standalone fullscreen layout.

**Specs:**
- Full viewport height, `bg L20`
- Left side: brand image or gradient, 50-60% width
- Right side: centered login card
- Login card: `bg W100`, `rounded-16px`, `shadow-card`, `padding 40px`, `max-width 440px`
- Logo: `40×40px`, centered, `margin-bottom 32px`
- Title: `H1`, `text N100`
- Inputs: floating label, full width
- CTA: `Y100` filled, full width, `margin-top 24px`

**Responsive:**
- `≥768px`: Side-by-side split
- `<768px`: Image hidden, login card full-width centered

---

## 7. Settings Page

```
┌──────┬──────────────────────────────────────────┐
│      │  Header: "Settings"                      │
│ Side │  ─ Tab bar (sections) ──────────────     │
│ bar  ├──────────────────────────────────────────┤
│      │  ┌──────────────────────────────────┐    │
│      │  │ Settings section card            │    │
│      │  │ max-width: 720px                 │    │
│      │  │                                  │    │
│      │  │ [Switch] [Label]                 │    │
│      │  │ [Switch] [Label]                 │    │
│      │  │ [Input]  [Input]                 │    │
│      │  │                                  │    │
│      │  │             [Save]               │    │
│      │  └──────────────────────────────────┘    │
└──────┴──────────────────────────────────────────┘
```

**Specs:**
- Tabs for section navigation (Profile, Notifications, Security, etc.)
- Settings card: `bg W100`, `rounded-16px`, `max-width 720px`
- Settings rows: `padding-y 16px`, `border-bottom 1px B40`
- Switch + label on same row: `flex justify-between`
- Save button: `Y100`, bottom-right of card

---

## 8. Error Page

```
┌──────────────────────────────────────────────────┐
│                                                  │
│              [Hexagon icon - large]              │
│              [Error code - H1]                   │
│              [Message - Body L]                  │
│              [CTA Button]                        │
│                                                  │
└──────────────────────────────────────────────────┘
```

**Specs:**
- Fullscreen, centered content, `bg L20`
- Hexagon icon: 80×80px, `bg R20`, icon `R100`
- Error code: `H1`, `text N100`
- Message: `Body L Medium`, `text N80`
- CTA: `B100` filled, navigates home

---

## 9. WorQX Home Page (reference implementation)

```
┌──────────────────────────────────────────────────┐
│  Nav bar (90px)                                  │
├──────────────────────────────────────────────────┤
│                                                  │
│  "Jouw apps"                  "Vraag 't Quinn"   │
│  ┌────────────────────────┐  ┌──────────────┐   │
│  │ App tiles (4-col grid) │  │ AI widget    │   │
│  │ 740px                  │  │ 360px        │   │
│  └────────────────────────┘  └──────────────┘   │
│                                                  │
│  "Vakgebied"   "Sneller met AI"   "Recent"       │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐      │
│  │ 360px    │  │ 360px    │  │ 360px    │      │
│  └──────────┘  └──────────┘  └──────────┘      │
│                                                  │
└──────────────────────────────────────────────────┘
```

**Row 1**: 2:1 ratio (740px + 360px), gap 20px
**Row 2**: 3-equal columns (360px each), gap 20px
**Section pattern**: heading text (15px) → 45px gap → white card

---

## Breakpoint Reference

| Name | Min-width | Nav | Content width | Layout |
|------|-----------|-----|--------------|--------|
| Mobile | 0 | Hamburger menu, 390×70px | 350px (20px margins) | Single column |
| Tablet | 768px | Horizontal, compressed | 680px | 2 columns |
| Desktop | 1024px | Full horizontal nav | 900px | Multi-column |
| Wide (WorQX) | 1400px | Full nav, 90px height | 1120px (140px margins) | Full layout |
