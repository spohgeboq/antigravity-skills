---
name: frontend-ui-dark-ts
description: "Build dark-themed React applications using Tailwind CSS with custom theming, glassmorphism effects, and Framer Motion animations. Use when creating dashboards, admin panels, or data-rich interfaces..."
risk: unknown
source: community
---

# Frontend UI Dark Theme (TypeScript)

A modern dark-themed React UI system using **Tailwind CSS** and **Framer Motion**. Designed for dashboards, admin panels, and data-rich applications with glassmorphism effects and tasteful animations.

## Stack

| Package | Version | Purpose |
|---------|---------|---------|
| `react` | ^18.x | UI framework |
| `react-dom` | ^18.x | DOM rendering |
| `react-router-dom` | ^6.x | Routing |
| `framer-motion` | ^11.x | Animations |
| `clsx` | ^2.x | Class merging |
| `tailwindcss` | ^3.x | Styling |
| `vite` | ^5.x | Build tool |
| `typescript` | ^5.x | Type safety |

## Quick Start

```bash
npm create vite@latest my-app -- --template react-ts
cd my-app
npm install framer-motion clsx react-router-dom
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

## Project Structure

```
public/
├── favicon.ico
├── favicon.svg
├── apple-touch-icon.png
├── og-image.png
└── site.webmanifest
src/
├── assets/fonts/
├── components/
│   ├── ui/
│   │   ├── Button.tsx
│   │   ├── Card.tsx
│   │   ├── Input.tsx
│   │   ├── Badge.tsx
│   │   ├── Dialog.tsx
│   │   ├── Tabs.tsx
│   │   └── index.ts
│   └── layout/
│       ├── AppShell.tsx
│       ├── Sidebar.tsx
│       └── PageHeader.tsx
├── styles/globals.css
├── App.tsx
└── main.tsx
```

## Configuration

### tailwind.config.js

```js
export default {
  content: ['./index.html', './src/**/*.{js,ts,jsx,tsx}'],
  theme: {
    extend: {
      fontFamily: {
        sans: ['Segoe UI', 'system-ui', 'sans-serif'],
      },
      colors: {
        brand: {
          DEFAULT: '#8251EE',
          hover: '#9366F5',
          light: '#A37EF5',
          subtle: 'rgba(130, 81, 238, 0.15)',
        },
        neutral: {
          bg1: 'hsl(240, 6%, 10%)',
          bg2: 'hsl(240, 5%, 12%)',
          bg3: 'hsl(240, 5%, 14%)',
          bg4: 'hsl(240, 4%, 18%)',
          bg5: 'hsl(240, 4%, 22%)',
          bg6: 'hsl(240, 4%, 26%)',
        },
        text: {
          primary: '#FFFFFF',
          secondary: '#A1A1AA',
          muted: '#71717A',
        },
        border: {
          subtle: 'hsla(0, 0%, 100%, 0.08)',
          DEFAULT: 'hsla(0, 0%, 100%, 0.12)',
          strong: 'hsla(0, 0%, 100%, 0.20)',
        },
        status: {
          success: '#10B981',
          warning: '#F59E0B',
          error: '#EF4444',
          info: '#3B82F6',
        },
        dataviz: {
          purple: '#8251EE',
          blue: '#3B82F6',
          green: '#10B981',
          yellow: '#F59E0B',
          red: '#EF4444',
          pink: '#EC4899',
          cyan: '#06B6D4',
        },
      },
      borderRadius: {
        DEFAULT: '0.5rem',
        lg: '0.75rem',
        xl: '1rem',
      },
      boxShadow: {
        glow: '0 0 20px rgba(130, 81, 238, 0.3)',
        'glow-lg': '0 0 40px rgba(130, 81, 238, 0.4)',
      },
      animation: {
        'fade-in': 'fadeIn 0.3s ease-out',
        'slide-up': 'slideUp 0.3s ease-out',
        'slide-down': 'slideDown 0.3s ease-out',
      },
      keyframes: {
        fadeIn: {
          '0%': { opacity: '0' },
          '100%': { opacity: '1' },
        },
        slideUp: {
          '0%': { opacity: '0', transform: 'translateY(10px)' },
          '100%': { opacity: '1', transform: 'translateY(0)' },
        },
        slideDown: {
          '0%': { opacity: '0', transform: 'translateY(-10px)' },
          '100%': { opacity: '1', transform: 'translateY(0)' },
        },
      },
      spacing: {
        'safe-top': 'env(safe-area-inset-top)',
        'safe-bottom': 'env(safe-area-inset-bottom)',
        'safe-left': 'env(safe-area-inset-left)',
        'safe-right': 'env(safe-area-inset-right)',
      },
      minHeight: {
        'touch': '44px',
      },
      minWidth: {
        'touch': '44px',
      },
    },
  },
  plugins: [],
};
```

### src/styles/globals.css

```css
@tailwind base;
@tailwind components;
@tailwind utilities;

