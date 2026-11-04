---
name: anti-generic-ui
description: >-
  Anti-AI-slop design system and boutique aesthetic standards for Solius Studio.
  Enforces distinct, high-craft, non-generic UI patterns and bans common AI design clichés.
  Use whenever creating or refining pages, layouts, visual components, cards, or hero sections.
---

# Anti-Generic UI & High-Craft Boutique Design Standards

## 1. The "Anti-AI-Slop" Manifesto
Standard AI assistants default to predictable, low-craft patterns that look like generic SaaS templates. In Solius Studio, these patterns are explicitly forbidden:

- ❌ **Banned**: Symmetrical 3-card feature grids with an icon, bold title, and two lines of gray text.
- ❌ **Banned**: Random purple/violet floating blur blobs detached from brand identity.
- ❌ **Banned**: Abstract 3D vector spheres or generic vector illustrations.
- ❌ **Banned**: Centered hero layouts with floating generic pill badges (`✨ Solución número 1`).

### What We Use Instead:
- ✅ **Bespoke Asymmetric Grids**: Varied card sizes (1-column focal point, 2-column detail ledger, data-dense strips).
- ✅ **Authentic Interface Artifacts**: Real interactive mockups, simulated code blocks, live status indicators, WhatsApp dialogue simulations, and live performance metrics.
- ✅ **Typographic Contrast**: Sharp pairings of high-contrast display headlines, clean sans-serif bodies, and technical monospace metadata tags (`font-mono text-xs uppercase tracking-widest text-zinc-500`).
- ✅ **Material Tactility**: Fine borders (`border-white/[0.07]`), dark glass surfaces (`bg-zinc-950/70 backdrop-blur-xl`), and controlled ruby red accents (`#ef4444`).

---

## 2. Micro-Artifacts That Build Authenticity
Every key section should feature at least one tangible, high-craft artifact:

### A. Live System Status Indicator
```html
<div class="inline-flex items-center gap-2 px-3 py-1 rounded-full border border-emerald-500/20 bg-emerald-500/10 text-emerald-400 text-xs font-mono">
  <span class="relative flex h-2 w-2">
    <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-emerald-400 opacity-75"></span>
    <span class="relative inline-flex rounded-full h-2 w-2 bg-emerald-500"></span>
  </span>
  <span>SISTEMAS OPERATIVOS // LATENCIA 18ms</span>
</div>
```

### B. High-Fidelity Interactive Preview Card
Instead of describing a service in abstract text, display a realistic miniature interactive card showing:
- Real timestamps (e.g. `Hoy 14:32`).
- Real business parameters (e.g. `Lead calificado: Facturación > $10k/mes`).
- Actionable buttons with clear tactile hover feedback.

---

## 3. Visual Depth & Lighting Hierarchy
- **Ambient Floor**: Base canvas is `#070709`.
- **Primary Cards**: `bg-zinc-900/40 border border-white/[0.08] hover:border-red-500/30 hover:bg-zinc-900/60`.
- **Top Edge Sheen**: Use a subtle linear top highlight to emulate hardware design:
  `before:absolute before:inset-x-0 before:top-0 before:h-px before:bg-gradient-to-r before:from-transparent before:via-white/20 before:to-transparent`
- **Monospace Technical Accents**: Use `font-mono text-[11px] text-zinc-500 uppercase tracking-wider` for step numbers, category badges, and version stamps (`// 01 ARCHITECTURE`, `// 02 AI INTEGRATION`).

---

## 4. Quality Checklist
Before shipping any visual component:
- [ ] Does this look like an exclusive boutique engineering firm, or a generic free template?
- [ ] Are all icons purposeful and custom-crafted rather than generic placeholders?
- [ ] Does every hover interaction feel instant, snappy, and hardware-accelerated?
- [ ] Is there clear contrast between primary, secondary, and metadata typography?
