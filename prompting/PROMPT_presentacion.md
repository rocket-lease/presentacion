# Prompt especializado — Generación de presentación Rocket Lease (HTML + guión)

> Pegá este prompt en una sesión nueva de Claude Code (modelo Opus 4.8, effort `xhigh`,
> `max_tokens` ≥ 64k) desde la raíz del repo `Rocket Lease`. Está construido siguiendo
> los lineamientos de `presentacion/prompting/official-antrhopic-prompting-guide.md`.

---

Sos un diseñador de presentaciones técnicas y front-end developer senior. Tu especialidad es convertir material de gestión de proyectos en presentaciones HTML autocontenidas, memorables y fáciles de exponer en vivo. Trabajás con precisión sobre datos reales y respetás al pie de la letra los sistemas de marca.

Tu tarea tiene **dos entregables** sobre el Trabajo Práctico final de la materia *Gestión de Desarrollo de Sistemas Informáticos* (FIUBA), para el producto **Rocket Lease**:

1. Un **artefacto HTML** de presentación: un único archivo autocontenido, dinámico, disruptivo, interactivo y moderno, que se pase como una presentación de diapositivas (avanzar/retroceder con un click o una tecla).
2. Un **guión tentativo** en Markdown que acompañe la exposición, diapositiva por diapositiva, asignando quién habla y cuánto tiempo.

## Contexto y materiales

Antes de producir nada, **leé todos estos archivos** y citá en tus notas las partes que vas a usar (estructura, datos, reglas de marca). No hagas afirmaciones sobre el contenido sin haber abierto el archivo.

Todo vive bajo la carpeta `presentacion/` (las rutas de abajo son relativas a la raíz del repo `Rocket Lease`). La jerarquía es:

```
presentacion/
├── presentacion_rocket_lease.html          ← ENTREGABLE 1 (lo creás vos)
├── guion_presentacion.md                   ← ENTREGABLE 2 (lo creás vos)
├── prompting/
│   ├── PROMPT_presentacion.md              (este prompt)
│   ├── presentacion_final.md
│   ├── material_complementario.txt
│   └── official-antrhopic-prompting-guide.md
└── material/
    ├── artefactos/      Artefactos_2026-04-15.pptx · _2026-05-06.pptx · _2026-05-12.pptx · Artefactos_RocketLease.xlsx
    ├── diseño/          BRAND.md · DESIGN.md · Logo.png
    ├── imagenes_riesgos/  Riesgos_Sprint1.png … Riesgos_Sprint6.png
    └── workflow-ia/     WORKFLOW.md
```

<documentos>
  <documento ruta="presentacion/prompting/presentacion_final.md">
    Estructura canónica de la presentación: secciones, orden, duraciones, tonalidad por
    sección, artefactos a cubrir y el flujo de la demo paso a paso con sus roles
    (Conductor C, Rentador R, Administrador A). Es la fuente de verdad de la estructura.
  </documento>
  <documento ruta="presentacion/prompting/material_complementario.txt">
    Guía de qué es cada material y cómo usarlo. Léela primero como índice.
  </documento>
  <documento ruta="presentacion/material/diseño/BRAND.md">
    Brand guidelines (identidad, tono de voz, paleta, tipografía, componentes, animaciones).
  </documento>
  <documento ruta="presentacion/material/diseño/DESIGN.md">
    Design System ("Noche violeta confiable"): tokens, reglas con nombre, do's & don'ts.
  </documento>
  <documento ruta="presentacion/material/diseño/Logo.png">
    Logo oficial de Rocket Lease (símbolo "R" + cohete sobre violeta). Usalo en la portada y
    en el chrome; preferí embeberlo (data-URI base64) para mantener el HTML autocontenido.
  </documento>
  <documento ruta="presentacion/material/workflow-ia/WORKFLOW.md">
    Workflow de interacción con la IA para desarrollar las user stories. Insumo de la
    sección "Workflow de desarrollo junto con inteligencia artificial".
  </documento>
  <documento ruta="presentacion/material/imagenes_riesgos/Riesgos_Sprint1.png … Riesgos_Sprint6.png">
    Estado de los riesgos por sprint (imágenes). Revisalas todas y armá la cronología /
    evolución global. OJO: Riesgos_Sprint1 aplica cambios sobre la base que está en
    presentacion/material/artefactos/Artefactos_2026-05-06.pptx.
  </documento>
  <documento ruta="presentacion/material/artefactos/Artefactos_2026-04-15.pptx, _2026-05-06.pptx, _2026-05-12.pptx">
    Avances de los artefactos de gestión PREVIOS al desarrollo técnico. Úsalos para mostrar
    la interacción con la IA al construir los artefactos (User Story Mapping antes/después, etc.).
  </documento>
  <documento ruta="presentacion/material/artefactos/Artefactos_RocketLease.xlsx">
    Excel donde cada pestaña es un artefacto (User Stories, Cronograma, Sprints, Avance,
    Riesgos, etc.). Es la FUENTE DE DATOS DURA para sprints, story points, burn-up/down,
    planificado vs realizado y estimaciones. IMPORTANTE: verificá que el archivo exista en
    el repo. Si NO lo encontrás, frená y pedímelo antes de graficar nada con números; no
    inventes ni estimes cifras (ver regla de fidelidad de datos).
  </documento>
