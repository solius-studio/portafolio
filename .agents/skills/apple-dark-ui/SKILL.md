---
name: apple-dark-ui
description: >-
  Visual design system and UI/UX standards for Solius Studio: Apple-inspired dark mode,
  glassmorphism, bento grids, and high-performance micro-interactions.
  Use whenever styling components, adding animations, selecting colors, or crafting layouts.
---

# Apple-Inspired Dark Mode UI Design System

## 1. Aesthetic DNA
- **Refined Minimalism**: Generous spacing, clean typography hierarchies, zero clutter.
- **Deep Blacks & Neutral Grays**:
  - Background base: `#070709` or `zinc-950`
  - Elevated surfaces: `zinc-900/60` with `backdrop-blur-xl`
  - Subtle borders: `border-white/[0.08]` or `border-zinc-800/80`
  - Hover highlights: `border-white/20`
- **Accent Highlighting**:
  - Crimson / Ruby Red: `#ef4444` / `#dc2626` used with intentionality (never overwhelming).
  - Subtle radial glow effects (`radial-gradient`) in backgrounds to create depth.

---

## 2. Card & Glassmorphism Pattern
Use this standard class combination for cards and containers:

```html
<div class="relative overflow-hidden rounded-2xl border border-white/[0.08] bg-zinc-900/40 p-6 backdrop-blur-md transition-all duration-300 hover:border-white/20 hover:bg-zinc-900/60 hover:shadow-2xl hover:shadow-red-500/5">
  <!-- Subtle ambient corner light -->
  <div class="pointer-events-none absolute -right-12 -top-12 h-32 w-32 rounded-full bg-red-500/10 blur-2xl"></div>
  
  <!-- Content -->
  <h3 class="text-lg font-semibold text-white">Title</h3>
  <p class="mt-2 text-sm leading-relaxed text-zinc-400">Description text goes here.</p>
</div>
```

---

## 3. Bento Grid Standards
- Structure features and metrics using a multi-column asymmetric grid:
  - Responsive: `grid grid-cols-1 md:grid-cols-3 lg:grid-cols-4 gap-4 md:gap-6`
  - Colspan variations: `col-span-1 md:col-span-2` for featured items.
- Every bento cell should feature:
  1. A distinctive icon in a rounded badge (`bg-white/5 border border-white/10 p-2.5 rounded-xl`).
  2. High-contrast title (`text-zinc-100`).
  3. Visual asset, metric pill, or interactive preview.

---

## 4. Typography Hierarchy
- **Headline H1 / Hero**: `text-4xl sm:text-6xl lg:text-7xl font-bold tracking-tight text-white`
- **Section Titles H2**: `text-3xl sm:text-4xl font-semibold tracking-tight text-white`
- **Card Titles H3**: `text-lg sm:text-xl font-medium text-zinc-100`
- **Body Text**: `text-zinc-400 text-sm sm:text-base leading-relaxed`
- **Badges / Tags**: `text-xs font-medium tracking-wide uppercase px-3 py-1 rounded-full bg-zinc-800/60 border border-white/10 text-zinc-300`

---

## 5. Animation Rules (60 FPS Performance)
- Animate **only** `transform` and `opacity` properties. Avoid animating `width`, `height`, `margin`, or `padding` directly to prevent layout recalculations.
- Transitions: Use smooth cubic-beziers:
  - Transition duration: `duration-200` to `duration-300` for hover states.
  - Interactive elements must provide instantaneous feedback on click / tap.
