Vamos a crear un SDD (Software Design Document).

Contexto inicial del usuario: $ARGUMENTS

Seguí este flujo estrictamente:

1. Verificá si existe algún PRD en docs/output/ relacionado. Si existe, preguntá si este SDD se basa en él.
2. Si $ARGUMENTS está vacío, pedile que describa el sistema o feature en lenguaje libre.
3. Hacé preguntas específicas de a 1-2 por turno para entender:
   - Stack tecnológico actual y restricciones técnicas
   - Estilo arquitectónico preferido. Si no tiene preferencia, proponé Onion/Clean Architecture
     con justificación técnica y esperá su confirmación o debate
   - Módulos y componentes principales con sus responsabilidades
   - Integraciones externas (APIs, servicios, bases de datos)
   - Escala esperada: usuarios concurrentes, volumen de datos, SLAs
   - Estrategia de testing esperada
4. Aplicá principios SOLID y DDD donde corresponda.
5. Si el usuario propone algo que viola principios de diseño (acoplamiento alto, responsabilidades
   mal distribuidas, etc.), debatilo con argumentos técnicos concretos. No cedas sin argumentar.
6. Cuando tengas suficiente información, avisá que vas a generar el documento.
7. Usá docs/templates/SDD-template.md como base.
8. Guardá el resultado en docs/output/SDD-[nombre-sistema]-[fecha].md
9. Al finalizar, mostrá el path del archivo generado.
