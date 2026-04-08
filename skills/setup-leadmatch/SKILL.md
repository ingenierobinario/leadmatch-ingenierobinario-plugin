---
name: setup-leadmatch
description: >
  Configurar el entorno del alumno para el curso LeadMatch. Usar cuando el alumno dice
  "setup-leadmatch", "configurar LeadMatch", "setup inicial", "empezar el curso", "preparar mi entorno",
  o cuando es la primera vez que usa el plugin.
---

# Setup LeadMatch — Onboarding del Alumno

Ejecutar el modulo de setup del curso "Construye desde 0 tu Negocio Digital". Este modulo no tiene cuestionario: su unico output es presentar el curso al alumno y crear su carpeta en Notion.

## Pasos del setup

### 1. Verificar acceso

Pedir al alumno su codigo de modulo de Setup y su email. Llamar a `empezar-modulo` del servidor MCP leadmatch-course para verificar:
- Codigo valido
- Email con acceso activo en Systeme.io

Si la verificacion falla, mostrar el error y no continuar.

### 2. Leer el inventario del Setup desde Notion

Una vez verificado el acceso, el servidor devuelve el ID de la pagina del inventario del Setup en Notion. Leerla con notion-fetch.

Esa pagina contiene la presentacion completa del curso. Transmitirla al alumno tal como esta: que es el curso, que va a construir en cada modulo y como funciona el flujo.

### 3. Crear la carpeta del alumno en Notion

**OBLIGATORIO**: Crear en el Notion del alumno una pagina llamada exactamente **"Negocio desde 0 con Lead Match"**. Esta carpeta es el repositorio central de todos los documentos del curso.

Usar el MCP de Notion para crearla. Buscar primero el nombre EXACTO "Negocio desde 0 con Lead Match". Si existe con ese nombre exacto, no duplicarla. Si existe una pagina con nombre parecido pero diferente (ej: "Negocio desde 0 con Lead Match - old", "Negocio desde 0 con LeadMatch", etc.), ignorarla y crear igualmente la carpeta con el nombre exacto correcto. No asumir que una pagina de nombre similar es la carpeta del curso.

### 4. Confirmar al alumno

Confirmar que el setup esta completo e indicar el siguiente paso:

- Setup completado
- Carpeta "Negocio desde 0 con Lead Match" creada en su Notion
- Proximo paso: cuando este listo, decir "ejecutar modulo 1"

## Reglas

- Toda la comunicacion en castellano. Sin faltas de ortografia.
- No improvisar la explicacion del curso: leerla del inventario de Notion y transmitirla.
- Si el MCP de Notion falla al crear la carpeta, informar al alumno y pedir que la cree manualmente.
