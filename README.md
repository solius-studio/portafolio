# Solius Studio 🚀

Agencia boutique de **Ingeniería Digital, Desarrollo Web de Alto Rendimiento y Automatizaciones con Inteligencia Artificial**.

Especializados en comercios de cercanía, plataformas e-commerce y servicios profesionales (estudios jurídicos y contables).

---

## 🎨 Identidad Visual
- **Estilo:** Minimalismo Apple (dark mode, glassmorphism, tipografía precisa, microinteracciones a 60 FPS).
- **Paleta de Colores:** Negros profundos (`#070709`), grises neutros (`#18181b`, `#27272a`), y acentos en rojo carmesí / rubí (`#ef4444`, `#dc2626`).

---

## 🛠️ Stack Tecnológico Base
- **Framework:** [Astro v5/v7](https://astro.build/) (Static Site Generation ultra veloz, 100/100 en Google PageSpeed).
- **Estilos:** Tailwind CSS v4.
- **Iconografía:** `@lucide/astro`.
- **Despliegue recomendado:** Vercel o Cloudflare Pages (CI/CD automático desde GitHub).

---

## 📁 Estructura del Proyecto
```
solius-studio/
├── public/                 # Favicons y assets estáticos
├── src/
│   ├── components/         # Componentes modulares
│   │   ├── Navbar.astro               # Barra de navegación flotante estilo Apple
│   │   ├── Hero.astro                 # Propuesta de valor, métricas y llamados a la acción
│   │   ├── BentoServices.astro        # Grilla bento con los 4 servicios clave
│   │   ├── ShowcasePreview.astro      # Vitrina de los casos de estudio ficticios
│   │   ├── AIAutomationSection.astro  # Sección explicativa de agentes IA y demo simulada
│   │   ├── Process.astro              # Proceso de trabajo paso a paso
│   │   ├── FAQ.astro                  # Preguntas frecuentes comerciales
│   │   ├── CTASection.astro           # Formulario y llamada a la acción final
│   │   └── Footer.astro               # Pie de página institucional
│   ├── layouts/
│   │   └── Layout.astro               # Plantilla global con luces ambientales y SEO
│   ├── pages/
│   │   └── index.astro                # Landing principal
│   └── styles/
│       └── global.css                 # Configuración de estilos y temas
└── astro.config.mjs
```

---

## 🚀 Hoja de Ruta de Demos Ficticias (Showcase)
Para generar confianza con clientes reales, se desarrollarán 3 proyectos de muestra:

1. **`LexVanguard` (Estudio Jurídico):**
   - Web corporativa sobria para abogados.
   - Intake de casos con filtro calificado antes de la consulta.
   - Agenda de turnos.
2. **`Aura Bistro & Bar` (Gastronomía / Comercio Local):**
   - Menú digital QR ultra rápido en smartphone.
   - Reservas y pedidos directos a WhatsApp con formato preestablecido.
3. **`NovaDesk AI` (Automatización Inteligente):**
   - Demostración de agente autónomo que responde dudas de un negocio las 24 horas y captura leads.

---

## 👥 Flujo de Trabajo en GitHub con tu Socio
1. **Clonar el repositorio:**
   ```bash
   git clone git@github.com:<tu-organizacion>/solius-studio.git
   ```
2. **Instalar dependencias:**
   ```bash
   npm install
   ```
3. **Iniciar entorno de desarrollo:**
   ```bash
   npm run dev
   ```
4. **Flujo de ramas (Branching):**
   - Nunca hacer push directo a `main`.
   - Crear una rama por funcionalidad: `git checkout -b feature/nombre-de-la-tarea`.
   - Abrir un Pull Request (PR) en GitHub para que el otro compañero lo revise y apruebe.
