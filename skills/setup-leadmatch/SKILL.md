---
name: setup-leadmatch
description: >
  Configurar el entorno del alumno para el curso LeadMatch. Usar cuando el alumno dice
  "configurar LeadMatch", "setup inicial", "empezar el curso", "preparar mi entorno",
  "conectar mis herramientas" o cuando es la primera vez que usa el plugin.
---

# Setup LeadMatch — Onboarding del Alumno

Guiar al alumno en la configuracion inicial de su entorno de trabajo para el curso "Construye desde 0 tu Negocio Digital".

## Contexto del curso

Este es un curso de 6 modulos donde el alumno construye su negocio digital desde cero. El flujo de cada modulo es:
1. El alumno proporciona su codigo de modulo y email
2. El servidor verifica el acceso (codigo valido + email en Systeme.io)
3. Se leen las instrucciones del modulo desde Notion
4. Se ejecutan cuestionarios adaptativos para recoger informacion del alumno
5. Se generan documentos estrategicos aplicados a su caso
6. Se guarda todo en Notion del alumno

Los outputs de cada modulo son los inputs del siguiente. Todo es acumulativo.

## Pasos del setup

### 1. Verificar acceso al curso

Pedir al alumno su email y el codigo del modulo de Setup. Usar la herramienta `empezar-modulo` del servidor MCP leadmatch-course para verificar:
- Que el codigo es valido
- Que el email tiene acceso activo en Systeme.io

### 2. Verificar herramientas conectadas

Comprobar que el alumno tiene Notion conectado. Intentar buscar o crear la carpeta "Negocio desde 0 con Lead Match" en su Notion. Esta carpeta sera el repositorio central de todos los documentos del curso.

### 3. Explicar el flujo de trabajo

Explicar al alumno como va a funcionar el sistema:
- Cada modulo tiene un inventario con todo lo necesario (guias, fichas, prompts)
- El plugin lee las guias automaticamente desde el inventario del curso
- El alumno responde cuestionarios adaptativos con interfaz interactiva
- El plugin ejecuta los prompts y genera los documentos
- Todo se guarda en su Notion

### 4. Confirmar que todo esta listo

Hacer un resumen de:
- Acceso verificado
- Herramientas verificadas
- Carpeta de Notion creada
- Proximo paso: empezar con el Modulo 1

## Reglas

- Toda la comunicacion debe ser en castellano.
- No cometer faltas de ortografia.
- Ser conciso y claro, sin rodeos.
- Si algo falla en la configuracion, explicar como resolverlo sin tecnicismos innecesarios.
