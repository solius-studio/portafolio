---
name: astro-tailwind-pro
description: >-
  Expert guide and best practices for developing with Astro (v5/v7) and Tailwind CSS v4 in Solius Studio.
  Use whenever creating or modifying Astro pages, components, layouts, routing, assets, or Tailwind styling.
---

# Astro & Tailwind CSS v4 Engineering Guide

## 1. Core Principles
- **Zero-JS by Default**: Do not send client-side JavaScript unless interactivity is strictly required. Leverage pure Astro `.astro` components.
- **Island Architecture**: When client interactivity is necessary, use explicit client directives:
  - `client:idle`: For non-critical widgets (e.g. chat widgets, analytics trackers).
  - `client:visible`: For interactive elements below the fold (e.g. bento animations, FAQ accordions).
  - `client:load`: Only for critical above-the-fold interactive components (e.g. sticky mobile navigation menus).
- **PageSpeed 100/100**: Fast LCP (Largest Contentful Paint), minimal CLS (Cumulative Layout Shift), and optimized assets.

---

## 2. Astro Component Patterns
- **Frontmatter Script (`---`)**:
  - Keep data fetching, imports, and interface definitions clean and typed.
  - Export component props with TypeScript `interface Props { ... }`.
  ```astro
  ---
  import { ArrowRight } from '@lucide/astro';

  interface Props {
    title: string;
    subtitle?: string;
    href: string;
  }

  const { title, subtitle, href } = Astro.props;
  ---

  <a href={href} class="group inline-flex items-center gap-2 ...">
    <span>{title}</span>
    <ArrowRight class="w-4 h-4 transition-transform group-hover:translate-x-1" />
  </a>
  ```

- **Slot Composition**:
  - Favor `<slot />` or named slots (`<slot name="icon" />`) to keep components reusable and decoupled.

---

## 3. Tailwind CSS v4 Guidelines
- **CSS-First Configuration**: Tailwind v4 uses standard CSS inside `src/styles/global.css`:
  - Uses `@import "tailwindcss";`
  - Custom theme tokens are defined via `@theme { ... }`.
  - Avoid legacy `tailwind.config.js` or `tailwind.config.cjs` files.
- **Semantic Color Usage**:
  - Dark background: `bg-[#070709]` or `bg-zinc-950`
  - Subtle borders: `border-white/10` or `border-zinc-800`
  - Glass cards: `bg-zinc-900/50 backdrop-blur-md`
  - Primary Accent: `text-red-500`, `bg-red-600 hover:bg-red-500`

---

## 4. API & Server Endpoints (`src/pages/api/`)
- When creating endpoints for forms, webhooks, or AI calls, create files under `src/pages/api/*.ts`:
  ```ts
  import type { APIRoute } from 'astro';

  export const prerender = false; // Required if project is in hybrid or static mode

  export const POST: APIRoute = async ({ request }) => {
    try {
      const data = await request.json();
      // Handle logic (e.g., webhook to n8n or LLM call)
      return new Response(JSON.stringify({ success: true }), {
        status: 200,
        headers: { 'Content-Type': 'application/json' }
      });
    } catch (error) {
      return new Response(JSON.stringify({ error: 'Invalid payload' }), { status: 400 });
    }
  };
  ```

---

## 5. Checklist Before Committing
- [ ] No unwanted console logs in client scripts.
- [ ] All images use `loading="lazy"` (except hero images which should have `loading="eager"` or `fetchpriority="high"`).
- [ ] Responsive design verified (mobile 375px, tablet 768px, desktop 1280px+).
- [ ] Semantic HTML tags (`<header>`, `<main>`, `<section>`, `<article>`, `<footer>`).
