# Blinqx Project Setup Guide

Step-by-step guide to initialize a new Blinqx-branded Next.js prototype.

## 1. Create Next.js Project

```bash
npx create-next-app@latest my-blinqx-app \
  --typescript \
  --tailwind \
  --eslint \
  --app \
  --src-dir=false \
  --import-alias="@/*"
```

## 2. Install Dependencies

```bash
# UI framework
npm install class-variance-authority clsx tailwind-merge lucide-react

# Radix primitives (added automatically by shadcn, but these are common)
npm install @radix-ui/react-dropdown-menu @radix-ui/react-dialog @radix-ui/react-avatar @radix-ui/react-tabs @radix-ui/react-tooltip

# Theme support
npm install next-themes

# Tailwind v4 PostCSS plugin
npm install -D @tailwindcss/postcss
```

## 3. Configure PostCSS

Replace `postcss.config.mjs`:

```javascript
/** @type {import('postcss-load-config').Config} */
const config = {
  plugins: {
    '@tailwindcss/postcss': {},
  },
}

export default config
```

**Delete** `tailwind.config.ts` if it exists — Tailwind v4 uses `@theme inline` in CSS instead.

## 4. Copy globals.css

Replace `app/globals.css` with the template from `globals-css-template.md` (in this folder).

## 5. Set Up Root Layout

Replace `app/layout.tsx`:

```tsx
import type React from "react"
import type { Metadata } from "next"
import { Inter } from "next/font/google"
import "./globals.css"

const inter = Inter({
  subsets: ["latin"],
  variable: "--font-inter",
  display: "swap",
})

export const metadata: Metadata = {
  title: "Blinqx [Your Product Name]",
  description: "[Your description]",
  icons: {
    icon: "/icon.svg",
  },
}

export default function RootLayout({
  children,
}: Readonly<{
  children: React.ReactNode
}>) {
  return (
    <html lang="nl">
      <body className={`${inter.variable} font-sans antialiased`}>
        {children}
      </body>
    </html>
  )
}
```

### Font Notes

- **Official brand font**: Metropolis UI (from Figma Style Guide)
- **Web fallback**: Inter (closest geometric sans-serif on Google Fonts)
- If Metropolis UI is available as self-hosted font files, replace the Inter import:

```tsx
import localFont from "next/font/local"

const metropolis = localFont({
  src: [
    { path: "./fonts/MetropolisUI-Medium.woff2", weight: "500", style: "normal" },
    { path: "./fonts/MetropolisUI-SemiBold.woff2", weight: "600", style: "normal" },
  ],
  variable: "--font-inter", // Keep the same CSS variable name for compatibility
  display: "swap",
})
```

## 6. Create Utility File

Create `lib/utils.ts`:

```typescript
import { clsx, type ClassValue } from 'clsx'
import { twMerge } from 'tailwind-merge'

export function cn(...inputs: ClassValue[]) {
  return twMerge(clsx(inputs))
}
```

## 7. Initialize shadcn

Create `components.json` at the project root (see `shadcn-config-template.md` in this folder), then:

```bash
# Add commonly needed components
npx shadcn@latest add button input label card dropdown-menu avatar dialog tabs tooltip
```

## 8. Copy Brand Assets

Copy logo SVGs to `public/images/`:
- Product-specific logo for dark backgrounds → `public/images/[product]-logo.svg`
- Product-specific logo for light backgrounds → `public/images/[product]-logo-dark.svg`

Copy the adaptive favicon:
- `public/icon.svg` (VX monogram — modify for your product if needed)

The yellow hexagonal chevron mark (`#FFCD00`) is the shared Blinqx brand element.

## 9. Verify Setup

Create a test page at `app/page.tsx`:

```tsx
export default function Home() {
  return (
    <div className="min-h-screen bg-background">
      {/* Header */}
      <header className="bg-[#1d2632] text-white px-6 py-4">
        <h1 className="text-lg font-semibold">Blinqx Test</h1>
      </header>

      {/* Content */}
      <main className="mx-auto px-6 py-8 max-w-6xl">
        <h2 className="text-xl font-semibold text-[#316A7D] mb-4">
          Section Heading
        </h2>
        <div className="rounded-xl bg-white shadow-sm border border-[#C5DBE3] p-6">
          <p className="text-[#1D2632]">Card content</p>
          <p className="text-[#4A515B] text-sm mt-2">Secondary text</p>
        </div>
      </main>
    </div>
  )
}
```

Run `npm run dev` and verify:
- Page background is light blue-gray (`#F4F7F9`)
- Header is dark navy (`#1D2632`)
- Section heading is dark blue (`#316A7D`)
- Card has white background with Figma border (`#C5DBE3`)
- Body text is navy (`#1D2632`), secondary text is help grey (`#4A515B`)
- Yellow accents (`#FFCD00`) for CTAs and active states

## 10. Reference Files

After setup, use these skill reference files for implementation:
- `design-tokens.json` — complete token system with 68 Figma CSS variables
- `components.json` — full component specs with Figma links and shadcn mappings
- `component-patterns.md` — copy-paste TSX patterns for all 14 component types
- `brand-identity.md` — design principles, do's/don'ts, decision tree for new elements
- `ai-coding-rules.md` — rule set for AI code generators (v0, Claude Code, Cursor)
