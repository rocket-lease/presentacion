---
id: presentacion
aliases: []
tags: []
---

## Estructura de la presentacion (24 min total)

- **Intro comercial** (~4 min): Product Vision, Personas, E/NE/H/NH, Features ↔ Personas
- **Demo** (~10 min): 18 pasos en vivo con 3 roles
- **Proceso de desarrollo** (~8 min): Metodologia con IA, Sprints, Artefactos, Riesgos, Lessons Learned
- **Cierre y preguntas** (~2 min): Conclusiones y Q&A

# Rocket Lease

## Que es Rocket Lease?

- Problematica
    - Identificamos la necesidad de una plataforma centralizada que conecte oferta y demanda de alquiler de vehiculos, con transparencia en precios y condiciones.

- Solucion
    - Desarrollamos un marketplace mobile-first de alquiler de vehiculos que conecta rentadores con clientes finales, integrando gestion de flota, pagos, un sistema de reputacion y niveles con beneficios.

- Demo
    - Realizamos una demo en vivo con 3 roles operando en paralelo: Conductor (C), Rentador (R), Administrador (A)
    - 18 pasos en 5 fases:
        - Fase 1 — Setup de la plataforma (login, mapa de precios, publicacion de auto)
        - Fase 2 — Busqueda y reserva (filtros, desglose de costos, voucher QR)
        - Fase 3 — Uso del vehiculo (chat, entrega/recepcion con QR, resena mutua)
        - Fase 4 — Incidente (reporte de problema, cola de tickets)
        - Fase 5 — Resolucion (comunicacion tripartita, cierre con impacto, cambio de reputacion)
    - Hito visual: mapa de precios dinamicos abierto toda la demo, actualizandose en vivo
    - Duracion: ~10 minutos

## Metodologia de trabajo

### Integracion con IA

Todo esto fue posible gracias a que las primeras semanas nos dedicamos a implementar un workflow con IA que potencie nuestro desarrollo

Este workflow se puede dividir en tres partes:
1. En la primer parte se hace un refinamiento de la historia de usuario que vayamos a implementar. Este refinamiento nos permite ver gaps existentes en los criterios de aceptacion y se hace mediante un ping pong de preguntas y respuestas que, junto con el contexto del proyeto, culmina en un documento que sirve como requerimiento tecnico para implementar dicha historia.
2. En la segunda parte se pasa al desarrollo. En este, la IA arranca generando los contratos entre el back y el front y pide por confirmacion humana. Una vez hecho esto, se lanzan dos agentes en paralelo que modifican tanto el back como el front de acuerdo a lo definido en la etapa anterior.
- Una vez tenido el codigo, la IA toma los criterios de aceptacion y los transforma en test de aceptacion que son ejecutados con la herramienta Cucumber.
3. En la tercera y ultima etapa se audita el rendimiento, la seguridad y las buenas practicas en el codigo

### Sprints

- Sprint Goals definidos:
    - Sprint 1: Loguearse y gestion de vehiculos
    - Sprint 2: Reservar vehiculos
    - Sprint 3: Verificaciones de documentos y gestion de pagos/precios
    - Sprint 4: Cancelaciones de reservas y reporte de problemas
    - Sprint 5: Precios dinamicos segun oferta/demanda y dashboard de metricas para el rentador
    - Sprint 6: Sistema de niveles con beneficios y resolucion de disputas
    - Sprint 7: Recomendaciones de autos personalizadas segun historial y preferencias

### Artefactos

- Explicar cada artefacto y en que nos ayudaron:
    - Alcance y objectivo
        - E/NE/H/NH
            - Nos sirvio para entender y definir bien el alcance que tiene nuestro producto 
            - (ejemplo de los seguros) TBD
        - Personas
            - Nos sirvio para entender bien el flujo que deberia tener nuestro producto desde distintos puntos de vistas de nuestros clientes
        - Product Vision
            - Nos ayudo a contrastar nuestra idea con algunos productos ya existentes y poder definir nuestro diferencial
        - USM
            - Nos ayudo mucho a ordenar y desglosar los flujos que tiene nuestra aplicacion, para posteriormente definir y priorizar las tareas a llevar a cabo para poder desarrollar nuestro producto

    - Organizacion
        - Backlog
            - Definimos 65 User Stories con 290 Story Points estimados
            - Estimamos con Poker Planning usando secuencia Fibonacci, participando todo el equipo
            - Distribuidas en 7 sprints
            - Nos permitio visualizar la carga total del proyecto y priorizar con criterio compartido
        - Cronograma
            - Planificamos 7 sprints con curva de carga deliberada: arranque tranquilo (S1-S2, fundaciones), carga fuerte (S3-S5, mapa, pagos, dashboard, reputacion), cierre liviano (S6-S7)
            - Nos ayudo a balancear la carga entre sprints y a absorber carryover sin descarrilar el proyecto
        - Riesgos

### Riesgos

- Gestionamos 7 riesgos a lo largo del proyecto, monitoreando su exposicion sprint a sprint
- Ejemplos destacados:
    - R1 "Atrasos" — cruzo el umbral en el Sprint 4 y lo desactivamos
    - R5 "LLM" — riesgo de perder acceso a agentes de IA gratuitos; lo mitigamos y lo cerramos
- Las oportunidades las tratamos como riesgos positivos (ej: explotar IA como ventaja competitiva)
- Estado final: casi todos mitigados o cerrados, quedando 2 riesgos activos al cierre
- Interaccion: doble-click sobre cada riesgo en la presentacion para ver su ficha (causas, plan, evolucion, estado final)
- Nos obligo a monitorear proactivamente lo que podia salir mal, no solo a reaccionar cuando pasaba

### Lessons Learned

- Workflows con agentes de IA personalizados — la IA es potente si esta bien usada.
    - Definir la metodologia desde el dia uno fue clave para que el agente aportara valor real y no ruido

- Importancia de planificar al detalle — planificar al detalle evito casi todas las fallas. 
    - Las pocas que tuvimos surgieron justo de lo que no habiamos planificado 
        - dependencias entre historias
        - scope distintos entre historias (por ejemplo, crear vehiculo / borrar, editar y obtener un vehiculo )

- Importancia de gestionar y mantener actualizados los riesgos
    - Tuvimos un riesgo que no pudimos identificar a tiempo: Copilot AI redujo su limite mensual drasticamente
        - Pudimos contenerlo (por suerte) al pasarnos a otro modelo gratuito, pero se vio afectado el desarrollo ya que veniamos utilizandolo para el desarrollo agentico
        - Lo mismo nos pudo haber pasado con el nuevo modelo gratuito, por lo que lo agregamos como riesgo

- Aplicacion de dinamicas de equipo adecuadas — las dinamicas de equipo valen tanto como el codigo. 
    - El clima del grupo fue lo que sostuvo el ritmo durante 7 sprints

- Re-estimar es reconocer que entendés mejor el problema que cuando lo planificaste por primera vez. 
    - En la práctica, muchos equipos tratan las estimaciones iniciales como un contrato fijo y cualquier ajuste lo viven como un desvío.
    - Pero la realidad es que al empezar un proyecto sabés poco, y a medida que desarrollás entendés más: aparecen complejidades que no viste, otras que creías complejas resultan triviales, y los números iniciales inevitablemente se desactualizan.
    - El valor de la re-estimación no está en "acercarse al número correcto", sino en forzar al equipo a revisar periódicamente si lo que pensaba sigue siendo cierto. 
    - Ese hábito —cuestionar las propias estimaciones con los datos que ya tenés— es más valioso que cualquier cifra que salga de la reunión.

## Preguntas

- Espacio para preguntas del tribunal
