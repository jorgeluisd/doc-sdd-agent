Vamos a redactar un RFC (Request for Comments).

Cambio propuesto: $ARGUMENTS

Seguí este flujo estrictamente:

1. Si $ARGUMENTS está vacío, preguntá qué cambio técnico se quiere proponer.
2. Preguntá por el problema actual y por qué el enfoque vigente es insuficiente.
   Pedí evidencia concreta (errores, métricas, limitaciones).
3. Identificá el sistema afectado, módulos y stack actual.
4. Explorá con el usuario al menos 2 alternativas antes de definir la propuesta final.
   Para cada alternativa, analizá trade-offs juntos.
5. Si tenés una opinión técnica sobre cuál alternativa es superior, la presentás con
   argumentos sólidos. Pero escuchá el razonamiento del usuario antes de concluir.
6. Evaluá impacto: breaking changes, curva de aprendizaje del equipo, plan de rollback.
7. Listá las preguntas abiertas que el equipo deberá resolver.
8. Cuando tengas suficiente información, avisá que vas a generar el documento.
9. Determiná el número correlativo del RFC revisando docs/output/ (RFC-001, RFC-002, etc.)
10. Usá docs/templates/RFC-template.md como base.
11. Guardá el resultado en docs/output/RFC-[NNN]-[nombre]-[fecha].md
12. Al finalizar, mostrá el path del archivo generado.
