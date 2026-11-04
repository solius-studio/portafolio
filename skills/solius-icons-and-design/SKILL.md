---
name: solius-icons-and-design
description: >-
  Guía de diseño, reglas de identidad visual y catálogo de iconos propietarios de Solius Studio.
  Usar esta skill cuando cualquier agente de IA cree o modifique componentes, páginas,
  botones, servicios o interfaces dentro del proyecto Solius Studio, para garantizar
  el uso exclusivo de los iconos propios y mantener la estética minimalista estilo Apple.
---

# Solius Studio · Sistema de Diseño e Iconos Propietarios

Este documento define la normativa técnica y visual estricta para cualquier agente de Inteligencia Artificial que trabaje en el código de **Solius Studio**.

---

## 1. ⚠️ Regla de Oro: Prohibición de Iconos Genéricos Externos

> **Queda terminantemente prohibido instalar o importar librerías de iconos genéricos de terceros** (como `lucide-astro`, `lucide-react`, `heroicons`, `font-awesome`, `react-icons`, etc.).

**Motivos:**
1. **Diferenciación de marca:** Solius Studio no usa plantillas ni iconos genéricos que cualquier otra web tiene. Todos los iconos son piezas vectoriales diseñadas a medida con el sello visual de la agencia.
2. **Rendimiento extremo:** Los iconos propios son componentes Astro nativos de cero dependencias en tiempo de ejecución.

Toda iconografía DEBE importarse desde `src/components/icons/`.

---

## 2. 📚 Catálogo de Iconos Propietarios Disponibles

| Componente | Archivo | Propósito / Cuándo usarlo |
| :--- | :--- | :--- |
| `<IconWeb />` | `src/components/icons/IconWeb.astro` | Sitios web, páginas institucionales, landings de alta velocidad, diseño responsive. |
| `<IconEcommerce />` | `src/components/icons/IconEcommerce.astro` | Tiendas online, catálogos, pasarelas de pago, carritos y checkout. |
| `<IconLegal />` | `src/components/icons/IconLegal.astro` | Estudios jurídicos, asesoría legal, auditorías, balance y justicia. |
| `<IconAI />` | `src/components/icons/IconAI.astro` | Agentes autónomos, núcleo de Inteligencia Artificial, integraciones y lógica inteligente. |
| `<IconSpeed />` | `src/components/icons/IconSpeed.astro` | Tiempos de carga ultrarrápidos, optimización de velocidad, PageSpeed 100/100. |
| `<IconShield />` | `src/components/icons/IconShield.astro` | Seguridad informática, garantía de servicio, confianza y protección de datos. |
| `<IconGastronomy />` | `src/components/icons/IconGastronomy.astro` | Comercios gastronómicos, cartas QR, cafeterías, restaurantes y bistrós. |
| `<IconChatAI />` | `src/components/icons/IconChatAI.astro` | Chatbots de WhatsApp, atención conversacional 24/7, soporte automático. |
| `<IconSparkle />` | `src/components/icons/IconSparkle.astro` | Destacados premium, microinteracciones, gemas e insignias distintivas. |
| `<IconArrowRight />` | `src/components/icons/IconArrowRight.astro` | Botones de llamado a la acción (CTA), enlaces de navegación y redirección. |
| `<IconCheck />` | `src/components/icons/IconCheck.astro` | Listas de características verificadas, ventajas competitivas y métricas cumplidas. |

---

## 3. 💻 Cómo Usar los Iconos en un Componente Astro

Importar siempre directamente por ruta relativa:

```astro
---
import IconWeb from '../components/icons/IconWeb.astro';
import IconArrowRight from '../components/icons/IconArrowRight.astro';
import IconCheck from '../components/icons/IconCheck.astro';
---

<div class="flex items-center gap-3">
  <!-- El icono respeta el color y tamaño mediante Tailwind -->
  <IconWeb class="w-6 h-6 text-white" />
  <p class="text-sm">Sitio Web Optimizado</p>
  <IconCheck class="w-4 h-4 text-red-500" />
</div>

<a href="#contacto" class="inline-flex items-center gap-2 text-red-500 hover:text-red-400">
  <span>Conocer más</span>
  <IconArrowRight class="w-3.5 h-3.5" />
</a>
```

---

## 4. 🎨 Creación de Nuevos Iconos Propios

Si el diseño requiere un icono que aún no existe en el catálogo:

1. **Ubicación:** Crearlo exclusivamente en `src/components/icons/Icon<Nombre>.astro`.
2. **Parámetros obligatorios:**
   - `viewBox="0 0 24 24"`.
   - `fill="none"`.
   - Prop `class` tipada (`interface Props { class?: string; }`) con default `w-6 h-6`.
3. **Estilo visual:**
   - Geometría de alta precisión y trazos limpios (`stroke-width="1.5"` a `1.8"`).
   - Trazos principales en `currentColor` con opacidades para dar profundidad dual (`stroke-opacity="0.85"` y `0.4"`).
   - **Acento quirúrgico en rojo carmesí:** Incluir al menos un detalle, nodo, gema o trazo en `#ef4444` para mantener la firma de Solius Studio.

### Plantilla para nuevo icono:
```astro
---
interface Props {
  class?: string;
}

const { class: className = "w-6 h-6" } = Astro.props;
---

<svg 
  viewBox="0 0 24 24" 
  fill="none" 
  xmlns="http://www.w3.org/2000/svg" 
  class={className}
>
  <!-- Estructura geométrica principal -->
  <path d="..." stroke="currentColor" stroke-width="1.6" stroke-opacity="0.85" />
  <!-- Detalle secundario con menor opacidad -->
  <path d="..." stroke="currentColor" stroke-width="1.2" stroke-opacity="0.4" />
  <!-- Sello / Acento distintivo Solius en rojo carmesí -->
  <circle cx="12" cy="12" r="1.5" fill="#ef4444" />
</svg>
```

---

## 5. 🎯 Paleta y Estética del Entorno

- **Fondo Global:** `#070709` / `bg-neutral-950`.
- **Bordes:** `border-white/10` con transición a `border-red-500/30` en hover.
- **Tarjetas:** Glassmorphism sutil `bg-neutral-900/40 backdrop-blur-xl`.
- **Textos:** Títulos en `text-white font-bold tracking-tight`, subtítulos en `text-neutral-400`.
- **Acentos:** Rojo rubí `text-red-500`, `bg-red-600 hover:bg-red-500`, glows `shadow-[0_0_30px_-5px_rgba(239,68,68,0.5)]`.
