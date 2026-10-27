# Especificación: [NOMBRE DE LA INICIATIVA]

**Rama**: `[NNN-nombre]`

**Creación**: [AAAA-MM-DD]

**Estado**: Borrador

**Entrada**: Descripción del usuario: "$ARGUMENTS"

## Alcance y límites

**Objetivo**: [Problema concreto y personas beneficiadas].
**Incluido**: [Comportamientos aprobados].
**Excluido**: [Límites explícitos para evitar funcionalidad especulativa].

Esta iniciativa DEBE respetar `.specify/memory/constitution.md`. La documentación
DEBE residir en `specs/NNN-nombre/` y contener exactamente `spec.md`, `plan.md` y
`tasks.md`, generados en las fases correspondientes. La spec define el comportamiento;
las decisiones técnicas y los contratos detallados se documentan en `plan.md`.

## Historias de usuario y aceptación

Las historias DEBEN priorizarse y poder verificarse de forma independiente.
Agregar o quitar historias según el alcance real, sin conservar ejemplos vacíos.

### Historia US1 - [Título breve] (Prioridad: P1)

[Describir el recorrido del usuario y su resultado observable].

**Justificación de prioridad**: [Valor y motivo de su orden].
**Verificación independiente**: [Acciones y resultado que demuestran el cumplimiento].

**Escenarios de aceptación**:

1. **Dado** [estado inicial], **cuando** [acción], **entonces** [resultado comprobable].
2. **Dado** [entrada inválida o fallo], **cuando** [acción], **entonces** [respuesta esperada].

### Historia US2 - [Título breve] (Prioridad: P2)

[Describir el recorrido del usuario y su resultado observable].

**Justificación de prioridad**: [Valor y motivo de su orden].
**Verificación independiente**: [Acciones y resultado que demuestran el cumplimiento].

**Escenarios de aceptación**:

1. **Dado** [estado inicial], **cuando** [acción], **entonces** [resultado comprobable].

### Casos límite

- [Comportamiento ante entradas inválidas o límites del dominio].
- [Comportamiento ante falta de datos, fallos de comunicación o acceso no autorizado si aplica].

## Requisitos

### Requisitos funcionales

- **RF-001**: El sistema DEBE [capacidad concreta y verificable].
- **RF-002**: El sistema DEBE [validación o regla de negocio observable].
- **RF-003**: El usuario DEBE poder [resultado del recorrido aprobado].

Las dudas que impidan definir aceptación DEBEN identificarse como
`PENDIENTE DE ACLARACIÓN: descripción` y resolverse antes de aprobar la spec.

### Interfaz y límites de acceso

[Si hay UI, definir estados de carga, vacío, error y éxito, accesibilidad por teclado,
etiquetas y adaptación a escritorio y móvil. Si hay acceso restringido, definir actores,
permisos y rechazo esperado. Indicar no aplica cuando corresponda.]

### Entidades principales

[Si hay datos, describir entidades, atributos relevantes y relaciones del dominio,
sin prescribir detalles EF Core. Incluir datos iniciales únicamente si son necesarios.]

## Estrategia de verificación aprobada

**Aceptación**: [Comprobaciones observables por historia].
**Pruebas automatizadas**: [Aprobadas con alcance específico, o no solicitadas].
**Pruebas de integración e infraestructura**: [Aprobación explícita y alcance, o no autorizadas].

Las pruebas e infraestructura NO DEBEN agregarse por defecto. El plan DEBE concretar
la estrategia aprobada y las tareas DEBEN incluir su ejecución y evidencia.

## Criterios de éxito

Los criterios DEBEN ser medibles y expresar resultados, sin depender de una implementación.

- **CE-001**: [Resultado cuantificable del recorrido principal].
- **CE-002**: [Resultado observable ante un fallo o caso límite].

## Supuestos y dependencias

- [Supuesto fundamentado sobre usuarios, datos o entorno].
- [Dependencia real y condición necesaria para comenzar].
- [Iniciativas de menor número que deben completarse antes de implementar].
