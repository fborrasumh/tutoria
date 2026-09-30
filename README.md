# TutorIA

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23066871.svg)](https://doi.org/10.5281/zenodo.23066871)

**Aplicación:** https://fborrasumh.github.io/tutoria/

Un tutor de IA que **hace pensar**, construido con el material del profesor. El profesor prepara una lección a partir de su tema y valida las soluciones; el estudiante la recorre paso a paso: el tutor no le da las respuestas, le hace razonar, le da pistas graduadas y confirma cuándo acierta. Diagnóstico al principio, comprobación al final y repaso espaciado. Aplicación de un solo fichero (`index.html`), sin servidor ni cuenta, con el diseño de la familia Forja.

## En qué se basa

El diseño sigue el ensayo aleatorizado de Kestin, Miller, Klales, Milbourne y Ponti (2025), *AI tutoring outperforms in-class active learning*, *Scientific Reports* 15, 17458 (https://doi.org/10.1038/s41598-025-97652-6). En ese estudio, un tutor de IA diseñado con buenas prácticas pedagógicas consiguió más aprendizaje, en menos tiempo, que una clase de aprendizaje activo. TutorIA traslada sus claves de diseño:

| Práctica del estudio | Cómo la aplica TutorIA |
|---|---|
| Aprendizaje activo, carga cognitiva, mentalidad de crecimiento | Reglas del tutor: preguntar en lugar de responder, una idea por mensaje, valorar el esfuerzo |
| Andamiaje controlado por la plataforma, no por el prompt | El código lleva la secuencia: una parte de cada actividad cada vez |
| Exactitud mediante soluciones escritas de antemano | Soluciones paso a paso validadas por el profesor (o verificadas automáticamente), con las que el tutor compara siempre |
| Feedback oportuno y ritmo propio | Tutor disponible en cada paso; el estudiante avanza cuando acierta |
| Medir el aprendizaje real | Diagnóstico y comprobación con preguntas distintas sobre los mismos objetivos |
| Espaciado (línea futura del estudio) | Repaso a uno, tres y siete días, con recordatorios en el calendario |

## Modo profesor

1. **Material**: el tema en PDF, Word, cuaderno Jupyter o texto.
2. **Revisar**: la IA propone objetivos (comprender, aplicar, analizar) y una actividad por objetivo dividida en partes. Cada parte lleva solución paso a paso, respuesta final, cita literal del material, errores frecuentes y tres pistas graduadas. Un segundo agente resuelve cada parte sin ver la solución y otro compara las dos resoluciones; el código comprueba que la cita existe en el material. Lo no verificado se marca en rojo. Todo es editable, incluidas las preguntas de diagnóstico y comprobación.
3. **Compartir**: la lección, marcada como validada, se comparte con un **enlace que la contiene comprimida** (sin servidor) o como fichero `.json`.

## Modo estudiante

- Abre la lección del profesor por enlace o fichero. Si no tiene ninguna, puede preparar una a partir del material: solo se conservan las partes verificadas y se avisa de que no está validada por el profesor.
- Recorrido: objetivos → diagnóstico sin nota → actividades → comprobación → resultado por objetivo, con qué repasar.
- **Con clave de OpenAI**: tutor conversacional que compara con la solución validada y lee fotos del trabajo hecho a mano. Si intenta revelar la respuesta final, la app lo retiene.
- **Sin clave**: modo práctica con autocorrección frente a la respuesta de referencia. Las pistas y las soluciones son las de la lección.
- Repaso espaciado con archivo `.ics` e informe descargable.

## Límites

El estudio original usó soluciones y prompts escritos por profesores expertos. La eficacia de lecciones generadas automáticamente no está demostrada: por eso la validación del profesor es el centro de TutorIA. El tutor está pensado para aprender un tema, idealmente antes de clase, no para realizar tareas evaluables.

## Privacidad

Lecciones y progreso se guardan en el navegador (`localStorage`). Con clave (`ia_openai_key`, compartida con el resto del catálogo), se envían a OpenAI la parte de la lección en curso y los mensajes del estudiante. El enlace del profesor no incluye el material completo, solo la lección.

## Cómo citar

Borrás Rocher, F. (2026). *TutorIA* (versión 1.0.0) [Software]. Universidad Miguel Hernández de Elche. https://doi.org/10.5281/zenodo.23066871

El DOI es el de concepto: apunta siempre a la última versión. GitHub ofrece la cita en APA y BibTeX con el botón *Cite this repository*, a partir de `CITATION.cff`.

Forma parte del catálogo [Herramientas IA para la academia](https://fborrasumh.github.io/ia/).

## Licencia

MIT © 2026 Fernando Borrás Rocher · Universidad Miguel Hernández de Elche.
