# Blinqx Presentation Guide (pptx)

> **Read this file when creating or editing PowerPoint presentations.**
> Parent skill: `SKILL.md` — read that first for universal brand rules.
> Template file: `assets/Blinqx_Template-Basic.potx` (41 example slides, 87 layouts)
> This skill OVERRIDES the system pptx skill for visual choices. The system skill handles python-pptx mechanics; this guide handles the Blinqx look.
> **Auto-discovery**: Check `references/shared/` and the `assets/` folder for any additional reference files not listed here — new resources are added over time.

---

## Presentation Design Language (from official Blinqx_Template-Basic.potx)

> **CRITICAL**: Always build presentations FROM the .potx template (`assets/Blinqx_Template-Basic.potx`), never recreate slides from scratch.
> Use python-pptx to load it, select slides, and fill placeholders.

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

### Design Principles

1. **Alternate themes** — don't use the same background for consecutive slides
2. **Yellow = emphasis** — use yellow bg or elements to highlight the most important slides
3. **Hexagons everywhere** — use the hexagon shape as icon container, decorative element, or visual motif
4. **Large typography** — titles are oversized (60pt) for impact
5. **Minimal text per slide** — body text is secondary, visuals and headings carry the message
6. **Photo placeholders = crosshatch hexagons** — diagonal-line patterns in the template are photo slots
7. **Green for data** — charts use teal/green palette, NOT the primary blue

---

## Template: Layout Catalog & Build Approach

> **Always build from the .potx template** using python-pptx. Never recreate slides from scratch.

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
