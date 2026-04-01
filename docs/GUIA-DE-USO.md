# Guia de Uso — Doc Agent

## Que son PRD, RFC y SDD?

### PRD (Product Requirements Document)
Documento de requisitos de producto. Define **que** se va a construir y **por que**.

Responde preguntas como:
- Cual es el problema que estamos resolviendo?
- Quienes son los usuarios objetivo?
- Cuales son las user stories y requisitos funcionales/no funcionales?
- Como medimos el exito?

**Audiencia principal:** Product Managers, stakeholders, equipo de desarrollo.

---

### RFC (Request for Comments)
Documento de propuesta tecnica. Define **como** se va a resolver un problema tecnico especifico y busca consenso del equipo antes de implementar.

Responde preguntas como:
- Cual es el problema tecnico actual?
- Que solucion se propone y que alternativas se consideraron?
- Cual es el impacto en el sistema, el equipo y los usuarios?
- Como se hace rollback si algo falla?

**Audiencia principal:** Equipo tecnico, Tech Leads, arquitectos.

---

### SDD (Software Design Document)
Documento de diseno de software. Define la **arquitectura y el diseno tecnico detallado** de la solucion.

Responde preguntas como:
- Que arquitectura y patrones se usan?
- Cuales son los modulos, entidades y flujos principales?
- Como se modelan los datos?
- Que APIs se exponen?
- Cual es la estrategia de testing, seguridad y observabilidad?

**Audiencia principal:** Desarrolladores, Tech Leads, DevOps.

---

## Orden de ejecucion

```
PRD  →  RFC  →  SDD
(que)   (como decidimos)   (como construimos)
```

| Paso | Documento | Proposito |
|------|-----------|-----------|
| 1 | **PRD** | Definir el problema, los usuarios, los requisitos y los criterios de exito |
| 2 | **RFC** | Proponer la solucion tecnica, evaluar alternativas y buscar consenso |
| 3 | **SDD** | Detallar la arquitectura, el diseno, las APIs, el modelo de datos y la estrategia de testing |

> **Nota:** No siempre se necesitan los tres. Para un cambio tecnico puntual que no tiene requisitos de producto nuevos, un RFC puede ser suficiente. Para features completas que involucran decisiones de arquitectura, lo ideal es seguir el flujo completo.

---

## Como usarlo

### Comandos disponibles

| Comando | Descripcion |
|---------|-------------|
| `/prd [descripcion]` | Inicia el flujo para crear un PRD |
| `/rfc [descripcion]` | Inicia el flujo para crear un RFC |
| `/sdd [descripcion]` | Inicia el flujo para crear un SDD |

El agente va a hacerte preguntas de a 1-2 por turno para recopilar la informacion necesaria. Cuando tenga suficiente contexto, genera el documento completo en markdown y lo guarda en `docs/output/`.

### Nomenclatura de archivos generados

```
TIPO-nombre-feature-YYYY-MM-DD.md
```

Ejemplos:
- `PRD-turnos-medicos-2026-03-28.md`
- `RFC-migracion-auth-2026-03-30.md`
- `SDD-notificaciones-2026-03-28.md`

---

## Ejemplo practico: Sistema de Turnos Medicos

### Paso 1 — Crear el PRD

```
/prd Sistema de turnos medicos online para una clinica
```

El agente te va a preguntar cosas como:
- Quienes son los usuarios? (pacientes, medicos, recepcionistas?)
- Que problemas tienen hoy? (turnos por telefono, esperas largas?)
- Que funcionalidades son imprescindibles vs nice-to-have?
- Hay restricciones de tiempo o presupuesto?

**Resultado:** `docs/output/PRD-turnos-medicos-2026-03-31.md` con requisitos, user stories, KPIs y timeline.

---

### Paso 2 — Crear el RFC

```
/rfc Migrar la gestion de turnos de un sistema legacy a una API REST con notificaciones en tiempo real
```

El agente te va a preguntar cosas como:
- Cual es el sistema actual y que stack usa?
- Que alternativas tecnicas consideraste? (REST vs GraphQL, polling vs WebSockets?)
- Hay breaking changes o migracion de datos?
- Como seria el rollback?

**Resultado:** `docs/output/RFC-migracion-turnos-2026-03-31.md` con la propuesta tecnica, alternativas evaluadas y plan de implementacion.

---

### Paso 3 — Crear el SDD

```
/sdd Diseno del sistema de turnos medicos con API REST, notificaciones y panel de administracion
```

El agente te va a preguntar cosas como:
- Que stack vas a usar? (framework, base de datos, infraestructura)
- Que entidades de dominio identificas? (Turno, Medico, Paciente, Especialidad?)
- Que flujos son los mas criticos?
- Que nivel de cobertura de tests esperas?

**Resultado:** `docs/output/SDD-turnos-medicos-2026-03-31.md` con arquitectura, modelo de dominio, APIs, modelo de datos y estrategia de testing.

---

## Tips

- **Se especifico en la descripcion inicial.** Cuanto mas contexto des en el comando, menos preguntas va a necesitar el agente.
- **No te saltees preguntas.** El agente pregunta para evitar ambiguedades, no por burocracia.
- **Podes iterar.** Si despues de generar un documento queres cambiar algo, decile que lo modifique.
- **No siempre necesitas los 3 documentos.** Adapta el flujo al tamano y complejidad de lo que estes construyendo.
