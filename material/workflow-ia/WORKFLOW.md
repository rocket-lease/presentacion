# WORKFLOW — Implementar una US end-to-end

Cómo se encadenan las skills y agents de `tools/` para llevar una User Story desde "viene de Trello" hasta "PR mergeado". Y, para cada herramienta, cuándo conviene usarla.

> Si solo querés la tabla de decisión y no leer el flujo: saltá a [Decision matrix](#decision-matrix).

---

## Flujo end-to-end de una US

```
  ┌─────────────────────────────────────────────────────────────┐
  │  US viene del backlog (planilla / Trello)                   │
  └────────────────────────────┬────────────────────────────────┘
                               │
                               ▼
  ┌─────────────────────────────────────────────────────────────┐
  │  1. /rocket-refine-us <N>                                   │
  │     Profesionaliza la US → PLAN-ATAQUE.md                   │
  │     (saltear si la US ya viene bien definida)               │
  └────────────────────────────┬────────────────────────────────┘
                               │
                               ▼
  ┌─────────────────────────────────────────────────────────────┐
  │  2. /rocket-context (1× por sesión, opcional)               │
  │     Carga glosario + decisiones + sprint actual             │
  └────────────────────────────┬────────────────────────────────┘
                               │
                               ▼
  ┌─────────────────────────────────────────────────────────────┐
  │  3. /rocket-us <N>                                          │
  │     Orquesta la implementación cross-repo:                  │
  │       contracts  →  checkpoint  →  api ∥ web                │
  │     Internamente delega/se apoya en:                        │
  │       • /rocket-contracts      (schemas Zod)                │
  │       • /rocket-api-module     (módulo NestJS)              │
  │       • /rocket-web-feature    (feature web)                │
  └────────────────────────────┬────────────────────────────────┘
                               │
                               ▼
  ┌─────────────────────────────────────────────────────────────┐
  │  4. /rocket-agent-test-writer <archivo>  (1× por archivo)   │
  │     Escribe tests del service/hook/componente recién hecho  │
  │     Corre en worktree aislado — podés seguir trabajando     │
  └────────────────────────────┬────────────────────────────────┘
                               │
                               ▼
  ┌─────────────────────────────────────────────────────────────┐
  │  5. /rocket-agent-consistency                               │
  │     Detecta drift contracts ↔ entity ↔ Prisma ↔ web         │
  │     (típicamente atrapa campos que faltaron en algún repo)  │
  └────────────────────────────┬────────────────────────────────┘
                               │
                               ▼
  ┌─────────────────────────────────────────────────────────────┐
  │  6. /rocket-check                                           │
  │     Corre gates mecánicos: tsc + lint + tests + build       │
  │     en los repos modificados                                │
  └────────────────────────────┬────────────────────────────────┘
                               │
                               ▼
  ┌─────────────────────────────────────────────────────────────┐
  │  7. /rocket-review                                          │
  │     Chequea convenciones del proyecto:                      │
  │       layer violations, $, fechas, i18n, TS strict, commits │
  └────────────────────────────┬────────────────────────────────┘
                               │
                               ▼
  ┌─────────────────────────────────────────────────────────────┐
  │  8. /rocket-agent-auditor                                   │
  │     Análisis profundo: security, performance, REST, DB,     │
  │     arquitectura cross-cutting, reusabilidad                │
  └────────────────────────────┬────────────────────────────────┘
                               │
                               ▼
  ┌─────────────────────────────────────────────────────────────┐
  │  Hook stop-checklist se dispara automáticamente             │
  │  → commit + PR                                              │
  └─────────────────────────────────────────────────────────────┘
```

Los pasos 4–8 se pueden saltear o reordenar según el caso, pero el orden 6 → 7 → 8 vale como funnel: lo barato y mecánico primero, lo caro y de juicio al final.

---

## Decision matrix

### Implementar (escribir código)

| Quiero… | Skill | Tipo |
|---|---|---|
| Profesionalizar una US mal definida | `/rocket-refine-us <N>` | inline |
| Implementar una US punta a punta (3 repos) | `/rocket-us <N>` | orquestador (spawnea api+web en paralelo) |
| Agregar un schema Zod aislado (sin US completa) | `/rocket-contracts <recurso>` | inline |
| Crear un módulo NestJS aislado | `/rocket-api-module <nombre>` | inline |
| Crear una feature web aislada | `/rocket-web-feature <nombre>` | inline |
| Escribir tests para un service/hook/componente | `/rocket-agent-test-writer <ruta>` | subagent (worktree) |

### Verificar (leer código sin tocar)

| Quiero… | Skill | Capa |
|---|---|---|
| Cargar contexto del dominio | `/rocket-context [dominio\|arch\|sprint]` | leer docs |
| Detectar drift cross-repo | `/rocket-agent-consistency [quick]` | subagent (Explore, read-only) |
| Verificar gates: tsc + lint + tests + build | `/rocket-check [repo]` | gates mecánicos |
| Chequear convenciones del proyecto | `/rocket-review [repo]` | reglas duras (pattern-based) |
| Análisis profundo (security/perf/arch/REST) | `/rocket-agent-auditor` | juicio (subagent) |

### Tooling meta

| Quiero… | Skill |
|---|---|
| Exportar las skills a otro asistente | `/rocket-adapt <cursor\|copilot\|cline\|...>` |

---

## Las tres capas de review (funnel)

Las tres skills de revisión NO son redundantes — cada una atrapa cosas distintas. Corrélas en orden:

```
/rocket-check       — ¿pasa CI?              ejecuta comandos, exit code
       │
       ▼
/rocket-review      — ¿respeta convenciones? grep + reglas duras del proyecto
       │
       ▼
/rocket-agent-auditor — ¿está bien diseñado?  razonamiento sobre múltiples archivos
```

**Ejemplos concretos de qué cae en cuál:**

| Problema | Lo atrapa |
|---|---|
| `pnpm test` falla | `rocket-check` |
| `let x: any` en el código | `rocket-review` |
| `Service` que importa `PrismaService` | `rocket-review` |
| `formatMoney(1500)` con número pelado | `rocket-review` |
| Loop con N queries adentro (N+1) | `auditor` |
| `POST /reservations` sin `Idempotency-Key` | `auditor` |
| `useReservas` 90% duplicado de `useOwnerReservations` | `auditor` |
| Input del body llega a una query `raw` sin parametrizar | `auditor` 🔴 |
| Falta índice en `reservations.vehicle_id` | `auditor` |

El auditor **asume** que las dos capas anteriores ya corrieron — no re-chequea `any` ni layer violations. Se enfoca en lo que requiere juicio.

---

## Skills inline vs subagentes — diferencia operativa

| Tipo | Carpeta | Cómo corre | Cuándo conviene |
|---|---|---|---|
| Skill inline | `tools/skills/` | en tu contexto principal | tareas chicas/rápidas o que necesitás ver paso a paso |
| Subagente | `tools/agents/` | contexto aislado, vos solo recibís el reporte | tareas que leen muchos archivos o que querés correr en paralelo |

Los archivos en ambas carpetas se llaman `SKILL.md` y se instalan en el mismo lugar (`~/.claude/skills/`) — la carpeta solo expresa intención organizativa. Lo que cambia es **qué hace el contenido del SKILL.md**: una skill inline contiene instrucciones que vos seguís; una de `agents/` contiene instrucciones que terminan en "spawnear un subagente con este prompt".

---

## Cuándo NO usar una skill

Hay casos en que ir directo es más rápido:

- **Tarea de 1 archivo y vos sabés qué hacer**: editá. No invoques `/rocket-web-feature` para agregar un botón.
- **Bugfix puntual**: no necesitás `/rocket-us`. Hacé el cambio + `/rocket-check` antes de commitear.
- **Exploración o lectura**: ninguna skill. Leé y listo.
- **Cuando una skill no te encaja al 100%**: mejor ir a mano que pelearte con el flujo. Después, si el caso se repite, actualizá la skill.

---

## Reglas para no generar redundancia al sumar skills

1. **Toda skill nueva declara `## Scope` y `## Out of scope`** en su SKILL.md. Si no podés escribir el "out of scope" sin pisar a otra skill existente, parála: o estás duplicando, o tenés que delegar.

2. **Las skills "grandes" delegan a las chicas, no reimplementan.** Si `/rocket-us` necesita scaffolding de un módulo NestJS, debe apuntar a `/rocket-api-module`, no copiar sus instrucciones inline. Cuando cambia la convención, se actualiza en un solo lugar.

3. **Capas de review no se mezclan.** Cada una con su nivel de análisis. Mecánico, reglas, juicio. No metas reglas de juicio en `rocket-review`, no metas chequeos mecánicos en el auditor.

4. **Si dos skills caen en la misma celda de la decision matrix**, una de las dos sobra o tienen que fusionarse.

5. **Antes de agregar una skill nueva, revisar esta tabla** y ver dónde encaja. Si no encaja en ninguna celda, agregá una fila nueva. Si encaja en una celda ya ocupada, parate y reconsiderá.

---

## Referencias

- Convenciones cross-repo: `api/docs/CONVENTIONS.md`
- Glosario de dominio: `api/docs/CONTEXT.md`
- Decisiones arquitectónicas: `api/docs/DECISIONS.md`, `api/docs/adr/`
- Contexto cargado en cada sesión: `tools/CLAUDE.md`
- Listado completo de skills + hooks: `tools/README.md`
- Skills experimentales (no auto-instaladas): `tools/experimental/README.md`
