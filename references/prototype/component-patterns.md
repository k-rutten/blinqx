# Blinqx Component Patterns

Code patterns extracted from the WorQX prototype and updated with Figma design tokens. Use as reference when building new Blinqx prototypes.

## Design System Component Inventory

From the Figma Style Guide, the Blinqx design system defines these 14 component types:

**Buttons** · **Headers** · **Cards & Side panels** · **Input** · **Alert** · **Controls** (toggle/switch/checkbox/radio) · **Tabs** · **Chips** · **Modals** · **Tooltips** · **Display** · **Message bars** · **Pickers** · **Menus**

All components share: rounded corners (`rounded-xl` / `rounded-2xl`), border in C5DBE3 (`#C5DBE3`), N100 text (`#1D2632`), Y100/B100 accents, and states (default/hover/focus/disabled/error).

---

## App Header (Dark Navigation Bar)

```tsx
<header className="bg-[#343C47] text-white flex-shrink-0">
  <div className="px-6 py-4">
    <div className="flex items-center justify-between">
      {/* Logo + Nav */}
      <div className="flex items-center gap-8">
        <Link href="/">
          <Image src="/images/[product]-logo.svg" alt="Logo" width={124} height={51} priority />
        </Link>

        <nav className="flex items-center">
          {navItems.map((item) => {
            const isActive = pathname === item.href
            return (
              <Link
                key={item.href}
                href={item.href}
                className={`px-4 py-6 relative text-sm transition-colors ${
                  isActive ? "text-[#FFCD00]" : "text-white/70 hover:text-white"
                }`}
              >
                {item.label}
                {isActive && <span className="absolute bottom-0 left-0 right-0 h-1 bg-[#FFCD00]" />}
              </Link>
            )
          })}
        </nav>
      </div>

      {/* Right side: company switcher + user menu */}
      <div className="flex items-center gap-3">
        {/* Company Switcher Pill */}
        <Button variant="ghost" className="flex items-center gap-2 bg-[#4A515B] text-white hover:bg-[#343C47] rounded-full px-4 py-2 h-auto">
          <Home className="w-4 h-4" />
          <span className="text-sm">{activeCompany.name}</span>
          <ChevronDown className="w-4 h-4" />
        </Button>

        {/* User Avatar */}
        <Avatar className="w-9 h-9">
          <AvatarFallback className="bg-[#F4F7F9] text-[#343C47] text-sm font-semibold">
            {initials}
          </AvatarFallback>
        </Avatar>
      </div>
    </div>
  </div>
</header>
```

**Key classes:**
- Header bg: `bg-[#343C47]`
- Active nav link: `text-[#FFCD00]`
- Active indicator: `h-1 bg-[#FFCD00]` (bottom border)
- Inactive nav: `text-white/70 hover:text-white`
- Company pill: `bg-[#4A515B] hover:bg-[#343C47]`

## User Dropdown Menu (Dark Theme)

```tsx
<DropdownMenuContent align="end" className="w-64 bg-[#343C47] border-[#343C47] text-white">
  <DropdownMenuLabel className="p-4 pb-3">
    <div className="flex items-center gap-3">
      <Avatar className="w-12 h-12">
        <AvatarFallback className="bg-[#F4F7F9] text-[#343C47] text-base font-semibold">
          {initials}
        </AvatarFallback>
      </Avatar>
      <div className="flex flex-col min-w-0">
        <span className="font-semibold text-base text-white">{name}</span>
        <span className="text-xs text-white/70 font-normal">{email}</span>
      </div>
    </div>
  </DropdownMenuLabel>
  <DropdownMenuSeparator className="bg-white/10" />
  <DropdownMenuItem className="px-4 py-3 text-white hover:bg-white/10 focus:bg-white/10 cursor-pointer">
    <User className="w-4 h-4 mr-3" />
    Menu item
  </DropdownMenuItem>
</DropdownMenuContent>
```

## Section Layout

