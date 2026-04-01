Vamos a crear un PRD (Product Requirements Document).

Contexto inicial del usuario: $ARGUMENTS

Seguí este flujo estrictamente:

1. Si $ARGUMENTS está vacío, pedile que describa el proyecto o feature en lenguaje libre, sin estructura.
2. Leé el contexto y hacé preguntas específicas de a 1-2 por turno para entender:
   - Problema concreto que resuelve (no la solución, el problema)
   - Usuarios objetivo y su contexto de uso
   - Funcionalidades principales (scope) y qué queda fuera (non-goals)
   - Restricciones conocidas: tiempo, presupuesto, tecnología, equipo
   - Métricas de éxito medibles (KPIs)
   - Riesgos y dependencias
3. Si el usuario propone algo ambiguo, preguntá antes de asumir.
4. Si ves inconsistencias, scope demasiado amplio, o una mejor forma de encararlo,
   debatilo con argumentos concretos. No cedas sin argumentar.
5. Cuando tengas suficiente información, avisá que vas a generar el documento.
6. Usá docs/templates/PRD-template.md como base.
7. Guardá el resultado en docs/output/PRD-[nombre-feature]-[fecha].md
8. Al finalizar, mostrá el path del archivo generado.
