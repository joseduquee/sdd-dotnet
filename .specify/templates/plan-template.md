# Plan de implementación: [NOMBRE DE LA INICIATIVA]

**Rama**: `[NNN-nombre]` | **Fecha**: [AAAA-MM-DD] | **Spec**: [Ruta a spec.md]

**Entrada**: `specs/NNN-nombre/spec.md` aprobada.

Este documento se completa mediante `speckit.plan`. Si no existe `spec.md`, detenerse:
`Ejecución detenida: antes de ejecutar speckit.plan debe crear el archivo spec.md mediante speckit.specify.`

## Resumen

[Necesidad aprobada, alcance y enfoque técnico. No agregar funcionalidad ajena a la spec.]

## Contexto técnico

**Plataforma**: .NET 11 y C#; [versión exacta del SDK y compatibilidad de paquetes].
**Backend**: ASP.NET Core Minimal APIs con Vertical Slice Architecture.
**Frontend**: Blazor Web App con Razor Components; [modo de renderizado y justificación].
**Comunicación**: Refit; [contratos DTO y límites entre proyectos].
**Persistencia**: EF Core, PostgreSQL y Npgsql; [cambios aplicables o no aplica].
**Estilos**: CSS propio en `wwwroot/app.css`; Lucide Icons cuando corresponda.
**Dependencias nuevas**: [Versiones, necesidad real y compatibilidad; ninguna si no aplica].
**Validación**: [Compilación, aceptación y pruebas aprobadas; herramientas y alcance].
**Despliegue**: [Entorno, configuración externa y restricciones].
**Rendimiento y escala**: [Objetivos medibles derivados de la spec; sin cifras inventadas].

## Comprobación constitucional

Este control DEBE realizarse antes de investigar y repetirse al finalizar el diseño.
Cada punto DEBE registrar evidencia o justificar por qué no aplica. Un incumplimiento
bloquea la implementación; documentarlo no autoriza una excepción.

- [ ] I. Spec aprobada, tres artefactos canónicos y orden numérico respetado.
- [ ] II. Minimal APIs por caso de uso; contratos, validación, handlers y OpenAPI definidos.
- [ ] III. Proyecto Blazor separado, Refit, sin acceso a EF Core desde frontend y CSS propio.
- [ ] IV. Configuraciones EF Core separadas, migraciones coherentes y seeds idempotentes si aplican.
- [ ] V. Alcance mínimo, dependencias justificadas, seguridad y verificaciones observables.
- [ ] Documentación propia íntegramente en español y stack obligatorio sin sustituciones.
- [ ] Incumplimientos heredados que afecten esta iniciativa resueltos antes de implementar.

**Resultado inicial**: [Conforme o bloqueado; evidencias].
**Resultado posterior al diseño**: [Conforme o bloqueado; evidencias].

## Investigación y decisiones

[Registrar aquí las alternativas evaluadas, decisiones, razones y dudas resueltas.
No generar un documento de investigación adicional.]

## Diseño por casos de uso

### Slices del backend

| Caso de uso | Ruta del slice | Endpoint | Handler y validación | Requisito |
|------------|----------------|----------|----------------------|-----------|
| [Nombre] | [Ruta concreta] | [Método y ruta HTTP] | [Responsabilidades] | [RF-NNN] |

### Contratos HTTP

[Documentar aquí solicitudes, respuestas DTO, códigos de estado, ProblemDetails,
autorización y metadatos OpenAPI por endpoint; sin generar una carpeta de contratos.]

### Frontend

[Rutas de páginas y componentes, cliente Refit, modo de renderizado, estados de carga,
vacío, error y éxito, navegación accesible y comportamiento en escritorio y móvil.]

### Modelo de datos y persistencia

[Entidades, relaciones, restricciones, índices y configuraciones IEntityTypeConfiguration<T>.
Definir migración coherente, seeds aprobados y mecanismo centralizado de arranque.
Documentar permisos, concurrencia y fallos; indicar no aplica cuando corresponda.]

### Seguridad y diagnóstico

[Validación en backend, autorización aprobada, secretos externos, logs estructurados
y tratamiento de errores sin exponer información sensible.]

## Estructura del proyecto

### Documentación de la iniciativa

```text
specs/NNN-nombre/
├── spec.md
├── plan.md
└── tasks.md
```

La iniciativa DEBE contener exactamente esos tres archivos. `speckit.plan` no crea
`tasks.md`; lo genera la fase posterior `speckit.tasks`.

### Código fuente

El backend DEBE ubicarse en `app/backend/` y el frontend en `app/frontend/`.

```text
app/
├── backend/
│   ├── src/
│   └── tests/
└── frontend/
    ├── src/
    └── tests/
```

[Precisar los proyectos y rutas reales de slices, infraestructura y componentes.
Las carpetas de pruebas solo se crean si están aprobadas; este árbol no las autoriza.]

## Verificación y ejecución local

[Incluir aquí los prerrequisitos, configuración sin secretos, comandos compatibles con
el repositorio, comprobaciones de aceptación y evidencia esperada. Las pruebas de
integración y su infraestructura requieren aprobación explícita en spec, plan y tareas.]

## Complejidad y bloqueos

| Decisión o incumplimiento | Necesidad e impacto | Alternativa simple | Resolución requerida |
|--------------------------|---------------------|--------------------|----------------------|
| [Descripción o ninguno] | [Evidencia] | [Evaluación] | [Decisión humana o tarea previa] |