```tsx
<main className="flex-1 overflow-auto bg-[#F4F7F9]">
  <div className="mx-auto px-6 py-8">
    {/* Section heading */}
    <h2 className="text-xl font-semibold text-[#316A7D] mb-4">
      Section Title
    </h2>

    {/* Card grid */}
    <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
      <div className="rounded-xl bg-white shadow-sm border border-[#C5DBE3] p-6">
        {/* Card content */}
      </div>
    </div>
  </div>
</main>
```

**Key classes:**
- Page bg: `bg-[#F4F7F9]`
- Section heading: `text-xl font-semibold text-[#316A7D]`
- Card: `rounded-xl bg-white shadow-sm border border-[#C5DBE3]`

## Buttons

### Primary (Yellow CTA)
```tsx
<Button className="bg-[#FFCD00] hover:bg-[#FFD631] text-[#343C47] font-semibold">
  Action
</Button>
```

### Primary CTA (Login-style, full-width rounded)
```tsx
<Button className="w-full h-11 rounded-full bg-[#FFCD00] hover:bg-[#FFD631] text-[#343C47] font-semibold text-sm shadow-none">
  Inloggen
</Button>
```

### Outline
```tsx
<Button variant="outline" className="rounded-full border-[#C5DBE3] hover:bg-[#F4F7F9] text-[#343C47] font-medium text-sm bg-white">
  Secondary Action
</Button>
```

### Ghost (header)
```tsx
<Button variant="ghost" className="hover:bg-white/10 text-white">
  Ghost
</Button>
```

## Input Fields (Bottom Border Pattern)

```tsx
<div className="space-y-1.5">
  <Label htmlFor="field" className="text-[#343C47] text-sm font-medium">
    Label Text
  </Label>
  <input
    id="field"
    type="text"
    className="w-full bg-[#F4F7F9] text-[#343C47] text-base px-4 py-3 border-b border-[#C5DBE3] focus:border-[#FFCD00] focus:outline-none placeholder-[#7A8591]"
    placeholder=""
  />
</div>
```

**Key classes:**
- Background: `bg-[#F4F7F9]`
- Border: `border-b border-[#C5DBE3]` (bottom border only)
- Focus: `focus:border-[#FFCD00] focus:outline-none`
- Text: `text-[#343C47]`

## Floating Label Input (Bottom Border Pattern)

```tsx
<div className="relative mb-6">
  <input
    id="floatingInput"
    type="text"
    className="peer w-full bg-[#F4F7F9] text-[#343C47] text-base px-4 py-3 border-b border-[#C5DBE3] focus:border-[#FFCD00] focus:outline-none placeholder-transparent"
    placeholder="Email address"
  />
  <label
    htmlFor="floatingInput"
    className="absolute left-4 -top-2.5 text-sm text-[#7A8591] transition-all peer-focus:-top-2.5 peer-focus:text-[#FFCD00] peer-placeholder-shown:top-3 peer-placeholder-shown:text-base"
  >
    Email address
  </label>
</div>
```

## Login Page

```tsx
<div className="min-h-screen relative flex items-center justify-center lg:justify-end">
  {/* Background Image */}
  <div className="absolute inset-0 z-0">
    <Image src="/images/login-bg.jpg" alt="Background" fill className="object-cover" priority />
  </div>

  {/* Login Card */}
  <div className="relative z-10 w-full max-w-[400px] mx-6 lg:mr-16">
    <div className="bg-white rounded-2xl shadow-2xl px-7 py-8">
      {/* Dark text logo on white card */}
      <Image src="/images/[product]-logo-dark.svg" alt="Logo" width={110} height={36} className="h-8 w-auto mb-6" />

      <h1 className="text-[#343C47] text-2xl font-bold mb-2">Inloggen</h1>
      <p className="text-[#7A8591] text-sm leading-relaxed mb-6">
        Welcome text here.
      </p>

      {/* Form fields + buttons */}
    </div>
  </div>
</div>
```

## Application Tile (Hexagonal Icon)

