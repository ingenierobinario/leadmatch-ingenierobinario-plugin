---
name: ejecutar-modulo
description: >
  Ejecutar un modulo del curso LeadMatch. Usar cuando el alumno dice "ejecutar modulo 1",
  "quiero trabajar en el modulo 2", "empezar modulo 3", "siguiente modulo", "generar el
  manual estrategico", "generar el brand book", "generar documento de estrategia",
  "prompt A del modulo 2", o cualquier referencia a trabajar en un modulo especifico del curso.
---

# Ejecutar Modulo — Flujo Principal del Curso LeadMatch

Este es el skill principal del plugin. Gestiona la ejecucion completa de cualquier modulo del curso "Construye desde 0 tu Negocio Digital".

## Requisitos de acceso

Antes de ejecutar cualquier modulo, el alumno debe proporcionar:

1. **Codigo del modulo**: un codigo alfanumerico que el profesor da en clase (ej: LM1-R22NZI)
2. **Email**: el mismo con el que se registro en Systeme.io

El servidor MCP realiza doble verificacion automatica: codigo valido + email suscrito con tag activo en Systeme.io. Si cualquiera falla, el alumno recibe un mensaje de error claro.

Usar la herramienta `empezar-modulo` del servidor MCP con el codigo y email del alumno.

## Modulos disponibles

| Modulo | Nombre | Outputs |
|--------|--------|---------|
| M0 | Setup Inicial | Set-up completo: Notion conectado, carpeta creada |
| M1 | Estrategia de Negocio | Manual Estrategico Producto + Informe Diagnostico |
| M2 | Estrategia de Marca | Doc Estrategia Marca + Informe Diagnostico |
| M3 | Identidad de Marca | Brand Book + Informe Diagnostico |
| M4 | Captacion y Ventas | Estrategia Ventas + Estructura Web (Copies) |
| M5 | Automatizacion | Estrategia Activacion + Analisis Web |
| M6 | Escalado | Informe Diagnostico y Optimizacion |

## Flujo de ejecucion

### Paso 1: Verificar acceso

Pedir al alumno su codigo de modulo y email. Llamar a la herramienta `empezar-modulo` del servidor MCP leadmatch-course. El servidor:
- Valida el codigo del modulo
- Verifica el email en Systeme.io
- Lee las instrucciones del modulo desde Notion
- Devuelve los datos del modulo con todas sus fases

Si la verificacion falla, mostrar el mensaje de error al alumno y no continuar.

### Paso 2: Leer el inventario del modulo

El servidor MCP devuelve los datos del modulo directamente desde Notion. El inventario contiene:
- **INPUT**: guias de instrucciones, fichas rellenables y checkpoints
- **PROMPTS**: los prompts exactos a ejecutar (A, B, y a veces C)
- **OUTPUT**: los documentos que deben generarse

Si el servidor no devuelve datos suficientes, consultar `references/modulos-urls.md` para obtener el ID de Notion y leerlo con notion-fetch.

### Paso 3: Leer las guias de instrucciones

Leer cada guia usando notion-fetch con la URL o ID que aparece en el inventario.

Las guias son el conocimiento experto. Contienen:
- Que hacer en cada bloque
- Como abordarlo
- Criterios de validacion
- Errores a evitar

**CRITICO**: Seguir las guias al pie de la letra. No improvisar ni añadir secciones que la guia no contempla.

### Paso 4: Recoger la informacion del alumno

**OBLIGATORIO**: Nunca preguntes al alumno directamente en el chat. Siempre usa las herramientas del MCP para el cuestionario.

Llamar INMEDIATAMENTE a `start-phase-questionnaire` del servidor MCP leadmatch-course con:
- `email`: el email verificado del alumno
- `moduleNumber`: el numero del modulo
- `phaseNumber`: 1 (primera fase)

Esta herramienta lanza la interfaz interactiva de preguntas. No hagas las preguntas tu mismo en texto. No improvises preguntas. No pidas informacion al alumno antes de llamar a `start-phase-questionnaire`.

Cuando el alumno responda cada pregunta, llamar a `answer-question` con la respuesta. Repetir hasta que el cuestionario este completo (`isComplete: true`).

Para M4 en adelante, tambien recuperar los outputs de modulos anteriores desde la carpeta "Negocio desde 0 con Lead Match" del Notion del alumno.

**Nota sobre acumulacion**: A partir del M3, el Brand Book integra M1 + M2 y se convierte en el unico input necesario para modulos posteriores.

### Paso 5: Ejecutar los prompts

Ejecutar los prompts del modulo en orden (A, luego B, luego C si existe):

**Prompt A** — Generacion del documento principal. Aplicar:
- Las instrucciones de la guia, bloque a bloque, en orden exacto
- La informacion de la ficha/cuestionario del alumno
- Los outputs de modulos anteriores como contexto

**Prompt B** — Generalmente es el diagnostico. Aplicar:
- El checkpoint como referencia de evaluacion
- Analisis objetivo, sin juzgar la idea del alumno
- Conclusion con veredicto: VALIDADO / AJUSTAR / REPLANTEAR

**Prompt C** (si existe) — Seguir las instrucciones del inventario.

### Paso 6: Guardar en Notion del alumno

Cada documento generado debe guardarse como pagina nueva en Notion del alumno, dentro de "Negocio desde 0 con Lead Match". Usar herramientas de Notion para crear paginas con nombre claro.

Tambien usar `save-results` del servidor MCP para persistir las respuestas del cuestionario.

### Paso 7: Confirmar y orientar

Tras completar el modulo:
1. Confirmar que todos los documentos se han guardado correctamente
2. Mostrar el veredicto del diagnostico (si aplica)
3. Indicar siguiente paso segun el veredicto:
   - VALIDADO: puede avanzar al siguiente modulo
   - AJUSTAR: señalar que puntos revisar antes de continuar
   - REPLANTEAR: recomendar sesion de consultoria con el equipo

## Reglas fundamentales

- **No inventar informacion** que el alumno no haya proporcionado. Si falta algo, preguntar.
- **No ser generico.** Todo debe estar aplicado al caso concreto del alumno.
- **Seguir las guias al pie de la letra.** Son los criterios profesionales del curso.
- **No juzgar la idea del alumno** en los diagnosticos. Solo analizar solidez y coherencia.
- **Toda la comunicacion en castellano.** Sin faltas de ortografia.
- **Ser responsable con el consumo de tokens.** No repetir informacion innecesariamente.
- **Doble verificacion**: antes de dar por terminado, revisar que se hayan generado y guardado todos los documentos indicados en el OUTPUT del inventario.
