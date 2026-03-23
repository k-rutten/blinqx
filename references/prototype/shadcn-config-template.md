# Blinqx shadcn/ui Configuration

## components.json

Place this at the root of your Next.js project:

```json
{
  "$schema": "https://ui.shadcn.com/schema.json",
  "style": "new-york",
  "rsc": true,
  "tsx": true,
  "tailwind": {
    "config": "",
    "css": "app/globals.css",
    "baseColor": "neutral",
    "cssVariables": true,
    "prefix": ""
  },
  "aliases": {
    "components": "@/components",
    "utils": "@/lib/utils",
    "ui": "@/components/ui",
    "lib": "@/lib",
    "hooks": "@/hooks"
  },
  "iconLibrary": "lucide"
}
```

Key choices:
- **Style**: `new-york` (more refined, compact components)
- **Base color**: `neutral` (our custom brand tokens override this)
- **CSS variables**: `true` (design tokens via `globals.css`)
- **Icon library**: `lucide` (consistent, lightweight icons)

## lib/utils.ts

```typescript
import { clsx, type ClassValue } from 'clsx'
import { twMerge } from 'tailwind-merge'

export function cn(...inputs: ClassValue[]) {
  return twMerge(clsx(inputs))
}
```

## postcss.config.mjs

```javascript
/** @type {import('postcss-load-config').Config} */
const config = {
  plugins: {
    '@tailwindcss/postcss': {},
  },
}

export default config
```

## Required Dependencies

```bash
# Core UI
npm install class-variance-authority clsx tailwind-merge

# Radix UI primitives (installed automatically by shadcn add)
# npm install @radix-ui/react-*

# Icons
npm install lucide-react

# Theme support (if dark mode needed)
npm install next-themes

# Tailwind v4 PostCSS
npm install -D @tailwindcss/postcss
```

## Installing shadcn Components

After setting up the config files above:

```bash
# Initialize shadcn (will detect components.json)
npx shadcn@latest init

# Add commonly used components
npx shadcn@latest add button input label card dropdown-menu avatar dialog tabs
```

All shadcn components will automatically use the Blinqx design tokens from `globals.css`.
