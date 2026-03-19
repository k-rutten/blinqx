# Blinqx globals.css Template

Copy this complete `globals.css` file into your Next.js project at `app/globals.css`.
It contains all Blinqx design tokens, Tailwind v4 theme mapping, and base styles.

```css
@import "tailwindcss";

@custom-variant dark (&:is(.dark *));

:root {
  /* Core semantic tokens */
  --background: #f0f6f8;       /* B10 - page background */
  --foreground: #1d2632;       /* N100 - body text */
  --card: #ffffff;             /* W100 - card surfaces */
  --card-foreground: #1d2632;
  --popover: #ffffff;
  --popover-foreground: #1d2632;
  --primary: #e5b73b;          /* Yellow accent - active nav, buttons, spinners */
  --primary-foreground: #1d2632;
  --secondary: #d3e4ea;        /* B30 - secondary surfaces */
  --secondary-foreground: #1d2632;
  --muted: #d3e4ea;            /* B30 - muted backgrounds */
  --muted-foreground: #5f6d7a; /* ~N70 - secondary text */
  --accent: #d3e4ea;
  --accent-foreground: #1d2632;
  --destructive: oklch(0.577 0.245 27.325);  /* ~R100 #D15858 */
  --destructive-foreground: oklch(0.577 0.245 27.325);
  --border: #d3e4ea;           /* B30 - borders */
  --input: #d3e4ea;            /* B30 - input borders */
  --ring: #1a5f5a;             /* Teal - focus ring */

  /* Custom brand tokens */
  --brand-teal: #1a5f5a;       /* Section headings, focus ring */
  --brand-teal-light: #6da6b9; /* B100 - secondary buttons, progress */
  --brand-yellow: #e5b73b;     /* Active nav, primary buttons */
  --brand-yellow-light: #f5d77a; /* Hex inner glow, highlights */
  --brand-peach: #f5d5c8;      /* Avatar backgrounds */
  --brand-gold: #d4a84b;       /* Yellow button hover */

  /* Chart colors */
  --chart-1: oklch(0.646 0.222 41.116);
  --chart-2: oklch(0.6 0.118 184.704);
  --chart-3: oklch(0.398 0.07 227.392);
  --chart-4: oklch(0.828 0.189 84.429);
  --chart-5: oklch(0.769 0.188 70.08);

  /* Radius */
  --radius: 0.5rem;

  /* Sidebar (if needed) */
  --sidebar: oklch(0.985 0 0);
  --sidebar-foreground: oklch(0.145 0 0);
  --sidebar-primary: oklch(0.205 0 0);
  --sidebar-primary-foreground: oklch(0.985 0 0);
  --sidebar-accent: oklch(0.97 0 0);
  --sidebar-accent-foreground: oklch(0.205 0 0);
  --sidebar-border: oklch(0.922 0 0);
  --sidebar-ring: oklch(0.708 0 0);
}

.dark {
  --background: oklch(0.145 0 0);
  --foreground: oklch(0.985 0 0);
  --card: oklch(0.145 0 0);
  --card-foreground: oklch(0.985 0 0);
  --popover: oklch(0.145 0 0);
  --popover-foreground: oklch(0.985 0 0);
  --primary: oklch(0.985 0 0);
  --primary-foreground: oklch(0.205 0 0);
  --secondary: oklch(0.269 0 0);
  --secondary-foreground: oklch(0.985 0 0);
  --muted: oklch(0.269 0 0);
  --muted-foreground: oklch(0.708 0 0);
  --accent: oklch(0.269 0 0);
  --accent-foreground: oklch(0.985 0 0);
  --destructive: oklch(0.396 0.141 25.723);
  --destructive-foreground: oklch(0.637 0.237 25.331);
  --border: oklch(0.269 0 0);
  --input: oklch(0.269 0 0);
  --ring: oklch(0.439 0 0);
  --chart-1: oklch(0.488 0.243 264.376);
  --chart-2: oklch(0.696 0.17 162.48);
  --chart-3: oklch(0.769 0.188 70.08);
  --chart-4: oklch(0.627 0.265 303.9);
  --chart-5: oklch(0.645 0.246 16.439);
  --sidebar: oklch(0.205 0 0);
  --sidebar-foreground: oklch(0.985 0 0);
  --sidebar-primary: oklch(0.488 0.243 264.376);
  --sidebar-primary-foreground: oklch(0.985 0 0);
  --sidebar-accent: oklch(0.269 0 0);
  --sidebar-accent-foreground: oklch(0.985 0 0);
  --sidebar-border: oklch(0.269 0 0);
  --sidebar-ring: oklch(0.439 0 0);
}

/* ============================================================================
   Figma Design Token Variables
   
   These CSS custom properties are extracted from Figma and represent the
   complete design system for Blinqx custom components.
   
   Total: 68 variables across 4 groups (Surface, Text, Border, Background)
   
   WHEN TO USE:
   - Figma vars (--surface/, --text/, --border/, --background/) are for custom
     Blinqx components and precise Figma matching
   - shadcn vars (--primary, --background, etc. above) are for shadcn/ui 
     component theming and Tailwind color utilities
   ============================================================================ */

:root {
  /* SURFACE TOKENS (46 variables) - Background fills for components, states, and navigation */
  
  /* Neutral surfaces */
  --surface/surface-neutral-dark: #1D2632;
  --surface/surface-neutral-hovered: #343C47;
  --surface/surface-neutral-focused: #4A515B;
  --surface/surface-neutral-pressed: #4A515B;
  --surface/surface-neutral-light: #D2D4D6;
  
  /* Blue surfaces */
  --surface/surface-blue-default: #6DA6B9;
  --surface/surface-blue-dark: #316A7D;
  --surface/surface-blue-hovered: #7CAFC0;
  --surface/surface-blue-focused: #8AB8C7;
  --surface/surface-blue-pressed: #8AB8C7;
  --surface/surface-blue-light: #D3E4EA;
  
  /* Yellow surfaces */
  --surface/surface-yellow-default: #FFCD00;
  --surface/surface-yellow-hovered: #FFD631;
  --surface/surface-yellow-focused: #F9D244;
  --surface/surface-yellow-pressed: #F9D244;
  --surface/surface-yellow-light: #FDF4C8;
  
  /* Red surfaces */
  --surface/surface-red-default: #D15858;
  --surface/surface-red-light: #F6DEDE;
  
  /* Green surfaces */
  --surface/surface-green-light: #CDF0EA;
  
  /* Base surfaces */
  --surface/surface-white: #FFFFFF;
  --surface/surface-level-0: #F4F7F9;
  --surface/surface-level-1: #E2EDF1;
  
  /* Component-specific surfaces */
  --surface/surface-badge: #EDBCBC;
  --surface/surface-pull-down-menu: #EFF2F7;
  --surface/surface-pull-down-menu-default: #EFF2F7;
  --surface/surface-pull-down-menu-hovered: #E4EAF1;
  --surface/surface-help: #4A515B;
  
  /* Interactive surfaces */
  --surface/surface-switch-active: #6DA6B9;
  --surface/surface-switch-inactive: #CAD5E3;
  --surface/surface-disabled: #D2D4D6;
  --surface/surface-placeholder: #777D84;
  
  /* Border interaction surfaces */
  --surface/surface-border-hovered: #E4EAF1;
  --surface/surface-border-focused: #EAEEF4;
  --surface/surface-border-pressed: #EAEEF4;
  
  /* Navigation item surfaces (inactive) */
  --surface/surface-nav-item-inactive: #D2D4D6;
  --surface/surface-nav-item-inactive-hovered: #E4EAF1;
  --surface/surface-nav-item-inactive-focused: #EAEEF4;
  --surface/surface-nav-item-inactive-pressed: #EAEEF4;
  
  /* Navigation item surfaces (selected) */
  --surface/surface-nav-item-selected: #343C47;
  --surface/surface-nav-item-selected-hovered: #4A515B;
  --surface/surface-nav-item-selected-focused: #616770;
  --surface/surface-nav-item-selected-pressed: #616770;
  
  /* Navigation item surfaces (active) */
  --surface/surface-nav-item-active: #FFE680;
  --surface/surface-nav-item-active-hovered: #FCE995;
  --surface/surface-nav-item-active-focued: #FFF0B3; /* Note: Figma typo 'focued' (missing 's') — keeping for consistency */
  --surface/surface-nav-item-active-pressed: #FFF0B3;
  
  /* TEXT TOKENS (14 variables) - Foreground/text colors */
  --text/text-default: #1D2632;
  --text/text-white: #FFFFFF;
  --text/text-help: #4A515B;
  --text/text-placeholder: #777D84;
  --text/text-disabled-default: #777D84;
  --text/text-disabled-light: #D2D4D6;
  --text/text-blue-dark: #316A7D;
  --text/text-red-dark: #951C1C;
  --text/text-red-default: #D15858;
  --text/text-green-dark: #005C3E;
  --text/text-yellow-dark: #875500;
  --text/text-menu-label-active: #FFCD00;
  --text/text-menu-label-inactive: #D2D4D6;
  --text/text-nav-item-active: #FFE680;
  
  /* BORDER TOKENS (7 variables) - Border/outline colors */
  --border/border-default: #C5DBE3;
  --border/border-neutral-medium: #A5A8AD;
  --border/border-neutral-dark: #4A515B;
  --border/border-blue: #6DA6B9;
  --border/border-error: #D15858;
  --border/border-yellow: #FFCD00;
  --border/border-switch-inactive: #CAD5E3;
  
  /* BACKGROUND TOKENS (1 variable) - Page/container backgrounds */
  --background/background-default: #F4F7F9;
}

@theme inline {
  --font-sans: var(--font-inter), ui-sans-serif, system-ui, sans-serif;
  --font-mono: ui-monospace, monospace;
  --color-background: var(--background);
  --color-foreground: var(--foreground);
  --color-card: var(--card);
  --color-card-foreground: var(--card-foreground);
  --color-popover: var(--popover);
  --color-popover-foreground: var(--popover-foreground);
  --color-primary: var(--primary);
  --color-primary-foreground: var(--primary-foreground);
  --color-secondary: var(--secondary);
  --color-secondary-foreground: var(--secondary-foreground);
  --color-muted: var(--muted);
  --color-muted-foreground: var(--muted-foreground);
  --color-accent: var(--accent);
  --color-accent-foreground: var(--accent-foreground);
  --color-destructive: var(--destructive);
  --color-destructive-foreground: var(--destructive-foreground);
  --color-border: var(--border);
  --color-input: var(--input);
  --color-ring: var(--ring);
  --color-chart-1: var(--chart-1);
  --color-chart-2: var(--chart-2);
  --color-chart-3: var(--chart-3);
  --color-chart-4: var(--chart-4);
  --color-chart-5: var(--chart-5);
  --radius-sm: calc(var(--radius) - 4px);
  --radius-md: calc(var(--radius) - 2px);
  --radius-lg: var(--radius);
  --radius-xl: calc(var(--radius) + 4px);
  --color-sidebar: var(--sidebar);
  --color-sidebar-foreground: var(--sidebar-foreground);
  --color-sidebar-primary: var(--sidebar-primary);
  --color-sidebar-primary-foreground: var(--sidebar-primary-foreground);
  --color-sidebar-accent: var(--sidebar-accent);
  --color-sidebar-accent-foreground: var(--sidebar-accent-foreground);
  --color-sidebar-border: var(--sidebar-border);
  --color-sidebar-ring: var(--sidebar-ring);
}

@layer base {
  * {
    @apply border-border outline-ring/50;
  }
  body {
    @apply bg-background text-foreground;
  }
}
```

## Token → Figma Mapping

| CSS Token | Hex | Figma Code |
|-----------|-----|------------|
| `--background` | `#f0f6f8` | B10 |
| `--foreground` | `#1d2632` | N100 |
| `--primary` | `#e5b73b` | ~Y110 |
| `--border` / `--input` / `--secondary` / `--muted` | `#d3e4ea` | B30 |
| `--muted-foreground` | `#5f6d7a` | ~N70 |
| `--ring` / `--brand-teal` | `#1a5f5a` | ~B140 |
| `--brand-teal-light` | `#6da6b9` | B100 |
| `--brand-yellow-light` | `#f5d77a` | ~Y80 |
| `--brand-gold` | `#d4a84b` | ~Y120 |
| `--brand-peach` | `#f5d5c8` | — |