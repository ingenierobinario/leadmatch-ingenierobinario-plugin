---
name: setup-leadmatch
description: >
  Configurar el entorno del alumno para el curso LeadMatch. Usar cuando el alumno dice
  "setup-leadmatch", "configurar LeadMatch", "setup inicial", "empezar el curso", "preparar mi entorno",
  o cuando es la primera vez que usa el plugin.
---

# Setup LeadMatch — Onboarding del Alumno

Ejecutar el modulo de setup del curso "Construye desde 0 tu Negocio Digital".

## PASO 0 — OBLIGATORIO: Verificar que el MCP esta conectado

Antes de hacer CUALQUIER cosa, verificar que el servidor MCP `leadmatch-course` esta disponible comprobando que la herramienta `empezar-modulo` existe en las herramientas cargadas.

Si `empezar-modulo` NO esta disponible, detener el setup completamente y decir al alumno:

> "Para continuar necesitas tener el conector **leadmatch-course** activo en esta sesion. Ve a **Conectores** en el panel lateral de Cowork, busca **leadmatch-course** y actívalo. Cuando este listo, vuelve a escribir **setup-leadmatch**."

No continuar ni un paso mas sin este conector activo. No improvisar alternativas.

---

## Paso 1: Verificar acceso al curso

Pedir al alumno su codigo de modulo de Setup y su email. Llamar a `empezar-modulo` del servidor MCP leadmatch-course para verificar:
- Codigo valido
- Email con acceso activo en Systeme.io

Si la verificacion falla, mostrar el error y no continuar.

## Paso 2: Leer el inventario del Setup desde Notion

Una vez verificado el acceso, leer la pagina del inventario del Setup en Notion con notion-fetch. Esa pagina contiene la presentacion completa del curso. Transmitirla al alumno tal como esta.

## Paso 3: Crear la carpeta del alumno en Notion

**OBLIGATORIO**: Crear en el Notion del alumno una pagina llamada exactamente **"Negocio desde 0 con Lead Match"**.

Buscar primero el nombre EXACTO. Si existe con ese nombre exacto, no duplicarla. Si existe una pagina con nombre parecido pero diferente (ej: "Negocio desde 0 con Lead Match - old", "Negocio desde 0 con LeadMatch", etc.), ignorarla y crear igualmente la carpeta con el nombre exacto correcto. No asumir que una pagina de nombre similar es la carpeta del curso.

Usar el MCP de Notion para crearla. Si falla, informar al alumno y pedirle que la cree manualmente — no continuar sin confirmar que existe.

## Paso 4: Confirmar al alumno

Confirmar que el setup esta completo:
- Acceso verificado
- Carpeta "Negocio desde 0 con Lead Match" creada en su Notion
- Proximo paso: cuando este listo, decir "ejecutar modulo 1"

## Reglas

- Toda la comunicacion en castellano. Sin faltas de ortografia.
- Sin MCP activo, no avanzar. Nunca. Ni un paso.
- No improvisar la explicacion del curso: leerla del inventario de Notion y transmitirla.
- No dar el setup por completado si la carpeta de Notion no existe confirmada.
