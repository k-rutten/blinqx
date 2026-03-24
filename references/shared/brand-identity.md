# Blinqx Brand Identity & Huisstijl

Dit document beschrijft de visuele identiteit van Blinqx: de principes achter het ontwerp, welke combinaties van kleuren en typografie zijn toegestaan, en hoe AI tools beslissingen moeten nemen bij het genereren van Blinqx-output.

---

## 1. Wie is Blinqx?

Blinqx maakt financiële software voor hypotheekadviseurs en woningkopers in Nederland. Producten zijn onder andere eBlinqx (het hypotheekplatform), WorQX (het werkplatform voor adviseurs), en diverse Blinqx-portalen.

**Blinqx is NIET Blis Digital.** Blis Digital is het moederbedrijf (een tech consultancy). Ze delen een parent company maar hebben volledig verschillende visuele identiteiten. Gebruik nooit Blis-kleuren (#007776, #00CDB6) in Blinqx-context.

---

## 2. Merkpersoonlijkheid

Blinqx zit op het snijvlak van twee werelden:

```
VERTROUWENWEKKEND ←———————→ BENADERBAAR
(financiële beslissingen)    (geen bankgevoel)
```

Elke ontwerpkeuze dient deze balans:

| Te zakelijk (vermijden) | Blinqx (het juiste midden) | Te speels (vermijden) |
|---|---|---|
| Puur zwart (#000000) | Navy (#1D2632) — warm, professioneel | Felle primaire kleuren |
| Scherpe hoeken op alles | 16px radius containers, pill buttons | Volledig ronde containers |
| Zwaar Bold (700) typografie | SemiBold (600) max — rustig gezag | Dunne Light (300) typografie |
| Gesatureerd blauw (#0000FF) | Gedempt teal-blauw (#6DA6B9) | Felroze of neonkleuren |
| Volledig omrande input boxes | Bottom-border only inputs | Borderless inputs |
| Grijze, klinische interface | Blauw-warm kleurenpalet | Kleurrijke, drukke interface |

**De toontest:** Als een hypotheekadviseur dit aan een klant laat zien, voelt het dan professioneel genoeg? En voelt een starter op de woningmarkt zich er comfortabel bij?

---

## 3. Design Principes

### Principe 1: Professioneel maar niet zakelijk
Navy in plaats van zwart. Gedempt blauw in plaats van gesatureerd. SemiBold in plaats van Bold. Alles een fractie zachter dan je bij een bank zou verwachten.

### Principe 2: Vriendelijk maar niet speels
Pill-buttons en afgeronde containers geven een toegankelijk gevoel. Maar gestructureerde layouts met duidelijke hiërarchie houden het serieus — dit gaat om hypotheken, niet om een spelletje.

### Principe 3: Rustige expertise
Het "vertrouwde adviseur" gevoel. Niet agressief verkoopachtig, niet steriel bankachtig. De kleur teal-blauw (#6DA6B9) is bewust gekozen: kalm, betrouwbaar, deskundig.

### Principe 4: Data-first
Minimale chrome. Bottom-border inputs. Ruime spacing. Hiërarchie door grootte en kleur, niet door gewicht. Bij formulieren met 20+ velden (hypotheekaanvragen) moet de data centraal staan, niet de interface-elementen.

### Principe 5: Eén stem
Maximaal 1 CTA (geel) per scherm. Consistente statuspatronen. Nooit meer dan 2 buttonstijlen in één actiegroep. Duidelijke visuele hiërarchie bij elk scherm.

---

## 4. Kleurgebruik — Wat mag wel en niet

### 4.1 Kernkleuren en hun rol

| Kleur | Hex | Wanneer gebruiken | Wanneer NIET gebruiken |
|---|---|---|---|
| **Navy** | `#1D2632` | Alle tekst, sidebar achtergrond, donkere surfaces | Nooit als achtergrond voor lichte tekst (behalve nav) |
| **Teal-blauw** | `#6DA6B9` | Primaire acties, links, focus states, actieve switch, tabs | Nooit als tekstkleur op lichte achtergrond (te laag contrast) |
| **Geel** | `#FFCD00` | CTA button (max 1 per view), actief menu-item, hexagon logo | Nooit als tekst, nooit op wit (onleesbaar), nooit meer dan 1x |
| **Pagina-achtergrond** | `#F4F7F9` | App-achtergrond, input achtergrond | Nooit als kaart-achtergrond (dat is wit) |
| **Wit** | `#FFFFFF` | Kaarten, panels, modals, popovers | — |
| **Header-blauw** | `#E2EDF1` | Pagina-headers, tabelkoppen, surface-level-1 | Nooit als tekst |
| **Border** | `#C5DBE3` | Scheidingslijnen, kaartranden, chipborders | — |
| **Hulptekst** | `#4A515B` | Secundaire tekst, tooltips, caption | Nooit als primaire body tekst |
| **Rood** | `#D15858` | Fouten, destructieve acties | Nooit decoratief |
| **Groen** | `#04B698` | Successtatus, positieve indicatoren | Nooit decoratief |
| **Oranje** | `#FFA652` | Waarschuwingen, aandacht nodig | Nooit decoratief |

### 4.2 Toegestane kleurcombinaties

**Tekst op achtergrond:**

| Combinatie | Contrast | Gebruik |
|---|---|---|
| `#1D2632` op `#FFFFFF` | 12.8:1 ✅ | Standaard body tekst |
| `#1D2632` op `#F4F7F9` | 11.2:1 ✅ | Tekst op pagina-achtergrond |
| `#1D2632` op `#E2EDF1` | 9.4:1 ✅ | Tekst in headers |
| `#1D2632` op `#FFCD00` | 8.9:1 ✅ | Tekst op CTA buttons |
| `#4A515B` op `#FFFFFF` | 6.2:1 ✅ | Hulptekst, captions |
| `#FFFFFF` op `#1D2632` | 12.8:1 ✅ | Tekst in donkere navigatie |

**Statuskleuren (altijd als paar gebruiken):**

| Status | Achtergrond | Tekst | Wanneer |
|---|---|---|---|
| Waarschuwing | `#EDBCBC` | `#951C1C` | Aandacht vereist, niet-kritieke fouten |
| Informatie | `#EFF2F7` | `#316A7D` | Informatieve berichten, tips |
| Succes | `#CDF0EA` | `#005C3E` | Bevestigingen, positieve feedback |
| Fout | `#F6DEDE` | `#951C1C` | Validatiefouten, kritieke waarschuwingen |

### 4.3 Verboden combinaties

| Combinatie | Waarom niet |
|---|---|
| Geel tekst op wit | 1.3:1 contrast — onleesbaar |
| Wit tekst op geel | 1.3:1 contrast — onleesbaar |
| Blauw (#6DA6B9) tekst op licht (#F4F7F9) | 2.4:1 — te laag voor body tekst |
| Zwart (#000000) waar dan ook | Niet in het palet — gebruik navy #1D2632 |
| Blis-kleuren (#007776, #00CDB6) | Ander merk — nooit in Blinqx context |
| Disabled tekst (#D2D4D6) op wit | 1.5:1 — onleesbaar (maar OK voor disabled state) |

### 4.4 Kleurgebruik per context

**Navigatie (donker thema):**
```
Achtergrond: #1D2632 (navy)
Actief item: gele achtergrond #FFE680, donker icoon, geel label #FFCD00
Geselecteerd: #343C47 achtergrond, wit icoon/label
Inactief: transparant, lichtgrijs (#D2D4D6) icoon/label
```

**Content area (licht thema):**
```
Pagina: #F4F7F9 achtergrond
Kaarten: wit (#FFFFFF) met shadow, 16px radius
Headers: #E2EDF1 achtergrond, 16px radius
Borders: #C5DBE3 voor scheiding
```

**Formulieren:**
```
Input achtergrond: #F4F7F9
Border: alleen onderaan — #A5A8AD (default), #4A515B (hover), #6DA6B9 (focus), #D15858 (error)
Label: zweeft van midden naar boven bij focus
```

---

## 5. Typografie — Wat mag wel en niet

### 5.1 Fonts

| Context | Font | Waarom |
|---|---|---|
| **Prototypes (web/app)** | Metropolis UI, fallback Inter | Metropolis is het officiële merkletter. Inter is visueel vergelijkbaar. |
| **Documenten (pptx/pdf/docx)** | Inter | Metropolis UI is niet beschikbaar in Office/PDF omgevingen. |
| **Nooit** | Arial, Roboto, system fonts als primair | Te generiek — geven geen merkidentiteit weer. |

### 5.2 Gewichten

| Gewicht | Naam | Gebruik | Nooit |
|---|---|---|---|
| 400 | Regular | Alleen in documenten (caption, tabelcel) | Nooit in prototypes als primair gewicht |
| 500 | Medium | Body tekst, inputwaarden, H1 | — |
| 600 | SemiBold | Buttons, tabs, koppen H2/H3, emphasis | — |
| 700 | Bold | **NOOIT GEBRUIKEN** | Altijd — te zwaar voor Blinqx-toon |

**Waarom geen Bold?** Metropolis UI in Bold wordt te autoritair. SemiBold geeft nadruk zonder te schreeuwen. De huisstijl creëert hiërarchie door grootte en kleur, niet door gewicht.

### 5.3 Toegestane type-combinaties

| Element | Stijl | Grootte | Regelhoogte | Kleur |
|---|---|---|---|---|
| Paginatitel | H1 Medium | 45px | 52px | `#1D2632` |
| Sectiekop | H2 SemiBold | 28px | 36px | `#1D2632` |
| Kaarttitel / modaltitel | H3 SemiBold | 22px | 28px | `#316A7D` (alerts) of `#1D2632` |
| Body tekst | Body L Medium | 16px | 24px | `#1D2632` |
| Body emphasis | Body L SemiBold | 16px | 24px | `#1D2632` |
| Buttons / tabs / labels | Body M SemiBold | 14px | 20px | Afhankelijk van component |
| Secundaire tekst | Body M Medium | 14px | 20px | `#4A515B` of `#1D2632` |
| Captions / chips / tooltips | Body S Medium | 12px | 16px | Context-afhankelijk |
| Menu-labels | Body S SemiBold | 12px | 16px | `#D2D4D6` (inactief) of `#FFCD00` (actief) |
| Badge counts | Badge Medium | 11px | 16px | `#951C1C` op `#EDBCBC` |

### 5.4 Verboden type-combinaties

- Body tekst kleiner dan 12px (behalve badges op 11px)
- Heading in Regular (400) gewicht
- Meer dan 2 verschillende groottes op één kaart
- Vetgedrukt (700) waar dan ook
- Gekleurde body tekst (body is altijd navy of hulpgrijs)
- HOOFDLETTERS voor lopende tekst (alleen OK voor korte labels)

---

## 6. Component-principes

### 6.1 Vormentaal

| Element | Radius | Waarom |
|---|---|---|
| Buttons, chips, badges | 48px (pill) | Vriendelijk, benaderbaar — signaleert "geen bank" |
| Kaarten, headers, modals, panels | 16px | Warm maar gestructureerd — professioneel maar niet hard |
| Message bars | 8px | Functioneel element, minder aandacht dan kaarten |
| Segmented controls, pull-down items | 8px | Subtiel, nested binnen grotere containers |
| Tooltips | 4px | Klein element, minimale afronding volstaat |
| Circulaire elementen (avatars, badges) | 9999px | Volledig rond voor profielfoto's en tellers |

### 6.2 Schaduwen en diepte

| Niveau | Gebruik | Visueel effect |
|---|---|---|
| **Card** (licht) | Kaarten, panels — rustende staat | Subtiele diepte, scheidt content van achtergrond |
| **Hovered** (medium) | Tooltips, hover op kaarten | Licht verhoogd, interactie-feedback |
| **Popup** (zwaar) | Modals, alerts, dropdowns, date pickers | Duidelijke overlay, trekt aandacht |

Gebruik nooit willekeurige CSS-schaduwen. Alleen deze drie niveaus.

### 6.3 Spacing-principes

Alle spacing is een veelvoud van 4px. Geen uitzonderingen.

| Veelvoud | px | Typisch gebruik |
|---|---|---|
| 1× | 4px | Badge padding, compacte gaps |
| 2× | 8px | Icoon-label gaps, dropdown items |
| 3× | 12px | Menu-items, tab bovenkant |
| 4× | 16px | Component padding, standaard gaps |
| 5× | 20px | Logo padding, medium button padding |
| 6× | 24px | Header/kaart/modal padding |
| 8× | 32px | Sectie-scheiding |
| 10× | 40px | Header linkerzijde padding |

---

## 7. Beslisboom voor nieuwe elementen

Wanneer je een element moet stylen dat niet expliciet in het design system staat:

```
1. Is het interactief (klikbaar/tappable)?
   JA → Pill-vorm (radius 48px) als het een actie-element is (button, chip)
   JA → 16px radius als het een container is (kaart, panel, dropdown)
   NEE → Ga naar stap 2

2. Bevat het data/content?
   JA → Wit (#FFFFFF) achtergrond, 16px radius, card shadow
   NEE → Ga naar stap 3

3. Is het een status/feedback element?
   JA → Gebruik statuskleurenpaar (achtergrond + tekst uit sectie 4.2)
   NEE → Ga naar stap 4

4. Is het een overlay/popup?
   JA → Wit achtergrond, 16px radius, popup shadow, rgba(0,0,0,0.5) overlay
   NEE → Ga naar stap 5

5. Is het decoratief/visueel?
   JA → Gebruik accent blauw (#6DA6B9) of geel (#FFCD00) spaarzaam
   NEE → Standaard: navy tekst (#1D2632) op witte of lichtblauwe achtergrond
```

---

## 8. Logo en beeldmerk

Het Blinqx-beeldmerk is een **gele hexagonale chevron** (`#FFCD00`). Dit is het gedeelde visuele element across alle Blinqx-producten.

| Variant | Bestand | Gebruik |
|---|---|---|
| Wit tekst-logo | `assets/worqx-logo.svg` | Donkere achtergronden (navigatie header) |
| Donker tekst-logo | `assets/eblinqx-worqx-logo.svg` | Lichte achtergronden (login kaart) |
| Monogram favicon | `assets/icon.svg` | Browser tab icoon |

**Regels:**
- Minimaal 24×24px (favicon), standaard 124×40px (navigatie)
- Op donkere achtergrond: wit logo-variant
- Op lichte achtergrond: donker logo-variant
- Bewaar beeldverhouding — nooit uitrekken
- Minimale vrije ruimte rondom: 12px

Elk nieuw Blinqx-product krijgt een eigen productlogo, maar de gele hexagonale chevron is universeel.

---

## 9. Wat Blinqx NIET is

| Blinqx is NIET... | Omdat... |
|---|---|
| Blis Digital | Ander merk, andere kleuren (#007776, #00CDB6), andere fonts (Mont, Inter Light) |
| Een banking app | Geen steriel grijs, geen gesatureerd blauw, geen scherpe hoeken |
| Een consumer app | Geen felle kleuren, geen speelse animaties, geen casual typografie |
| Een dashboard tool | Geen data-overload, geen minimale spacing, geen compacte tabellen |

Blinqx is financiële software die eruitziet als een vertrouwde adviseur: professioneel, kalm, en toegankelijk.

---

## 10. Visuele Do's & Don'ts — Alles op één plek

### ✅ DO

| Categorie | Regel |
|---|---|
| **Kleuren** | Gebruik `#1D2632` voor alle tekst — nooit `#000000` |
| **Kleuren** | Gebruik statuskleurenparen (donkere tekst op lichte achtergrond) |
| **Kleuren** | Maximaal 1 geel (`#FFCD00`) CTA-element per scherm |
| **Kleuren** | Maximaal 3 kleuren per slide: tekst + accent + 1 statuskleur |
| **Typografie** | Gebruik Metropolis UI (proto) of Inter (docs) — nooit Arial/Roboto |
| **Typografie** | Maximaal SemiBold (600) gewicht |
| **Typografie** | Creëer hiërarchie door grootte en kleur, niet door gewicht |
| **Componenten** | Pill-vormige buttons (radius 48px) |
| **Componenten** | Bottom-border-only inputs met floating labels |
| **Componenten** | 16px radius op alle containers (kaarten, modals, headers) |
| **Componenten** | Elke interactieve element: 5 states (enabled→disabled) |
| **Layout** | Consistent navigatiepatroon (top bar ÓF sidebar, nooit beide) |
| **Layout** | Card shadow voor kaarten, popup shadow voor overlays |
| **Layout** | Alle spacing in veelvouden van 4px |
| **Layout** | Stack layouts onder 1024px breedte |

### ❌ DON'T

| Categorie | Regel | Waarom |
|---|---|---|
| **Kleuren** | `#000000` gebruiken | Te hard — gebruik navy `#1D2632` |
| **Kleuren** | `#007776` of `#00CDB6` gebruiken | Blis Digital merk — ander merk |
| **Kleuren** | Geel tekst op wit, wit tekst op geel | 1.3:1 contrast — onleesbaar |
| **Kleuren** | Blauw (`#6DA6B9`) als body tekst op licht | 2.4:1 contrast — te laag |
| **Kleuren** | Statuskleur als decoratie gebruiken | Verwarrend — rood = altijd fout, groen = altijd goed |
| **Typografie** | Bold (700) gebruiken, waar dan ook | Te zwaar voor Blinqx-toon |
| **Typografie** | Body tekst kleiner dan 12px | Onleesbaar (behalve badges 11px) |
| **Typografie** | Meer dan 2 tekstgroottes per kaart | Te druk — bewaar hiërarchie |
| **Typografie** | HOOFDLETTERS voor lopende tekst | Alleen OK voor korte labels |
| **Componenten** | Vierkante buttons (radius < 48px) | Voelt te zakelijk/enterprise |
| **Componenten** | Volledig omrande input boxes | Te veel visuele ruis bij 20+ velden |
| **Componenten** | Kaart in kaart zonder visuele scheiding | Geen diepte — gebruik shadow of ruimte |
| **Componenten** | Icon-buttons zonder tooltip | Gebruiker weet niet wat het doet |
| **Componenten** | Meer dan 2 buttonstijlen in één actiegroep | Verwarrend — kies primary + outlined |
| **Layout** | Top bar EN sidebar tegelijk | Kies één navigatiepatroon |
| **Layout** | Scherpe hoeken op containers | Voelt te rigide voor Blinqx-toon |
| **Layout** | Willekeurige CSS shadows | Alleen card/hovered/popup — nooit iets anders |

---

## 11. UX Scherm-compositie — Welk component waar

Dit beschrijft hoe Blinqx-schermen zijn opgebouwd. Gebruik dit bij het ontwerpen van nieuwe pagina's.

### 11.1 Anatomie van een Blinqx pagina

```
┌─────────────────────────────────────────────────────────┐
│ NAVIGATIE                                                │
│ (sidebar 80px donker OF top bar 90px donker)             │
├─────────────────────────────────────────────────────────┤
│ HEADER                                                   │
│ bg: #E2EDF1, radius 16px                                │
│ [H1 titel] [actiebuttons rechts] [tabs onderaan]         │
├─────────────────────────────────────────────────────────┤
│ CONTENT AREA (bg: #F4F7F9)                              │
│                                                          │
│ ┌─────────────────────────────────────────────────────┐ │
│ │ KAART (bg: wit, radius 16px, shadow card)           │ │
│ │ [Titelbalk met border-bottom]                       │ │
│ │ [Content: tabellen, formulieren, lijsten]            │ │
│ │ [Actiebalk onderaan (optioneel)]                    │ │
│ └─────────────────────────────────────────────────────┘ │
│                                                          │
│ ┌──────────────────────┐ ┌────────────────────────────┐ │
│ │ KAART 70%            │ │ SIDEPANEL 30%              │ │
│ │ Hoofdcontent         │ │ bg: wit, radius 16px       │ │
│ │                      │ │ Metadata, samenvatting     │ │
│ └──────────────────────┘ └────────────────────────────┘ │
└─────────────────────────────────────────────────────────┘
```

### 11.2 Schermtypes en hun componenten

**Dashboard / Overzicht:**
```
Header (met tabs voor secties)
├── KPI-kaarten (3-koloms grid)
├── Hoofdkaart 70% (tabel of lijst)
└── Sidepanel 30% (filters, samenvatting)
```
Componenten: header, tab, card, chip (statuslabels), pagination

**Lijstweergave / Tabel:**
```
Header (titel + actiebuttons)
├── Toolbar (search bar + filter chips + sorteer)
└── Tabelkaart (volledig breed)
    ├── Tabelkop (bg #E2EDF1, font SemiBold)
    ├── Rijen (alternating #FFFFFF / #F4F7F9)
    └── Pagination onderaan
```
Componenten: header, search bar, chip (filters), card (als tabelcontainer), pagination

**Detailpagina:**
```
Header (titel + acties zoals "Bewerken", "Verwijderen")
├── Hoofdkaart 60-70% (formulier of informatie)
│   ├── Chapter bars (sectiescheiders)
│   ├── Input groepen (floating label)
│   └── Actiebuttons onderaan
└── Sidepanel 30-40% (status, metadata, notities)
    ├── Statuschips
    ├── Contactinfo met monogram
    └── Notitieblok (gele achtergrond)
```
Componenten: header, card, chapter bar, input, chip, monogram, note

**Formulier (volledig breed):**
```
Header (staptitel, of "Nieuwe aanvraag")
└── Formulierkaart (max-w 640px, gecentreerd)
    ├── Chapter bar ("Persoonlijke gegevens")
    ├── Input groep (floating labels, 2-koloms bij breed scherm)
    ├── Chapter bar ("Financiële gegevens")
    ├── Input groep
    ├── Radio/checkbox groepen
    └── Actiebuttons (rechts uitgelijnd: Annuleren + Opslaan)
```
Componenten: header, card, chapter bar, input, radio, checkbox, button

**Modal / Alert dialog:**
```
[Overlay rgba(0,0,0,0.5)]
└── Modal/Alert (wit, 16px radius, popup shadow)
    ├── [Sluitknop rechtsboven (modal)] of [Icoon cirkel (alert)]
    ├── Titel (H3, kleur #316A7D)
    ├── Body tekst (Body L Medium)
    ├── [Scheidingslijn border-top #C5DBE3]
    └── Actiebuttons (max 2: outlined links + filled rechts)
```
Alert icoon-cirkel per type: error=roze bg+rood icoon, warning=lichtroze+donkerrood, info=lichtgrijs+blauw, success=lichtgroen+donkergroen

**Login pagina:**
```
[Fullscreen achtergrondafbeelding 60%] [Loginkaart 40%]
                                       ├── Logo (donkere variant)
                                       ├── H1 "Inloggen"
                                       ├── Subtekst
                                       ├── Input velden
                                       └── CTA button (geel, rounded-full, full width)
```
Geen navigatie. Max breedte loginkaart: 440px. Extra grote shadow (shadow-2xl).

**Error pagina:**
```
[Volledig scherm, bg #F4F7F9, gecentreerd]
├── Illustratie (UFO met karakter-hexagon + karakter-rechthoek)
├── H1 foutcode ("Pagina niet beschikbaar")
├── Body L uitleg
├── Primary button ("Terug naar [BESTEMMING]")
└── Hulptekst ("Blijft dit probleem zich voordoen?")
```
Max breedte content: 480px. Gebruik Blinqx-illustraties, geen generieke iconen.

### 11.3 Component-combinatieregels

| Wanneer je... | Gebruik dan... | Nooit... |
|---|---|---|
| Acties groepeert | Max 2 buttons: 1 filled + 1 outlined | 3+ buttons naast elkaar |
| Status toont | Chip met statuskleur (positive/warning/regular) | Gekleurde tekst zonder achtergrond |
| Waarschuwt | Message bar (8px radius) met statuskleurenpaar | Alleen een rood randje of icoon |
| Bevestiging vraagt | Alert dialog met icoon-cirkel | Browser confirm() dialog |
| Data groepeert | Kaart met titelbalk + border-bottom | Alleen witruimte als scheiding |
| Secties scheidt (formulier) | Chapter bar (bg #E2EDF1, 16px radius) | Alleen een <hr> lijn |
| Navigatie bouwt | Sidebar (80px donker) of top bar (90px donker) | Beide tegelijk |
| Feedback geeft (hover) | Subtle bg shift + shadow transition 150ms | Kleurverandering van tekst |
| Lege state toont | Illustratie + H3 + body + optionele actiebutton | Alleen tekst "Geen resultaten" |
