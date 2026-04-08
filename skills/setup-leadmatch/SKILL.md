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

> "Para continuar necesitas activar el conector del curso. Es un solo clic que solo tienes que hacer una vez:
>
> 1. Ve a **Personalizar** (icono de persona en el panel lateral)
> 2. Dentro del plugin **Leadmatch ingenierobinario**, haz clic en **Conectores**
> 3. Veras **leadmatch-course** con un boton **Instalar** — haz clic
> 4. Cuando este instalado, vuelve aqui y escribe **setup-leadmatch**"

No continuar ni un paso mas sin este conector activo. No improvisar alternativas.

---

## Paso 1: Verificar acceso al curso

Este es SIEMPRE el primer paso. Pedir al alumno su codigo de modulo de Setup y su email. Llamar a `empezar-modulo` del servidor MCP leadmatch-course para verificar:
- Codigo valido
- Email con acceso activo en Systeme.io

Si la verificacion falla, mostrar el error y no continuar.

---

## Paso 2: Cuentas necesarias

Mostrar al alumno la lista completa de plataformas que va a necesitar durante el curso, con los links de registro. Preguntarle de una sola vez cuales le faltan por crear. No preguntar una a una.

Las plataformas son:

1. **Gmail** — necesaria para Google Drive y otras integraciones → https://accounts.google.com/signup
2. **Notion** — donde se guardan todos los documentos del curso → https://www.notion.so/signup
3. **Canva** — para crear las piezas visuales del negocio → https://www.canva.com/signup
4. **Systeme.io** — plataforma de ventas y automatizacion → https://systeme.io/es?sa=sa026826405007614a639b86359cfcb12d31dae20d
5. **Siteground** — hosting web del negocio → https://www.siteground.com/index.htm?afcode=77aff42ee9d1a63e15c2a7f866c25f0e
6. **Vimeo** — para alojar videos del negocio → https://vimeo.com/join

Preguntar: "¿Tienes cuenta en todas? Dime cuales te faltan y las creas ahora."
Esperar confirmacion de que tiene todas antes de continuar.

---

## Paso 3: Conectores MCP

Explicar al alumno que necesita activar 3 conectores en Cowork. Dar las instrucciones de todos juntos:

> "Ve a **Conectores** en el panel lateral de Cowork y conecta estos tres:
> 1. **Notion** — conecta con tu cuenta
> 2. **Google Drive** — conecta con tu cuenta Gmail
> 3. **Canva** — conecta con tu cuenta
>
> Confirma cuando los tres esten activos."

No continuar al Paso 4 hasta que confirme que los tres estan activos.

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
- Acceso al curso verificado
- Cuentas creadas y verificadas
- Conectores MCP activos (Notion, Google Drive, Canva)
- Carpeta "Negocio desde 0 con Lead Match" creada en su Notion
- Proximo paso: cuando este listo, decir "ejecutar modulo 1"

---

## Reglas

- Toda la comunicacion en castellano. Sin faltas de ortografia.
- Sin MCP leadmatch-course activo, no avanzar. Nunca. Ni un paso.
- No improvisar la explicacion del curso: leerla del inventario de Notion y transmitirla.
- No dar el setup por completado si la carpeta de Notion no existe confirmada.
