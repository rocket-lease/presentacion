# Guión de presentación — Rocket Lease

**Materia:** Gestión de Desarrollo de Sistemas Informáticos · FIUBA · Grupo 16
**Soporte visual:** `presentacion_rocket_lease.html` (avanzar con `→` / barra espaciadora / click en la zona derecha)
**Duración total objetivo:** ~26 min · Introducción ~4' · Demo ~10' · Gestión ~9' · Cierre ~2,5'

> Este guión es **tentativo y editable**: son frases para *decir*, no para *leer palabra por palabra*. Cada slide indica **quién habla**, **cuánto** y **qué mostrar / clickear**.

**Equipo (referencia de roles en la exposición):**

| Integrante | Rol en la presentación |
|---|---|
| Juan Manuel Dalmau | Apertura, visión, cronograma y cierre |
| Francisco López Tancredi | Personas, alcance, User Stories |
| Mariano Merlinsky | Features, plan de comunicación, USM |
| Ezequiel Pérez Adamo | Conduce la demo (Administrador) · Sprints/Avance |
| Aizen Sánchez | Conductor en la demo · Riesgos |
| Santino Zucconi | Rentador en la demo · Workflow IA · Lessons |

**Atajos útiles durante la exposición:** `O` o `Esc` = vista general (miniaturas) · `?` = ayuda · doble-click en un riesgo = ficha · números `1-6` = saltar de sección.

---

## SECCIÓN 1 — INTRODUCCIÓN (~4 min)
*Tono: inspirador, "venta a inversores". Imperativos claros. Que dé ganas de usar la app.*

### Slide 1 · Portada — **Juan Manuel** — 0:30
> "Buenas. Somos el Grupo 16 y les traemos **Rocket Lease**: el marketplace que pone tu próximo auto a un toque de distancia, y que convierte cualquier flota en un negocio. En los próximos minutos los llevamos por la visión del producto, una demo en vivo, cómo lo gestionamos, y qué nos llevamos."
- **Mostrar:** portada con los 6 integrantes y la agenda (Introducción · Demo · Gestión · Conclusiones).

### Slide 2 · Product Vision — **Juan Manuel** — 1:00
> "El problema es viejo: alquilar un auto es repetir datos, no saber si hay disponibilidad y firmar seguros que nadie entiende. Del otro lado, las rentadoras cambian precios a mano, auto por auto. **Rocket Lease conecta las dos puntas** con transparencia total: el cliente busca, compara, **reserva y paga** sin letra chica; la rentadora **publica, gestiona y promociona** con métricas accionables. No somos otro AVIS: somos un ecosistema completo —precios dinámicos, contrato claro, accesibilidad y un sistema de reputación que premia la confianza."
- **Mostrar:** la frase de visión y los tres pilares (mobile-first / cliente / rentadora). Señalar el badge "Diferente a AVIS".

### Slide 3 · Personas — **Francisco** — 1:15
> "No diseñamos para 'un usuario'. Diseñamos para necesidades reales. **Julián** viaja por trabajo y quiere reservar en dos clicks. **Sofía** alquila por primera vez y necesita entender qué firma. **Martín** solo maneja automático y hoy ninguna app lo deja filtrar por eso. **Tomás** no tiene tarjeta de crédito. Y del lado de la oferta, **Lucas** y **Carmen** manejan flotas de 20 y 350 autos que necesitan destacar. Rocket Lease gana **justo donde los demás excluyen**."
- **Mostrar:** las 6 tarjetas de personas. Pasar el cursor por Martín y Tomás al nombrarlos (se elevan).
- **Color:** azul cian = conductores, ámbar = rentadores.

### Slide 4 · Es / No es / Hace / No hace — **Francisco** — 0:45
> "Foco. **Es** una plataforma de alquiler y de gestión de flota. **No es** compraventa, ni aseguradora, ni un Uber. **Hace** todo el ciclo: verificación, contrato digital, reserva con control de concurrencia, pagos y reputación. Y deliberadamente **no hace** mantenimiento ni emite pólizas. Un alcance claro es lo que nos dejó construir algo sólido."
- **Mostrar:** las 4 columnas. Rematar con la línea de abajo (responsabilidad al rentador en caso de choque).

