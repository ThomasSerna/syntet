# AGENTS.md

## Silent execution

- Remain completely silent while working.
- Do not send acknowledgements, progress/status updates, intermediate results, reasoning, or narration of commands, tools, file operations, edits, builds, or tests.
- Do not send messages between tool calls.
- Complete all requested work and verification before responding.
- Send exactly one concise user-facing message when the entire task is complete.
- Interrupt only if essential user input or permission is strictly required to continue.

## Continuidad

1. Leer [producto](docs/product.md) y [roadmap](docs/roadmap.md) al comenzar trabajo en Syntet.
2. Consultar [backlog](docs/backlog.md), abrir la issue correspondiente y comprobar dependencias, decisiones pendientes y aceptación antes de editar. Registrar la asignación al tomarla; preservar el trabajo de otros colaboradores.
3. Para cambios de dominio o integración, leer [arquitectura](docs/architecture.md) y los [ADR](docs/adr/README.md). Para audio, leer [motor](docs/audio-engine.md); para archivos, [formato](docs/project-format.md).
4. Aplicar el procedimiento de [desarrollo](docs/development.md) y las comprobaciones pertinentes de [pruebas](docs/testing.md). Cerrar una tarea con evidencia y límites explícitos; dejar el siguiente paso en la issue.

## Estado y fuentes de autoridad

- El repositorio comienza con documentación y backlog. No hay aplicación ni pruebas de audio implementadas.
- Producto y matriz funcional definen lo comprometido; arquitectura y ADR definen límites y decisiones. GitHub Issues conserva aceptación específica, dependencias, estado, responsables y evidencia.
- Cambiar alcance exige actualizar los documentos normativos y las issues afectadas en la misma entrega. Revisar cambios humanos antes de actualizar una issue; mantener sus identificadores `SYN-…` y marcador `syntet-id`.
- Una tarea de investigación no demuestra una capacidad implementada. Una función requiere evidencia del recorrido que promete; un menú conectado no basta.

## Límites técnicos

- Dominio musical independiente de UI, dispositivo y objetos de plugins. Interfaz, CLI y agentes comparten operaciones tipadas.
- El callback procesa planes y buffers preparados. Disco, serialización, compilación de grafos y retirada de recursos grandes pertenecen a otros hilos.
- Preservar proyectos y fuentes originales; validar entradas y devolver errores recuperables. Los cambios incompatibles de datos o protocolo requieren versión, migración o rechazo explícito y pruebas.
- Añadir módulos o crates con una responsabilidad real y dependencias permitidas. Evolucionar aplicación, formato y protocolo por separado.
- Investigar FL Studio mediante el [método de caja negra](docs/reference/research-method.md). Usar recursos propios o con redistribución verificada y registrarlos en [ATTRIBUTION.md](ATTRIBUTION.md).
