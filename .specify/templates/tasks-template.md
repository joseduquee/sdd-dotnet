---
description: "Plantilla de tareas trazables para implementar una iniciativa fullstack .NET"
---

# Tareas: [NOMBRE DE LA INICIATIVA]

**Entrada**: `specs/NNN-nombre/spec.md` y `specs/NNN-nombre/plan.md` aprobados.

**Prerrequisitos**: Spec, plan y constitución leídos; iniciativas de menor número completadas.

Si no existe `plan.md`, detenerse:
`Ejecución detenida: antes de ejecutar speckit.tasks debe crear el archivo plan.md mediante speckit.plan.`

Si se intenta implementar sin este documento, detenerse:
`Ejecución detenida: antes de ejecutar speckit.implement debe crear el archivo tasks.md mediante speckit.tasks.`

## Formato y trazabilidad

Usar `- [ ] TNNN [P] [USn] Descripción con rutas concretas y requisito asociado`.

- `TNNN` DEBE ser un identificador único y ordenado por dependencias.
- `[P]` solo indica tareas independientes, sin conflictos de archivos; no autoriza subagentes.
- `[USn]` vincula la tarea con una historia de la spec; las tareas comunes DEBEN citar su requisito.
- Cada tarea DEBE especificar dependencias y una verificación observable, aquí o en una tabla.
- Todos los archivos modificados o creados DEBEN quedar cubiertos por una tarea.
- Solo se DEBE marcar `[X]` después de completar y verificar; los bloqueos quedan pendientes.

La iniciativa DEBE contener exactamente `spec.md`, `plan.md` y `tasks.md`.
La investigación, contratos, modelo de datos y ejecución local se consultan en `plan.md`.
No generar documentos auxiliares para eludir esta estructura.

## Convenciones de rutas

- Backend: `app/backend/src/<ProyectoApi>/`, con slices agrupados por caso de uso.
- Frontend: `app/frontend/src/<ProyectoWeb>/`, con Razor Components y cliente Refit.
- Estilos: `wwwroot/app.css` dentro del proyecto frontend.
- Pruebas aprobadas: `app/backend/tests/` o `app/frontend/tests/`, según el plan.

Sustituir los nombres de ejemplo por rutas reales del plan. No crear proyectos ni
carpetas de pruebas sin alcance aprobado.

<!--
Las tareas siguientes son ejemplos, no una autorización de implementación.
speckit.tasks DEBE sustituirlas por tareas concretas derivadas de spec.md y plan.md,
eliminar las que no apliquen y preservar la organización por historia de usuario.
No agregar autenticación, eventos, migraciones, seeds ni pruebas por defecto.
-->

## Fase 1: Preparación

**Objetivo**: Preparar únicamente la estructura e infraestructura aprobadas.

- [ ] T001 Preparar proyectos .NET 11 en las rutas de `app/backend/` y `app/frontend/` definidas en el plan; [requisito].
- [ ] T002 Configurar dependencias y configuración externa sin secretos en [rutas concretas]; [requisito].

**Control**: [Compilación y configuración verificables; dependencias de cada tarea].

## Fase 2: Fundamentos necesarios

**Objetivo**: Resolver los prerrequisitos que bloqueen las historias aprobadas.

- [ ] T003 Configurar Minimal APIs, OpenAPI y errores ProblemDetails en [rutas concretas del backend]; [requisito].
- [ ] T004 Configurar el cliente tipado Refit y el sistema visual en [rutas concretas del frontend]; [requisito].

Si hay persistencia, agregar tareas específicas para el modelo, configuraciones
`IEntityTypeConfiguration<T>`, compilación, migración coherente y arranque centralizado.
Agregar `UseSeeding()` y `UseAsyncSeeding()` únicamente si hay datos iniciales aprobados.
Los permisos, concurrencia y fallos del arranque DEBEN verificarse conforme al plan.

**Control**: [Evidencia de que los fundamentos requeridos funcionan antes de continuar].

## Fase 3: Historia US1 - [Título] (Prioridad: P1)

**Objetivo**: [Resultado aprobado].
**Dependencias**: [Identificadores previos].
**Verificación independiente**: [Escenarios de aceptación de la spec].

### Pruebas aprobadas

[Incluir tareas de pruebas automatizadas solo si la spec las aprueba. Las pruebas de
integración y su infraestructura requieren aprobación explícita en spec, plan y tareas.
Cuando se incluyan pruebas de regresión, comprobar el fallo esperado antes de corregir.]

### Implementación

- [ ] T005 [US1] Implementar contratos, validación, handler y mapeo del caso de uso en [ruta concreta del slice]; [RF-NNN].
- [ ] T006 [US1] Exponer el endpoint Minimal API con códigos HTTP y OpenAPI en [ruta concreta]; depende de T005; [RF-NNN].
- [ ] T007 [US1] Implementar la página o componente Blazor y su llamada Refit en [rutas concretas]; depende de T006; [RF-NNN].
- [ ] T008 [US1] Verificar aceptación, estados de carga, vacío, error y éxito, teclado y escritorio/móvil según el plan; depende de T007; [CE-NNN].

**Control**: [Resultado observable y evidencia de aceptación de US1].

## Fase 4: Historias adicionales

[Repetir la fase por historia, con identificadores únicos, prioridad, rutas, dependencias,
pruebas aprobadas y aceptación independiente. Eliminar esta sección si no aplica.]

## Fase final: Verificación y cierre

- [ ] T009 Verificar compilación de proyectos afectados y ejecutar las comprobaciones aprobadas en `plan.md`; depende de las tareas de implementación.
- [ ] T010 Revisar trazabilidad, contratos, límites frontend/backend, seguridad y cumplimiento constitucional; registrar evidencia y bloqueos en `tasks.md`.

## Dependencias y orden

1. Completar las iniciativas de menor número antes de iniciar esta implementación.
2. Completar preparación y fundamentos requeridos antes de las historias dependientes.
3. Implementar cada slice y su interfaz por prioridad, conservando aceptación independiente.
4. Generar migraciones solo después de completar el modelo y verificar compilación.
5. Ejecutar validaciones antes de cerrar tareas; no corregir defectos ajenos al alcance.

## Evidencia de verificación

| Tarea | Dependencias | Comprobación | Resultado o bloqueo |
|-------|--------------|--------------|---------------------|
| [TNNN] | [TNNN o ninguna] | [Comando o escenario observable] | [Pendiente] |

Registrar los comandos realmente ejecutados y sus resultados. No declarar verificaciones
que no se realizaron ni cerrar tareas bloqueadas. No crear commits sin solicitud explícita.