:root {
  --color-brand: #8251EE;
  --color-brand-hover: #9366F5;
  --color-brand-light: #A37EF5;
  --color-brand-subtle: rgba(130, 81, 238, 0.15);
  --color-bg-1: hsl(240, 6%, 10%);
  --color-bg-2: hsl(240, 5%, 12%);
  --color-bg-3: hsl(240, 5%, 14%);
  --color-bg-4: hsl(240, 4%, 18%);
  --color-bg-5: hsl(240, 4%, 22%);
  --color-bg-6: hsl(240, 4%, 26%);
  --color-text-primary: #FFFFFF;
  --color-text-secondary: #A1A1AA;
  --color-text-muted: #71717A;
  --color-border-subtle: hsla(0, 0%, 100%, 0.08);
  --color-border-default: hsla(0, 0%, 100%, 0.12);
  --color-border-strong: hsla(0, 0%, 100%, 0.20);
  --color-success: #10B981;
  --color-warning: #F59E0B;
  --color-error: #EF4444;
  --color-info: #3B82F6;
  --spacing-xs: 0.25rem;
  --spacing-sm: 0.5rem;
  --spacing-md: 1rem;
  --spacing-lg: 1.5rem;
  --spacing-xl: 2rem;
  --spacing-2xl: 3rem;
  --radius-sm: 0.375rem;
  --radius-md: 0.5rem;
  --radius-lg: 0.75rem;
  --radius-xl: 1rem;
  --transition-fast: 150ms ease;
  --transition-normal: 200ms ease;
  --transition-slow: 300ms ease;
}

html {
  color-scheme: dark;
}

body {
  @apply bg-neutral-bg1 text-text-primary font-sans antialiased;
  min-height: 100vh;
}

*:focus-visible {
  @apply outline-none ring-2 ring-brand ring-offset-2 ring-offset-neutral-bg1;
}

::-webkit-scrollbar {
  width: 8px;
  height: 8px;
}

::-webkit-scrollbar-track {
  @apply bg-neutral-bg2;
}

::-webkit-scrollbar-thumb {
  @apply bg-neutral-bg5 rounded-full;
}

::-webkit-scrollbar-thumb:hover {
  @apply bg-neutral-bg6;
}

@layer components {
  .glass {
    @apply backdrop-blur-md bg-white/5 border border-white/10;
  }
  .glass-card {
    @apply backdrop-blur-md bg-white/5 border border-white/10 rounded-xl;
  }
  .glass-panel {
    @apply backdrop-blur-lg bg-black/40 border border-white/5;
  }
  .glass-overlay {
    @apply backdrop-blur-sm bg-black/60;
  }
  .glass-input {
    @apply backdrop-blur-sm bg-white/5 border border-white/10 focus:border-brand focus:bg-white/10;
  }
}

@layer utilities {
  .animate-in {
    animation: fadeIn 0.3s ease-out, slideUp 0.3s ease-out;
  }
}
```

### src/main.tsx

```tsx
import React from 'react';
import ReactDOM from 'react-dom/client';
import { BrowserRouter } from 'react-router-dom';
import App from './App';
import './styles/globals.css';

ReactDOM.createRoot(document.getElementById('root')!).render(
  <React.StrictMode>
    <BrowserRouter>
      <App />
    </BrowserRouter>
  </React.StrictMode>
);
```

### src/App.tsx

```tsx
import { Routes, Route } from 'react-router-dom';
import { AnimatePresence } from 'framer-motion';
import { AppShell } from './components/layout/AppShell';
import { Dashboard } from './pages/Dashboard';
import { Settings } from './pages/Settings';

