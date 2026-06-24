# Rocket Lease — Presentación final

Presentación del Trabajo Práctico final de **Gestión de Desarrollo de Sistemas Informáticos** (FIUBA · Grupo 16), para el producto **Rocket Lease**.

> **Equipo:** Juan Manuel Dalmau · Francisco López Tancredi · Mariano Merlinsky · Ezequiel Pérez Adamo · Aizen Sánchez · Santino Zucconi

---

## ▶️ Cómo abrirla

**Doble-click en [`presentacion_rocket_lease.html`](presentacion_rocket_lease.html).**

Es un único archivo **autocontenido** (HTML + CSS + JS embebidos, logo y QR en base64). No necesita servidor, build ni conexión — solo un navegador moderno (Chrome, Edge, Firefox). La única dependencia externa es la fuente Poppins por CDN; sin internet, cae al fallback de sistema sin romper nada.

## ⌨️ Navegación y atajos

| Acción | Tecla / gesto |
|---|---|
| Avanzar | `→` · `barra espaciadora` · click en la mitad derecha |
| Retroceder | `←` · click en la mitad izquierda |
| Primera / última slide | `Inicio` / `Fin` |
| Vista general (miniaturas) | `O` o `Esc` |
| Saltar a sección (Portada/Intro/Demo/Gestión/Riesgos/Cierre) | `1`–`6` |
| Ayuda con todos los atajos | `?` |
| Ver la ficha de un riesgo | **doble-click** sobre el riesgo (slide 15) |

- **Barra de progreso**, contador `n / total` y dots de navegación siempre visibles.
- **Deep-linking por hash**: la URL guarda la slide actual (`...#slide-13`), así podés retomar donde quedaste o linkear una diapositiva puntual.
- Respeta `prefers-reduced-motion` (desactiva animaciones si el SO lo pide).
- En el cierre hay un **QR** que lleva a <https://rocketlease.qzz.io/>.

## 🗂️ Estructura del repositorio

```
presentacion/
├── presentacion_rocket_lease.html   ← la presentación (entregable 1)
├── guion_presentacion.md            ← guión por slide: quién habla, tiempos (entregable 2)
├── prompting/                       prompt y material de armado
│   ├── PROMPT_presentacion.md
│   ├── presentacion_final.md        estructura canónica de la presentación
│   ├── material_complementario.txt
│   └── official-antrhopic-prompting-guide.md
└── material/                        fuentes de datos y de marca
    ├── artefactos/                  Artefactos_RocketLease.xlsx + avances .pptx
    ├── diseño/                      BRAND.md · DESIGN.md · Logo.png
    ├── imagenes_riesgos/            Riesgos_Sprint1..6.png
    └── workflow-ia/                 WORKFLOW.md
```

## 📊 Fidelidad de datos

Todos los números salen de los artefactos reales, no hay cifras inventadas:

- **Sprints / Avance / Burn-Up / Burn-Down** → pestaña `Avance` de `material/artefactos/Artefactos_RocketLease.xlsx` (290 SP planificados · 290 realizados, con el Sprint 7 cerrado).
- **Riesgos** → evolución de `material/imagenes_riesgos/Riesgos_Sprint*.png` + estado final de la pestaña `Análisis de Riesgos` del xlsx.
- **Features ↔ Personas, Cronograma, User Stories** → pestañas del mismo xlsx + re-estimación 313 → 290 SP de los `.pptx`.

## 🎨 Marca

Sigue `material/diseño/BRAND.md` y `DESIGN.md` ("Noche violeta confiable", dark-premium):
**cian = Conductor/Cliente · ámbar = Rentador · violeta = marca/plataforma (Administrador)**.
