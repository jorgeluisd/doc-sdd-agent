# SDD: [Nombre del Sistema/Feature]

**Versión:** 1.0  
**Autor:**  
**Fecha:**  
**PRD relacionado:**  
**Estado:** Draft | En revisión | Aprobado

---

## 1. Contexto Técnico

### Sistema actual (si aplica)
Descripción del estado actual, deuda técnica relevante, limitaciones conocidas.

### Restricciones técnicas
- Stack obligatorio:
- Restricciones de infraestructura:
- SLAs requeridos:

---

## 2. Arquitectura General

**Estilo arquitectónico:** Onion / Clean / Hexagonal / Microservicios / otro

### Diagrama de alto nivel

```
┌─────────────────────────────────────┐
│           Presentation Layer         │
│  (Controllers / API / UI)           │
├─────────────────────────────────────┤
│           Application Layer          │
│  (Use Cases / Application Services) │
├─────────────────────────────────────┤
│             Domain Layer             │
│  (Entities / Aggregates / Services) │
├─────────────────────────────────────┤
│         Infrastructure Layer         │
│  (Repos / DB / External APIs)       │
└─────────────────────────────────────┘
```

### Principios aplicados
- [ ] Single Responsibility
- [ ] Open/Closed
- [ ] Dependency Inversion
- [ ] Separación de concerns
- [ ] DDD (si aplica)

---

## 3. Módulos y Componentes

### Módulo: [Nombre]
- **Responsabilidad:**
- **Interfaces expuestas:**
- **Dependencias:**
- **Capa:** Presentation / Application / Domain / Infrastructure

### Módulo: [Nombre]
- **Responsabilidad:**
- **Interfaces expuestas:**
- **Dependencias:**
- **Capa:**

---

## 4. Modelo de Dominio

### Entidades principales
| Entidad | Descripción | Agregado raíz |
|---------|-------------|---------------|
| | | Sí / No |

### Value Objects
| Value Object | Descripción |
|-------------|-------------|
| | |

### Diagrama de clases / ER
```
[Entidad A] ──── [Entidad B]
      │
      └──── [Value Object]
```

---

## 5. Flujos Principales

### Flujo: [Nombre del caso de uso]

```
Actor → Controller → UseCase → DomainService → Repository → DB
                         ↓
                    Domain Event
                         ↓
                    EventHandler
```

**Pasos:**
1.
2.
3.

**Errores posibles:**
- `ErrorA`: cuando ocurre X
- `ErrorB`: cuando ocurre Y

---

## 6. Decisiones de Diseño (ADR)

| ID | Decisión | Alternativas consideradas | Razón de la elección |
|----|----------|--------------------------|----------------------|
| ADR-01 | | | |
| ADR-02 | | | |

---

## 7. APIs e Interfaces

### `POST /recurso`
**Descripción:**

**Request:**
```json
{
  "campo": "tipo"
}
```

**Response 200:**
```json
{
  "campo": "tipo"
}
```

**Errores:**
| Código | Descripción |
|--------|-------------|
| 400 | |
| 401 | |
| 404 | |
| 500 | |

---

## 8. Modelo de Datos

```sql
-- Tabla principal
CREATE TABLE nombre (
  id          UUID PRIMARY KEY DEFAULT gen_random_uuid(),
  campo       VARCHAR(255) NOT NULL,
  created_at  TIMESTAMP NOT NULL DEFAULT NOW(),
  updated_at  TIMESTAMP NOT NULL DEFAULT NOW()
);

-- Índices
CREATE INDEX idx_nombre_campo ON nombre(campo);
```

### Consideraciones
- Estrategia de migraciones:
- Soft delete:
- Auditoría:

---

## 9. Estrategia de Testing

| Tipo | Qué cubre | Herramienta | Cobertura mínima |
|------|-----------|-------------|-----------------|
| Unit | Domain layer, Use cases | | 80% |
| Integration | Repositories, APIs | | |
| E2E | Flujos críticos | | |
| Contract | APIs externas | | |

### Casos de prueba críticos
- [ ]
- [ ]

---

## 10. Seguridad

| Aspecto | Implementación |
|---------|----------------|
| Autenticación | |
| Autorización | |
| Validación de inputs | |
| Datos sensibles | |
| Rate limiting | |

---

## 11. Observabilidad

| Aspecto | Detalle |
|---------|---------|
| Logs | Nivel, formato, datos a loguear |
| Métricas | Qué medir, herramienta |
| Trazabilidad | Correlation IDs, distributed tracing |
| Alertas | Umbrales, canales |

---

## 12. Deploy y Operaciones

| Aspecto | Detalle |
|---------|---------|
| Infraestructura | |
| Variables de entorno | |
| Feature flags | |
| Estrategia de rollout | |
| Rollback plan | |

---

## 13. Historial de cambios

| Versión | Fecha | Autor | Cambios |
|---------|-------|-------|---------|
| 1.0 | | | Versión inicial |