export default function App() {
  return (
    <AppShell>
      <AnimatePresence mode="wait">
        <Routes>
          <Route path="/" element={<Dashboard />} />
          <Route path="/settings" element={<Settings />} />
        </Routes>
      </AnimatePresence>
    </AppShell>
  );
}
```

## Animation Patterns

### Framer Motion Variants

```tsx
export const fadeIn = {
  initial: { opacity: 0 },
  animate: { opacity: 1 },
  exit: { opacity: 0 },
  transition: { duration: 0.2 },
};

export const slideUp = {
  initial: { opacity: 0, y: 20 },
  animate: { opacity: 1, y: 0 },
  exit: { opacity: 0, y: 20 },
  transition: { duration: 0.3, ease: 'easeOut' },
};

export const scaleOnHover = {
  whileHover: { scale: 1.02 },
  whileTap: { scale: 0.98 },
  transition: { type: 'spring', stiffness: 400, damping: 17 },
};

export const staggerContainer = {
  hidden: { opacity: 0 },
  visible: {
    opacity: 1,
    transition: {
      staggerChildren: 0.05,
      delayChildren: 0.1,
    },
  },
};

export const staggerItem = {
  hidden: { opacity: 0, y: 10 },
  visible: {
    opacity: 1,
    y: 0,
    transition: { duration: 0.2, ease: 'easeOut' },
  },
};
```

### Page Transition Wrapper

```tsx
import { motion } from 'framer-motion';
import { ReactNode } from 'react';

interface PageTransitionProps {
  children: ReactNode;
}

export function PageTransition({ children }: PageTransitionProps) {
  return (
    <motion.div
      initial={{ opacity: 0, y: 20 }}
      animate={{ opacity: 1, y: 0 }}
      exit={{ opacity: 0, y: -20 }}
      transition={{ duration: 0.3, ease: 'easeOut' }}
    >
      {children}
    </motion.div>
  );
}
```

## Glass Effect Patterns

```tsx
// Glass Card
<div className="glass-card p-6">
  <h2 className="text-lg font-semibold text-text-primary">Card Title</h2>
  <p className="text-text-secondary mt-2">Card content goes here.</p>
</div>

// Glass Panel (Sidebar)
<aside className="glass-panel w-64 h-screen p-4">
  <nav className="space-y-2">{/* Navigation items */}</nav>
</aside>

// Glass Modal Overlay
<motion.div
  className="fixed inset-0 glass-overlay flex items-center justify-center z-50"
  initial={{ opacity: 0 }}
  animate={{ opacity: 1 }}
  exit={{ opacity: 0 }}
>
  <motion.div
    className="glass-card p-6 max-w-md w-full mx-4"
    initial={{ scale: 0.95, opacity: 0 }}
    animate={{ scale: 1, opacity: 1 }}
    exit={{ scale: 0.95, opacity: 0 }}
  >
    {/* Modal content */}
  </motion.div>
</motion.div>
```

## Typography

| Element | Classes |
|---------|---------|
| Page title | `text-2xl font-semibold text-text-primary` |
| Section title | `text-lg font-semibold text-text-primary` |
| Card title | `text-base font-medium text-text-primary` |
| Body text | `text-sm text-text-secondary` |
| Caption | `text-xs text-text-muted` |
| Label | `text-sm font-medium text-text-secondary` |

## Color Usage

| Use Case | Color | Class |
|----------|-------|-------|
| Primary action | Brand purple | `bg-brand text-white` |
| Primary hover | Brand hover | `hover:bg-brand-hover` |
| Page background | Neutral bg1 | `bg-neutral-bg1` |
| Card background | Neutral bg2 | `bg-neutral-bg2` |
| Elevated surface | Neutral bg3 | `bg-neutral-bg3` |
| Input background | Neutral bg2 | `bg-neutral-bg2` |
| Input focus | Neutral bg3 | `focus:bg-neutral-bg3` |
| Border default | Border default | `border-border` |
| Border subtle | Border subtle | `border-border-subtle` |
| Success | Status success | `text-status-success` |
| Warning | Status warning | `text-status-warning` |
| Error | Status error | `text-status-error` |

## Related Files

- Design Tokens — Complete color system, spacing, typography scales
- Components — Button, Card, Input, Dialog, Tabs, and more
- Patterns — Page layouts, navigation, lists, forms

## When to Use
This skill is applicable to execute the workflow or actions described in the overview.