</documentos>

Citá primero lo relevante de cada documento (entre `<citas>`) y recién después construí. Para los `.pptx` y `.xlsx`, extraé el contenido con las herramientas disponibles; si un formato no se puede leer directamente, decímelo en lugar de adivinar su contenido.

## Entregable 1 — Artefacto HTML

Creá un único archivo `presentacion/presentacion_rocket_lease.html`, autocontenido (HTML + CSS + JS embebidos; sin build, sin dependencias que requieran servidor). Puede usar CDNs para fuentes (Poppins) y, si hace falta para gráficos, una librería liviana vía CDN — preferí JS vanilla o SVG propio antes que sumar peso.

Incluí tantas features e interacciones relevantes como puedas. Andá más allá de lo básico: es una entrega final que se presenta en vivo ante un tribunal, tiene que sorprender y leerse impecable en proyector.

### Navegación (requisito central: "fácil de pasar")
- Avanzar/retroceder con **flecha derecha/izquierda**, **barra espaciadora** (avanzar) y **click** (zonas izquierda/derecha o botones visibles).
- Una diapositiva visible a la vez, transición horizontal suave (slide + fade).
- **Indicador de progreso** (barra superior o dots) y **contador** "n / total".
- **Vista overview** (tecla `O` o `Esc`): grilla de miniaturas para saltar a cualquier slide.
- **Deep-linking por hash** en la URL (`#slide-7`) para retomar donde quedó.
- Soporte de **teclado completo** (Home/End para primera/última). Indicá los atajos en una ayuda accesible con `?`.
- Responsive a 16:9 de proyector; legible a 3-4 metros (tamaños generosos, contraste alto).

