---
name: setup-leadmatch
description: >
  Configurar el entorno del alumno para el curso LeadMatch. Usar cuando el alumno dice
  "setup-leadmatch", "configurar LeadMatch", "setup inicial", "empezar el curso", "preparar mi entorno",
  o cuando es la primera vez que usa el plugin.
---

# Setup LeadMatch — Onboarding del Alumno

Ejecutar el modulo de setup del curso "Construye desde 0 tu Negocio Digital".

---

## PASO 0 — OBLIGATORIO: Verificar que el MCP esta conectado

Antes de hacer CUALQUIER cosa, verificar que el servidor MCP `leadmatch-course` esta disponible comprobando que la herramienta `empezar-modulo` existe en las herramientas cargadas.

Si `empezar-modulo` NO esta disponible, detener el setup completamente y decir al alumno:

> "Para continuar necesitas tener el conector **leadmatch-course** activo en esta sesion. Ve a **Conectores** en el panel lateral de Cowork, busca **leadmatch-course** y actívalo. Cuando este listo, vuelve a escribir **setup-leadmatch**."

No continuar ni un paso mas sin este conector activo. No improvisar alternativas.

---

## Paso 1: Cuentas necesarias

Preguntar al alumno, una a una, si ya tiene cuenta en cada plataforma. Para las que no tenga, darle el link y esperar a que confirme que la ha creado antes de pasar a la siguiente. No avanzar al siguiente paso hasta tener todas confirmadas.

Las plataformas son:

1. **Gmail** — necesaria para Google Drive y otras integraciones
   - Link: https://accounts.google.com/signup

2. **Notion** — donde se guardan todos los documentos del curso
   - Link: https://www.notion.so/signup

3. **Canva** — para crear las piezas visuales del negocio
   - Link: https://www.canva.com/signup

4. **Systeme.io** — plataforma de ventas y automatizacion del negocio
   - Link afiliado: https://systeme.io/es?sa=sa026826405007614a639b86359cfcb12d31dae20d

5. **Siteground** — hosting web del negocio
   - Link afiliado: https://www.siteground.com/index.htm?afcode=77aff42ee9d1a63e15c2a7f866c25f0e

6. **Vimeo** — para alojar videos del negocio
   - Link: https://vimeo.com/join

---

## Paso 2: Conectores MCP

Guiar al alumno para que configure los conectores uno a uno en Cowork. Para cada uno, dar las instrucciones y esperar confirmacion antes de pasar al siguiente.

1. **Notion**
   > "Ve a **Conectores** en el panel lateral de Cowork → busca **Notion** → conecta con tu cuenta. Confirma cuando este activo."

2. **Google Drive**
   > "En **Conectores**, busca **Google Drive** → conecta con tu cuenta Gmail. Confirma cuando este activo."

3. **Canva**
   > "En **Conectores**, busca **Canva** → conecta con tu cuenta. Confirma cuando este activo."

No continuar al Paso 3 hasta que los tres conectores esten confirmados.

---

## Paso 3: Verificar acceso al curso

Pedir al alumno su codigo de modulo de Setup y su email. Llamar a `empezar-modulo` del servidor MCP leadmatch-course para verificar:
- Codigo valido
- Email con acceso activo en Systeme.io

Si la verificacion falla, mostrar el error y no continuar.

---

## Paso 4: Leer el inventario del Setup desde Notion

Una vez verificado el acceso, leer la pagina del inventario del Setup en Notion con notion-fetch. Esa pagina contiene la presentacion completa del curso. Transmitirla al alumno tal como esta.

---

## Paso 5: Crear la carpeta del alumno en Notion

**OBLIGATORIO**: Crear en el Notion del alumno una pagina llamada exactamente **"Negocio desde 0 con Lead Match"**.

- Crearla como pagina raiz en el workspace privado del alumno, al mismo nivel que el resto de sus paginas principales. No aninarla dentro de ninguna otra pagina.
- Buscar primero el nombre EXACTO. Si existe con ese nombre exacto, no duplicarla.
- Si existe una pagina con nombre parecido pero diferente (ej: "Negocio desde 0 con Lead Match - old", "Negocio desde 0 con LeadMatch", etc.), ignorarla y crear igualmente la pagina con el nombre exacto correcto. No asumir que una pagina de nombre similar es la carpeta del curso.

Usar el MCP de Notion para crearla. Si falla, informar al alumno y pedirle que la cree manualmente — no continuar sin confirmar que existe.

---

## Paso 6: Confirmar al alumno

Confirmar que el setup esta completo:
- Cuentas creadas y verificadas
- Conectores MCP activos (Notion, Google Drive, Canva)
- Acceso al curso verificado
- Carpeta "Negocio desde 0 con Lead Match" creada en su Notion
- Proximo paso: cuando este listo, decir "ejecutar modulo 1"

---

## Reglas

- Toda la comunicacion en castellano. Sin faltas de ortografia.
- Sin MCP leadmatch-course activo, no avanzar. Nunca. Ni un paso.
- Ir paso a paso y esperar confirmacion del alumno en cada uno. No saltarse fases.
- No improvisar la explicacion del curso: leerla del inventario de Notion y transmitirla.
- No dar el setup por completado si la carpeta de Notion no existe confirmada.