```tsx
<button className="group relative flex flex-col items-center justify-center gap-4 rounded-lg border border-[#C5DBE3] bg-white p-8 transition-all hover:border-[#FFCD00]/50 hover:shadow-md focus:outline-none focus:ring-2 focus:ring-[#FFCD00] focus:ring-offset-2">
  <div className="relative h-20 w-20">
    <svg viewBox="0 0 100 100" className="h-full w-full transition-transform group-hover:scale-105">
      <polygon points="50,5 95,27.5 95,72.5 50,95 5,72.5 5,27.5" fill="#FFCD00" />
      <polygon points="50,12 88,31 88,69 50,88 12,69 12,31" fill="#FFD631" opacity="0.4" />
    </svg>
    <div className="absolute inset-0 flex items-center justify-center">
      <span className="text-lg font-bold text-[#343C47]">{shortCode}</span>
    </div>
  </div>
  <span className="text-base font-medium text-[#343C47]">{name}</span>
</button>
```

## Loading Spinner

```tsx
<div className="min-h-screen flex items-center justify-center bg-[#F4F7F9]">
  <div className="text-center">
    <div className="w-8 h-8 border-4 border-[#FFCD00] border-t-transparent rounded-full animate-spin mx-auto mb-4" />
    <p className="text-sm text-[#7A8591]">Loading...</p>
  </div>
</div>
```

## Message Bar Component

### Info
```tsx
<div className="flex items-center gap-3 bg-[#EFF2F7] border-l-4 border-[#6DA6B9] rounded px-4 py-3">
  <InfoIcon className="w-5 h-5 text-[#6DA6B9] flex-shrink-0" />
  <p className="text-sm text-[#343C47]">Info message text</p>
</div>
```

### Success
```tsx
<div className="flex items-center gap-3 bg-[#CDF0EA] border-l-4 border-[#04B698] rounded px-4 py-3">
  <CheckCircleIcon className="w-5 h-5 text-[#04B698] flex-shrink-0" />
  <p className="text-sm text-[#343C47]">Success message text</p>
</div>
```

### Warning
```tsx
<div className="flex items-center gap-3 bg-[#EDBCBC] border-l-4 border-[#FFA652] rounded px-4 py-3">
  <AlertIcon className="w-5 h-5 text-[#FFA652] flex-shrink-0" />
  <p className="text-sm text-[#343C47]">Warning message text</p>
</div>
```

### Error
```tsx
<div className="flex items-center gap-3 bg-[#F6DEDE] border-l-4 border-[#D15858] rounded px-4 py-3">
  <AlertCircleIcon className="w-5 h-5 text-[#D15858] flex-shrink-0" />
  <p className="text-sm text-[#343C47]">Error message text</p>
</div>
```

## Chip Component

### Default
```tsx
<span className="inline-flex items-center gap-2 px-3 py-1.5 rounded-full bg-[#F4F7F9] text-[#343C47] text-sm font-medium border border-[#C5DBE3]">
  Default chip
  <button className="text-[#7A8591] hover:text-[#343C47]">×</button>
</span>
```

### Regular (Primary)
```tsx
<span className="inline-flex items-center gap-2 px-3 py-1.5 rounded-full bg-[#E8F1FF] text-[#316A7D] text-sm font-medium border border-[#C5DBE3]">
  Regular chip
  <button className="text-[#6DA6B9] hover:text-[#316A7D]">×</button>
</span>
```

### Positive (Success)
```tsx
<span className="inline-flex items-center gap-2 px-3 py-1.5 rounded-full bg-[#CDF0EA] text-[#04B698] text-sm font-medium border border-[#04B698]/20">
  Positive chip
  <button className="text-[#04B698] hover:text-[#048E78]">×</button>
</span>
```

### Warning
```tsx
<span className="inline-flex items-center gap-2 px-3 py-1.5 rounded-full bg-[#EDBCBC] text-[#FFA652] text-sm font-medium border border-[#FFA652]/20">
  Warning chip
  <button className="text-[#FFA652] hover:text-[#FF8C23]">×</button>
</span>
```

## Switch Component

### On State
```tsx
<label className="flex items-center cursor-pointer">
  <input type="checkbox" className="hidden peer" defaultChecked />
  <div className="relative inline-flex w-11 h-6 bg-[#04B698] rounded-full peer-focus:outline-none peer-focus:ring-2 peer-focus:ring-[#04B698]/50 transition-colors">
    <span className="absolute top-0.5 left-0.5 w-5 h-5 bg-white rounded-full transition-transform peer-checked:translate-x-5" />
  </div>
</label>
```

