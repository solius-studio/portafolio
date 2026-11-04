# AGENTS.md · Reglas de Trabajo para Agentes de IA en Solius Studio

Este archivo establece las directivas obligatorias para cualquier modelo o asistente de Inteligencia Artificial (Antigravity, Claude, Cursor, Codex, ChatGPT, etc.) que lea, modifique o genere código en este repositorio.

---

## 1. ⚠️ DIRECTIVA CRÍTICA: ICONOS PROPIETARIOS (PROHIBIDO ICONOS GENÉRICOS)

> **BAJO NINGUNA CIRCUNSTANCIA SE DEBEN IMPORTAR O INSTALAR LIBRERÍAS DE ICONOS EXTERNAS O GENÉRICAS** (por ejemplo: `lucide-astro`, `lucide-react`, `heroicons`, `font-awesome`, `react-icons`, etc.).

Todos los iconos deben provenir de la biblioteca propia de componentes Astro ubicada en:
📂 `src/components/icons/`

### Catálogo de Iconos Propios:
- `IconWeb.astro` ➔ Para sitios web, landings, diseño responsive y arquitecturas digitales.
- `IconEcommerce.astro` ➔ Para tiendas online, carritos, productos y pasarelas de pago.
- `IconLegal.astro` ➔ Para estudios jurídicos, contables, auditorías y firmas profesionales.
- `IconAI.astro` ➔ Para agentes de Inteligencia Artificial, automatizaciones y algoritmos.
- `IconSpeed.astro` ➔ Para velocidad de carga extrema, PageSpeed 100/100 y optimización.
- `IconShield.astro` ➔ Para seguridad informática, garantías de servicio y confianza.
- `IconGastronomy.astro` ➔ Para comercios gastronómicos, cartas digitales y restaurantes.
- `IconChatAI.astro` ➔ Para asistentes conversacionales, bots de WhatsApp y atención 24/7.
- `IconSparkle.astro` ➔ Para insignias premium, gemas y microinteracciones de marca.
- `IconArrowRight.astro` ➔ Para botones de acción (CTA) y navegación direccional.
- `IconCheck.astro` ➔ Para listas de ventajas verificadas y métricas cumplidas.

Si se requiere un icono nuevo que no existe en esta lista, **SE DEBE CREAR UN COMPONENTE PROPIO** en `src/components/icons/Icon<Nombre>.astro` siguiendo la plantilla de la skill `solius-icons-and-design`.

---

## 2. 🎨 Identidad Visual y Estilo Apple

1. **Paleta de Colores Obligatoria:**
   - **Fondo:** Negro absoluto y neutros profundos (`#070709`, `#0a0a0c`, `bg-neutral-950`).
   - **Bordes:** Finos y sutiles (`border border-white/10`), nunca bordes gruesos o toscos.
   - **Superficies:** Glassmorphism elegante (`bg-neutral-900/40 backdrop-blur-xl`).
   - **Acento Solius:** Rojo carmesí/rubí (`#ef4444`, `red-600`, `shadow-[0_0_25px_-5px_rgba(239,68,68,0.4)]`).
2. **Tipografía:**
   - Textos primarios en blanco nítido (`text-white font-bold tracking-tight`).
   - Textos secundarios en gris neutro legible (`text-neutral-400 font-normal leading-relaxed`).
3. **Móvil Primero:**
   - Todos los comercios y clientes prospectados navegan desde smartphones. La experiencia táctil y la velocidad en pantallas chicas debe ser impecable.

---

## 3. 🛠️ Stack y Entorno Técnico

- **Framework:** Astro v5/v7 (generación estática pura, cero sobrecarga JS en el cliente).
- **Estilos:** Tailwind CSS v4 con importación nativa `@import "tailwindcss";` en `src/styles/global.css`.
- **Despliegue:** GitHub Pages a través de GitHub Actions en la ruta base:
  - `site`: `'https://solius-studio.github.io'`
  - `base`: `'/portafolio'`
  - **Importante:** Cualquier ruta interna a assets debe ser compatible con la variable `import.meta.env.BASE_URL` o relativa.

---

## 4. 🧠 Skills Disponibles

Para procedimientos detallados, consultar la skill del proyecto:
- [solius-icons-and-design](./skills/solius-icons-and-design/SKILL.md) o [versión en .agents](./.agents/skills/solius-icons-and-design/SKILL.md).

---

## 5. ✅ Procedimiento de Verificación Obligatorio

Antes de finalizar cualquier tarea o hacer commit, el agente DEBE ejecutar:
```bash
npm run build
```
Si el build falla o produce warnings de componentes rotos, no se debe hacer push hasta corregirlo.
