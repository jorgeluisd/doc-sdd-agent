# Doc Agent 📄

Agente de documentación técnica para Claude Code. Genera documentos PRD, SDD y RFC
de alta calidad a través de un flujo conversacional guiado.

## Requisitos

- [Claude Code](https://claude.ai/code) instalado
- Cuenta Claude Pro o acceso a la API de Anthropic

## Instalación de Claude Code

```bash
# Mac
brew install claude-code

# O con el instalador nativo
curl -fsSL https://claude.ai/install.sh | sh
```

## Uso

```bash
# Clonar el repo
git clone <url-del-repo>
cd doc-agent

# Iniciar Claude Code
claude
```

Una vez dentro de la sesión interactiva de Claude Code, usá los comandos:

```
/prd sistema de turnos médicos
/sdd módulo de notificaciones push
/rfc migración de REST a GraphQL
```

O simplemente describí lo que necesitás en lenguaje natural:

```
Necesito crear el PRD para el módulo de pagos de nuestra app
```

## Estructura del proyecto

```
doc-agent/
├── CLAUDE.md                    ← Contexto e instrucciones del agente
├── .claude/
│   ├── settings.json            ← Configuración de permisos
│   └── commands/
│       ├── prd.md               ← /prd
│       ├── sdd.md               ← /sdd
│       └── rfc.md               ← /rfc
├── docs/
│   ├── templates/               ← Templates base de cada documento
│   │   ├── PRD-template.md
│   │   ├── SDD-template.md
│   │   └── RFC-template.md
│   └── output/                  ← Documentos generados (git-ignored por defecto)
└── README.md
```

## Personalización

### Ajustar el stack de tu proyecto
Editá `CLAUDE.md` y agregá el stack tecnológico específico de tu proyecto:

```markdown
## Stack del proyecto
- Backend: Node.js + Express + TypeScript
- Base de datos: PostgreSQL + Prisma
- Frontend: React + Next.js
- Infraestructura: AWS + Docker
- Arquitectura: Onion Architecture
```

### Versionar los documentos generados
Por defecto, `docs/output/` está en `.gitignore`. Si querés versionar los docs:

```bash
# Eliminar la línea del .gitignore
sed -i '' '/docs\/output/d' .gitignore
git add docs/output/
git commit -m "docs: agregar outputs versionados"
```

### Agregar comandos personalizados
Creá nuevos archivos en `.claude/commands/`:

```bash
echo "Revisá este código y generá documentación técnica para: \$ARGUMENTS" \
  > .claude/commands/doc-code.md
```

Usalo con: `/doc-code src/services/PaymentService.ts`

## Tips

- Cuanto más contexto inicial le des al agente, más específico será el resultado
- Podés pasarle contexto de PRDs existentes para crear un SDD relacionado
- Si el agente hace una pregunta que ya respondiste, recordáselo
- Usá `/rfc` para proponer cambios técnicos antes de implementarlos — el agente
  te ayuda a pensar las alternativas y el impacto

## Contribuir

Los templates y comandos son markdown puro — fáciles de mejorar y adaptar.
Pull requests bienvenidos.