### Slide 5 · Features ↔ Personas — **Mariano** — 1:15
> "¿Cómo sabemos qué construir primero? Cruzamos **cada feature con la valoración de cada persona**, del 1 al 5. Y aparece un patrón hermoso: hay un **núcleo que todos puntúan 5** —registro, pagos, reserva— y después un **diferencial por persona**. Miren a Julián: lo enamora la re-reserva y los niveles. A Sofía, el contrato claro y el desglose de costos. A Carmen, la edición masiva de precios. Una base universal, y un gancho para cada uno."
- **Mostrar / clickear:** ir tocando 2-3 personas en la columna izquierda (Julián → Sofía → Carmen). Las barras se animan con los puntajes reales. Señalar el "Núcleo común" abajo.

---

## SECCIÓN 2 — DEMO (~10 min)
*Tono: dinámico. Es el soporte visual que ordena la demo en vivo. Tres operadores en paralelo.*
*Reparto en pantalla: **Conductor (C) = Aizen** · **Rentador (R) = Santino** · **Administrador (A) = Ezequiel** (coordina y narra).*

### Slide 6 · Demo · Roles — **Ezequiel** — 0:45
> "Ahora lo vemos funcionar. Tres personas operando **al mismo tiempo**: el **Conductor** que alquila —en cian—, el **Rentador** que publica —en ámbar—, y el **Administrador**, que es la plataforma —en violeta—. Cuando vean dos colores juntos, es porque están pasando cosas en paralelo. Arrancamos."
- **Mostrar:** la leyenda de colores y los números clave (18 pasos, 7 acciones en paralelo, ~10').

### Slide 7 · Demo · Flujo de 18 pasos — **Aizen + Santino + Ezequiel** — 9:00
> *(Ezequiel coordina. A medida que ejecutan en la app real, este slide acompaña: tocar cada paso despliega "qué mirar".)*

**Fase 1 · Setup de la plataforma**
- **(A) Ezequiel** — "Entro como administrador y abro el **mapa de precios dinámicos**. **Lo dejo abierto**: en un minuto va a cobrar sentido." *(pasos 1-2)*
- **(R) Santino** — "Entro como rentador, **publico un auto nuevo** —precio, características, fotos, documentación— y le **asigno un set de reglas** que ya tenía armado." *(pasos 3-5)*

**Fase 2 · Búsqueda y reserva**
- **(C) Aizen** — "Entro como conductor. **Busco, filtro y guardo favoritos**." *(paso 6-7)*
- **∥ HITO:** mientras Aizen navega, **Ezequiel muestra en el mapa cómo se actualiza el impacto en vivo** *(paso 7 — "C navega → A muestra el impacto en el mapa")*.
- **(C) Aizen** — "Entro a un auto, veo el **desglose de costos** y **reservo**: control de concurrencia y **voucher con QR**." *(pasos 8-9)*

**Fase 3 · Uso del vehículo** *(acciones espejo C ∥ R)*
- **(C) Aizen ∥ (R) Santino** — "**Chateamos** para coordinar la entrega." *(paso 10)*
- "**Entrego / recibo el auto** leyendo el QR —se formaliza el inicio—." *(paso 11)*
- "**Devolución / recepción**: se cierra el ciclo." *(paso 12)*
- "Y nos **reseñamos** mutuamente, 1 a 5." *(paso 13)*

**Fase 4 · Incidente**
- **(C) Aizen** — "Algo salió mal: **reporto un problema**." *(paso 14)*
- **(A) Ezequiel** — "El reclamo me llega a la **cola de tickets**." *(paso 15)*

**Fase 5 · Resolución**
- **(A ∥ C ∥ R)** — "Nos comunicamos los tres **por el mismo ticket**." *(paso 16)*
- **(A) Ezequiel** — "**Cierro el ticket aplicando el impacto** sobre el conductor o el rentador." *(paso 17)*
- **∥ HITO final:** **Aizen y Santino ven en vivo cómo cambió su reputación/estado** *(paso 18 — "Visualizar impacto")*.

> **Cierre de demo (Ezequiel):** "Eso es Rocket Lease de punta a punta: publicar, reservar, usar, resolver. Todo conectado."
- **Notas de pantalla:** ir tocando los pasos para mostrar el "qué mirar" en violeta. Recordar el hito del mapa (paso 7) y el del impacto final (paso 18).

---

## SECCIÓN 3 — GESTIÓN DEL PROYECTO (~9 min)
*Tono: preciso, orientado a datos. Acá mostramos cómo lo construimos.*

### Slide 8 · Plan de comunicación — **Mariano** — 0:45
> "Detrás de la app hay un **ritmo semanal**. Daily async por WhatsApp; Sprint Planning, Mid-Sprint y Pre-Demo por Discord; y el hito de cada semana: la **Demo + Status report con el PO**, donde repasamos alcance, métricas, riesgos y costos, y definimos el sprint siguiente."
- **Mostrar:** la tabla del plan de comunicación. Señalar la fila de la Demo con el PO.

### Slide 9 · User Story Mapping — **Mariano** — 1:15
> "El User Story Mapping lo construimos **junto con la IA**, y la evolución es clara. **Al principio** teníamos listas sueltas de features, palabras ambiguas, sin un backbone real. La IA nos explicó la estructura, detectó huecos —reservas, pagos, disputas, métricas— y nos llevó **al después**: dos mapas bien armados, uno para el conductor y otro para el rentador, listos para definir el MVP."
- **Clickear:** arrancar en **"Antes"** (chips sueltos + problemas) y **tocar "Después (con IA)"** para revelar los dos backbones. Es el momento del toggle.

### Slide 10 · User Stories pesadas — **Francisco** — 1:00
> "El backlog terminó en **65 historias** y **290 story points**. Estimamos **entre todo el equipo, con Poker Planning y Fibonacci** —no para acertar el número, sino para que discrepar nos obligue a entender la historia. Las más pesadas, de 13 puntos: el **mapa interactivo**, los **precios dinámicos**, el **sistema de tickets**, la **reputación** y las **recomendaciones**."
- **Mostrar:** la lista de las US de 13 y 8 puntos y la secuencia Fibonacci. Señalar los totales 65 / 290 / 7.

### Slide 11 · Cronograma — **Juan Manuel** — 1:15
> "Siete sprints con una **curva de carga deliberada**: arranque tranquilo en los sprints 1 y 2 —fundaciones, cuenta y publicación—, **carga fuerte en el 3, 4 y 5** —mapa, pagos, dashboard y reputación— y un cierre liviano en el 6 y 7. De hecho, re-estimamos de **313 a 290 puntos** para balancearlo mejor."
- **Mostrar:** la tabla por sprint (US + SP + resumen) y el gráfico de barras de SP por sprint (se anima al entrar).

### Slide 12 · Workflow de desarrollo con IA — **Santino** — 1:00
> "Para implementar cada historia armamos un **workflow con IA**: refinamos la US, cargamos contexto, y un orquestador genera contracts, API y web en paralelo. Pero lo importante es el **embudo de revisión**: primero lo mecánico —¿pasa CI?—, después las convenciones, y al final el juicio: seguridad, performance, diseño. **La IA acelera el boilerplate; el equipo decide.**"
- **Mostrar:** los pasos del flujo y las 3 capas del funnel (mecánico → reglas → juicio).

### Slide 13 · Sprints · Burn-Up / Burn-Down — **Ezequiel** — 1:15
> "Consolidando los **7 sprints**, este es el pulso del proyecto. El **Burn-Up** muestra cómo el realizado acumulado fue trepando hasta **272 de 290 puntos**, pegado al plan. El **Burn-Down**, lo mismo desde el otro lado: el trabajo restante cayó de 290 a 18. Cerramos en **94%**: los 18 puntos del Sprint 7 —recomendaciones y push— quedaron como alcance no realizado."
- **Mostrar:** los dos gráficos (se animan al entrar). Señalar el techo de 290 en el Burn-Up.
- *(Datos: pestaña **Avance** del Excel.)*

### Slide 14 · Avance · Planificado vs Realizado — **Ezequiel** — 1:00
> "Acá se ve la **honestidad del proceso**. Por sprint: en el 5 **sub-entregamos** —44 de 57— y el **Sprint 6 absorbió ese carryover**, entregando 37 sobre 24 planificados. ¿El resultado? Para el cierre del Sprint 6 **lo acumulado real igualó al plan**: 272 contra 272. La curva real se mantuvo pegada a la planificada todo el proyecto."
- **Mostrar:** las barras Planificado vs Realizado y la curva acumulada. Señalar el cruce en el Sprint 6.

### Slide 15 · Riesgos · Evolución — **Aizen** — 1:30
> "Gestionamos **7 riesgos** sprint a sprint. Lo más interesante no es la foto final, sino el **movimiento**: el riesgo de **atrasos cruzó el umbral en el Sprint 4** y lo desactivamos; sumamos un riesgo **nuevo** —perder el acceso a los agentes de IA gratuitos— y lo bajamos; y tratamos las **oportunidades** como riesgos positivos: explotar la IA fue una decisión de gestión. Cerramos con casi todo **mitigado o cerrado**."
- **Clickear:** **doble-click en un riesgo** (por ejemplo R1 "Atrasos" o R5 "LLM") para abrir su **ficha** —causas, planes, evolución de la exposición y estado final—. Es la interacción estrella de esta sección.
- *(Datos: imágenes de riesgos por sprint + pestaña **Análisis de Riesgos**.)*

---

## SECCIÓN 4 — CIERRE (~2,5 min)
*Tono: reflexivo, profundo y alentador.*

### Slide 16 · Lessons Learned — **Santino** — 1:15
> "Nos llevamos cinco lecciones. Las tres que ya teníamos: la **IA es potente si está bien usada** —clave haber definido la metodología desde el día uno—; las **dinámicas de equipo** valen tanto como el código; y **planificar al detalle** evita casi todas las fallas. Y dos que sumamos: **el contrato primero** —acordar la API antes de codear desactivó el mayor riesgo técnico— y que **estimar juntos vale el tiempo** —discrepar es la señal de que falta entender algo—."
- **Mostrar:** las 5 tarjetas. Señalar las dos marcadas como **"PROPUESTA"** (4 y 5).

### Slide 17 · Cierre — **Juan Manuel** (+ una frase por integrante) — 1:15
> "No construimos solo una app: **construimos un método**. Siete sprints, seis personas frente al teclado, una sola dirección: hacia adelante. **272 de 290 puntos** entregados, **7 riesgos llevados a 2**, y **65 historias** con una sola visión. Con planificación, buen clima de equipo e IA bien usada, un grupo chico entrega como uno grande."
> *(Opcional: cada integrante cierra con una frase de 5 segundos sobre lo que se lleva del TP.)*
> "**¡Gracias! ¿Preguntas?**"
- **Mostrar:** slide de cierre con las métricas y la línea del equipo.

---

### Resumen de tiempos

| Sección | Slides | Objetivo |
|---|---|---|
| Introducción | 1–5 | ~4:00 |
| Demo | 6–7 | ~9:45 |
| Gestión del Proyecto | 8–15 | ~8:45 |
| Cierre | 16–17 | ~2:30 |
| **Total** | **17** | **~25:45** |

> **Tip de exposición:** si el tribunal pregunta por un dato puntual (un sprint, un riesgo), usá `O` para abrir la vista general y saltar directo al slide, o doble-click en el riesgo para su ficha. La URL guarda el slide (`#slide-13`), así que podés retomar donde quedaste.
