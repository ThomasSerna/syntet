# Syntet

Estación de producción musical nativa en Rust, inspirada en el flujo de patrones de FL Studio y en las prácticas de ingeniería de las Craft Apps de Artcraft.

**Estado: planificación publicada; la aplicación todavía no está implementada.** El primer objetivo funcional será crear un beat completo, grabar voz, guardar el proyecto, recuperarlo y exportarlo. La visión incluye composición y sampling avanzados, mezcla, automatización, MIDI y plugins.

## Empezar aquí

1. Leer [producto y alcance](docs/product.md).
2. Consultar el [roadmap](docs/roadmap.md) y el [índice del backlog](docs/backlog.md).
3. Elegir una tarea en [GitHub Issues](https://github.com/ThomasSerna/syntet/issues), comprobar sus dependencias y leer los documentos indicados en ella.
4. Antes de implementar, revisar [arquitectura](docs/architecture.md), [desarrollo](docs/development.md) y [verificación](docs/testing.md).

Los agentes y colaboradores encuentran el procedimiento de continuidad en [AGENTS.md](AGENTS.md).

## Documentación

| Tema | Documento |
|---|---|
| Objetivos, usuarios y límites | [Producto](docs/product.md) |
| Inventario completo de capacidades | [Matriz funcional](docs/reference/fl-studio-matrix.md) |
| Método de observación y fuentes | [Investigación de caja negra](docs/reference/research-method.md) |
| Subsistemas y dependencias | [Arquitectura](docs/architecture.md) |
| Audio, transporte y grabación | [Motor de audio](docs/audio-engine.md) |
| Archivos y recuperación | [Formato de proyecto](docs/project-format.md) |
| Decisiones y alternativas | [ADR](docs/adr/README.md) |
| Calidad y aceptación | [Pruebas](docs/testing.md) |
| Colaboración y mantenimiento | [Desarrollo](docs/development.md) |
| Etapas de entrega | [Roadmap](docs/roadmap.md) |
| Épicas y tareas publicadas | [Backlog](docs/backlog.md) |
| Recursos y licencias | [Atribución](ATTRIBUTION.md) |

## Principios

- Rust nativo con egui/eframe y wgpu; Windows primero, con límites de plataforma explícitos.
- Flujo de patrones flexible, identidad visual propia y experiencia inicial para principiantes.
- Interfaz y ayuda en español e inglés; producción de estudio y biblioteca redistribuible.
- Un mismo núcleo musical para interfaz, CLI, agentes y exportación.
- Integridad de proyectos y tomas, evolución de formatos y resultados comprobables antes de declarar funciones terminadas.

GitHub Issues conserva el estado operativo, los responsables y la evidencia de cada tarea. Los documentos del repositorio conservan el alcance, las decisiones y los criterios de evolución; el índice local no duplica estados ni responsables.

No hay todavía comandos de compilación o ejecución de Syntet. Las dependencias concretas, el rendimiento, la sincronización de dispositivos y la compatibilidad de plugins deberán validarse en sus hitos.

## Referencias y licencia

La investigación utilizará documentación y observación de caja negra con material propio. Las fuentes públicas de Artcraft se registran en el [método de investigación](docs/reference/research-method.md); sus guías privadas no fueron revisadas. Los nombres de productos de terceros identifican referencias y no implican afiliación.

El destino acordado es código abierto y aplicación gratuita. La licencia permisiva exacta debe confirmarse antes de publicar una distribución; todavía no se otorga una licencia de código mediante este README. Los activos tendrán licencias y procedencia registradas individualmente.
