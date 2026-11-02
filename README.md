# TutorIA

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23066871.svg)](https://doi.org/10.5281/zenodo.23066871)

**Aplicación:** https://fborrasumh.github.io/tutoria/

Un tutor de IA que **hace pensar**, construido con el material del profesor. El profesor prepara una lección a partir de su tema y valida las soluciones; el estudiante la recorre paso a paso: el tutor no le da las respuestas, le hace razonar, le da pistas graduadas y confirma cuándo acierta. Diagnóstico al principio, comprobación al final y repaso espaciado. Aplicación de un solo fichero (`index.html`), sin servidor ni cuenta, con el diseño de la familia Forja.

**Idiomas:** español (por defecto), inglés y portugués, con selector en la barra superior (o `?lang=en` / `?lang=pt` en la URL). La lección se escribe en el idioma que elige el profesor y el tutor conversa en ese idioma.

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

1. **Material**: el tema en PDF, Word, PowerPoint, cuaderno Jupyter, Markdown o texto.
2. **Revisar**: la IA propone objetivos (comprender, aplicar, analizar) y una actividad por objetivo dividida en partes. Cada parte lleva solución paso a paso, respuesta final, cita literal del material, errores frecuentes y tres pistas graduadas. Un segundo agente resuelve cada parte sin ver la solución y otro compara las dos resoluciones; **el código comprueba que la cita existe en el material**. Lo no verificado se marca en rojo con el motivo. Todo es editable, incluidas las preguntas de diagnóstico y comprobación; el código descarta las preguntas mal formadas (sin cuatro opciones distintas o con «todas/ninguna de las anteriores»).
3. **Compartir**: la lección, marcada como validada, se comparte con un **enlace que la contiene comprimida** (sin servidor) o como fichero `.json`. Ni el enlace ni el fichero llevan el material.

## Modo estudiante

- Abre la lección del profesor por enlace o fichero. Si no tiene ninguna, puede preparar una a partir del material: solo se conservan las partes verificadas y se avisa de que no está validada por el profesor.
- Recorrido: objetivos → diagnóstico sin nota → actividades → comprobación → resultado por objetivo, con qué repasar.
- **Con clave de IA**: tutor conversacional que compara con la solución validada y lee fotos del trabajo hecho a mano (si el modelo admite imágenes). Si un mensaje del tutor fuera a revelar la respuesta final sin que el estudiante la haya dado, **el código lo retiene**.
- **Sin clave**: modo práctica con autocorrección frente a la respuesta de referencia. Las pistas y las soluciones son las de la lección.
- Repaso espaciado con archivo `.ics` e informe en Word, generado en el navegador sin conexión.

## Cómo se usa la IA

Con la clave de cada persona de **OpenAI, Google Gemini o Anthropic Claude**, con desplegable de los modelos disponibles en esa clave. La clave se guarda solo en el navegador (la de OpenAI, `ia_openai_key`, es compartida con el resto del catálogo). Sin servidor.

## Privacidad

Lecciones, material y progreso se guardan en el navegador (IndexedDB). Con clave, sale hacia el proveedor elegido: al preparar una lección, el material; con el tutor, la parte de la lección en curso y los mensajes del estudiante. En ambos casos se enmascaran antes correos, DNI/NIE y teléfonos. Las fotos se envían tal cual: no se pueden enmascarar. Antes del primer envío de cada sesión se muestra una muestra de lo que sale y se pide confirmación.

## Límites

El estudio original usó soluciones y prompts escritos por profesores expertos. La eficacia de lecciones generadas automáticamente no está demostrada: por eso la validación del profesor es el centro de TutorIA. La verificación automática (segundo agente + cita comprobada) reduce errores, pero no los elimina; una parte «verificada» puede seguir siendo incorrecta. El enmascarado no detecta nombres propios. Los PDF escaneados sin texto no se admiten. El tutor está pensado para aprender un tema, idealmente antes de clase, no para realizar tareas evaluables. Los resultados del diagnóstico y la comprobación son orientativos, no una nota.

## Novedades de la versión 2.0.0

Interfaz en español, inglés y portugués; OpenAI, Gemini o Claude con selector de modelos; aviso previo al envío y enmascarado de datos personales; almacenamiento en IndexedDB con migración automática de las lecciones de la versión 1; reverificación con el material guardado; lectura de PowerPoint; informe en Word sin red; diseño Forja actualizado.

## Autoría

Fernando Borrás Rocher (Universidad Miguel Hernández de Elche) · ORCID [0000-0002-5519-4573](https://orcid.org/0000-0002-5519-4573)

## Cómo citar

Borrás Rocher, F. (2026). *TutorIA* (versión 2.0.0) [Software]. Universidad Miguel Hernández de Elche. https://doi.org/10.5281/zenodo.23066871

El DOI es el de concepto: apunta siempre a la última versión. GitHub ofrece la cita en APA y BibTeX con el botón *Cite this repository*, a partir de `CITATION.cff`.

Forma parte del catálogo [Herramientas IA para la academia](https://fborrasumh.github.io/ia/).

## Licencia

MIT © 2026 Fernando Borrás Rocher · Universidad Miguel Hernández de Elche.