### Off State
```tsx
<label className="flex items-center cursor-pointer">
  <input type="checkbox" className="hidden peer" />
  <div className="relative inline-flex w-11 h-6 bg-[#C5DBE3] rounded-full peer-focus:outline-none peer-focus:ring-2 peer-focus:ring-[#6DA6B9]/50 transition-colors">
    <span className="absolute top-0.5 left-0.5 w-5 h-5 bg-white rounded-full transition-transform peer-checked:translate-x-5" />
  </div>
</label>
```

## Tab Component

```tsx
<div className="border-b border-[#C5DBE3]">
  <div className="flex gap-8">
    {tabs.map((tab) => (
      <button
        key={tab.id}
        onClick={() => setActiveTab(tab.id)}
        className={`px-1 py-3 text-sm font-medium border-b-2 transition-colors ${
          activeTab === tab.id
            ? "border-[#FFCD00] text-[#343C47]"
            : "border-transparent text-[#7A8591] hover:text-[#343C47]"
        }`}
      >
        {tab.label}
      </button>
    ))}
  </div>
</div>

{/* Tab content */}
<div className="py-6">
  {activeTabContent}
</div>
```

## Alert Dialog with Icon Circle

```tsx
<div className="fixed inset-0 z-50 flex items-center justify-center bg-black/50">
  <div className="bg-white rounded-2xl shadow-2xl max-w-md p-8">
    {/* Icon circle background */}
    <div className="flex justify-center mb-6">
      <div className="w-16 h-16 rounded-full bg-[#EDBCBC] flex items-center justify-center">
        <AlertIcon className="w-8 h-8 text-[#FFA652]" />
      </div>
    </div>

    {/* Content */}
    <h2 className="text-xl font-bold text-[#343C47] text-center mb-2">
      Are you sure?
    </h2>
    <p className="text-sm text-[#7A8591] text-center mb-6">
      This action cannot be undone.
    </p>

    {/* Actions */}
    <div className="flex gap-3">
      <button className="flex-1 px-4 py-2 rounded-full border border-[#C5DBE3] text-[#343C47] font-medium hover:bg-[#F4F7F9] transition-colors">
        Cancel
      </button>
      <button className="flex-1 px-4 py-2 rounded-full bg-[#D15858] text-white font-medium hover:bg-[#C04949] transition-colors">
        Delete
      </button>
    </div>
  </div>
</div>
```

## Status Colors

Use these for semantic states across all components:

| State | Color | Figma | Light bg variant |
|-------|-------|-------|-----------------|
| Error / Destructive | `#D15858` | R100 | `#F6DEDE` |
| Success / Positive | `#04B698` | G100 | `#CDF0EA` |
| Warning / Attention | `#FFA652` | O100 | `#EDBCBC` |
| Info / Neutral | `#6DA6B9` | B100 | `#EFF2F7` |

## Common Tailwind Patterns

```
/* Hover transition */          transition-all / transition-colors
/* Focus ring */                focus:outline-none focus:ring-2 focus:ring-[#FFCD00] focus:ring-offset-2
/* Card shadow */               shadow-sm (default), shadow-md (hover), shadow-2xl (login card)
/* Border radius */             rounded-xl (cards, inputs), rounded-2xl (login card), rounded-full (buttons, pills)
/* Text truncation */           truncate / line-clamp-2
/* Responsive padding */        px-5 py-6 sm:px-7 sm:py-8
/* Input bottom-border */       border-b border-[#C5DBE3] focus:border-[#FFCD00]
```

## Color Token Reference

```
Primary Blue:         #6DA6B9 (use var(--surface/surface-blue-default, #6da6b9))
Primary Blue Dark:    #316A7D
CTA Yellow:           #FFCD00
Yellow Hover:         #FFD631
Dark Neutral (N90):   #343C47
Medium Neutral (N80): #4A515B
Light Background:     #F4F7F9
Border Default:       #C5DBE3
Text Muted:           #7A8591
Success:              #04B698
Warning:              #FFA652
Error:                #D15858
```