### Estructura de slides (espejá `presentacion_final.md`, en este orden)
1. **Portada**: título, materia, FIUBA, el logo de Rocket Lease (`presentacion/material/diseño/Logo.png`), los 6 integrantes (Juan Manuel Dalmau, Francisco López Tancredi, Mariano Merlinsky, Ezequiel Pérez Adamo, Aizen Sánchez, Santino Zucconi) y agenda (Introducción · Demo · Gestión del Proyecto · Conclusiones).
2. **Introducción (~4 min)** — tono inspirador, "venta a inversores": Product Vision, Personas, Es/No Es/Hace/No Hace, y Features con la **correlación personas↔features según su valoración**. Que dé ganas de usar la app.
3. **Demo (~10 min)** — guía visual del flujo de 18 pasos con los tres roles (C/R/A) y las acciones en paralelo (las separadas por `|||`). No es la app real corriendo: es el soporte visual que ordena la demo (pasos, rol activo, qué mirar, ej. "dejar mapa abierto", "mostrar impacto en mapa").
4. **Gestión del Proyecto** — un slide (o grupo) por artefacto, en este orden: Plan de comunicación · User Story Mapping (antes/después con la IA) · User Stories (las más pesadas; estimación por todo el equipo con Poker Planning en Fibonacci) · Cronograma (resumen por sprint: # de historias, story points, resumen funcional, con gráficos) · Workflow de desarrollo con IA · Sprints (**Burn-Up y Burn-Down globales consolidando los 7 sprints, con datos concretos del artefacto**) · Avance (Planificado vs Realizado y Planificado acumulado vs Realizado acumulado) · Riesgos (evolución global con **doble-click interactivo en cada riesgo** para ver su detalle/historia).
5. **Cierre** — reflexivo, profundo y alentador: Lessons Learned (hay 3 en el material; **proponé al menos 2 más** coherentes con el proyecto) y conclusiones personales del equipo.

### Interactividad mínima exigida
- **Riesgos**: vista de evolución global y, al hacer **doble-click** sobre un riesgo, abrir su ficha (descripción, severidad/probabilidad por sprint, mitigación, estado final).
- **Gráficos con datos reales** del xlsx: Burn-Up/Down global (7 sprints consolidados), Planificado vs Realizado y acumulados. Animá la entrada de los gráficos al llegar al slide.
- **User Story Mapping antes/después**: un toggle/slider que compare el mapa pre-IA vs post-IA.
- Micro-interacciones con propósito (hover/active), no decorativas.

### Sistema de marca — usá la dirección concreta de Rocket Lease (NO la house style por defecto)
Aplicá fielmente `BRAND.md` y `DESIGN.md`. Es dark-premium violeta, no cream/serif editorial.
- **Fondo** base `#0D0D1A`; superficies por luminosidad `#13131F` / `#1A1A2E` / `#222238`.
- **Violeta de marca** `#7C3AED` (hover `#6D28D9`) **solo en lo accionable/destacado** (≤10% de cada pantalla; "The One Accent Rule").
- **Acentos por rol** bloqueados: **cian `#06B6D4` = Conductor/Cliente**, **ámbar `#F59E0B` = Rentador**. Usalos para distinguir los roles en la demo. Un acento en el rol equivocado es un bug.
- **Tipografía única Poppins** (400/500/600/700), escala y tracking `-0.02em` en headings.
- Radios: pill `9999px` para CTAs/badges, `12px` para cards/inputs de UI, `24px` para cards image-led.
- **Animaciones**: ease-out fuerte (`cubic-bezier(0.23,1,0.32,1)`), 150–300ms, pocas pero memorables; respetá `prefers-reduced-motion` obligatoriamente.
- Semánticos (success/warning/error/info) solo para estado real, no decoración.
- Reglas que NO podés violar: nada de gradient text, nada de eyebrows uppercase tracked sobre cada sección, no anidar cards, no inventar un cuarto color de identidad, no combinar border 1px + shadow blur grande en la misma card.

<frontend_aesthetics>
NUNCA uses estéticas genéricas de IA: fuentes sobreusadas (Inter, Roboto, Arial, system fonts), gradientes violeta-sobre-blanco tipo SaaS, layouts y componentes predecibles, diseño cookie-cutter sin carácter. La identidad ya está definida por BRAND.md/DESIGN.md: ejecutala con personalidad, cohesión y micro-interacciones cuidadas.
</frontend_aesthetics>

## Entregable 2 — Guión

Creá `presentacion/guion_presentacion.md`. Es el texto que el equipo dice mientras pasa los slides.
- Estructurado **por slide** (numerado igual que el HTML), con: **quién habla**, **duración objetivo** y el **texto sugerido** + notas de "qué mostrar en pantalla / qué clickear".
- Respetá el **presupuesto de tiempo** por sección: Introducción ~4 min, Demo ~10 min, más Gestión y Cierre; sumá un total aproximado y repartí coherentemente.
- En la demo, marcá las acciones en paralelo (C/R/A) y los hitos visuales (ej. "A deja el mapa abierto", "C navega → A muestra el impacto en el mapa en vivo").
- **Tono según `BRAND.md`**: introducción inspiradora y vendedora; gestión precisa y orientada a datos; cierre reflexivo y alentador. Español rioplatense, imperativos claros ("Reservá", "Publicá tu auto"), sin tecnicismos innecesarios de cara al "cliente/inversor".
- Que sea tentativo y editable: frases naturales para decir, no párrafos rígidos para leer palabra por palabra.

## Reglas transversales (no negociables)

- **Fidelidad de datos**: usá DATOS CONCRETOS del `Artefactos_RocketLease.xlsx` y de las imágenes de riesgos. **No inventes ni estimes ningún número.** Si un dato no está disponible o el archivo no se puede leer, dejá un placeholder visible (`[DATO PENDIENTE: …]`) y avisámelo; no rellenes con cifras plausibles.
- **Idioma**: todo el contenido visible (HTML y guión) en **español rioplatense**.
- **Coherencia de roles/color** en toda la presentación (cian conductor, ámbar rentador, violeta marca).
- **Autocontenido**: el HTML debe abrir con doble-click en un navegador moderno, sin pasos extra. Si incluís imágenes de los riesgos, referencialas por ruta relativa o embebelas; documentá cuál elegiste.
- No agregues archivos temporales al repo; si creás scripts auxiliares para parsear el xlsx/pptx, eliminalos al terminar.

## Proceso sugerido

1. Leé `material_complementario.txt` y `presentacion_final.md` para fijar el alcance.
2. Leé `BRAND.md` y `DESIGN.md`; extraé los tokens a variables CSS.
3. Extraé datos del `.xlsx` y contenido de los `.pptx`; armá la cronología de riesgos desde las 6 imágenes (base en `Artefactos_2026-05-06.pptx`).
4. Consolidá los 7 sprints para Burn-Up/Down y los gráficos de avance, **citando de dónde sale cada número**.
5. Construí el HTML, después el guión alineado a los mismos slides.
6. Antes de cerrar, verificá: navegación por teclado y click funciona; hash de URL; doble-click en riesgos; gráficos con datos reales (no inventados); marca aplicada; `prefers-reduced-motion`; legibilidad en 16:9. Reportame un resumen breve de lo hecho y de cualquier `[DATO PENDIENTE]`.

Cuando termines, dejá un resumen conciso de ambos entregables y de los supuestos que tomaste.
