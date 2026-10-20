# Desarrollo y colaboración

Syntet comienza con documentación y backlog. Esta entrega no contiene código de la aplicación, manifiestos Cargo, CI de Rust ni comandos propios ejecutables. La [arquitectura](architecture.md) define límites objetivo; el [roadmap](roadmap.md) decide cuándo se materializan.

## Fuentes de autoridad

| Información | Fuente |
|---|---|
| Público, objetivos y límites | [Producto](product.md) |
| Capacidades y referencia funcional | [Matriz de FL Studio](reference/fl-studio-matrix.md) |
| Diseño técnico y decisiones | [Arquitectura](architecture.md) y [ADR](adr/README.md) |
| Resultados de cada entrega | [Roadmap](roadmap.md) |
| Estado, aceptación, responsables y evidencia de trabajo | [GitHub Issues](https://github.com/ThomasSerna/syntet/issues) |
| Navegación del backlog | [Índice local](backlog.md) |

El índice local enlaza las issues; no mantiene una segunda copia de estados o responsables. Los cambios de alcance actualizan producto, matriz y tareas afectadas en la misma entrega. Una propuesta técnica permanece identificada como propuesta hasta resolver su decisión o experimento.

## Antes de tomar una tarea

1. Leer las instrucciones de [AGENTS.md](../AGENTS.md) y el documento de dominio indicado por la issue.
2. Revisar la issue y sus dependencias en GitHub, incluidos cambios humanos recientes.
3. Comprobar que está lista para comenzar: resultado acotado, decisiones bloqueantes resueltas y verificación definida.
4. Asignar responsable al tomarla y registrar el alcance del trabajo. Si se trabaja en paralelo, acordar propiedad de archivos y puntos de integración.

Una tarea futura puede tener una capacidad y aceptación claras y todavía requerir refinamiento técnico. Eso no autoriza a elegir en silencio una alternativa que cambie el comportamiento, los datos persistentes o una frontera pública.

## Identidad y estados

Cada issue tendrá un ID estable `SYN-…` y un marcador de identidad en su cuerpo. Al reanudar una publicación se busca ese marcador entre issues abiertas y cerradas antes de crear otra. Un título nuevo no crea una identidad nueva; un ID publicado no se renumera.

Se utilizarán las etiquetas existentes `documentation`, `enhancement`, `question`, `accessibility` y `bug` según corresponda. Tipo, hito, prioridad y preparación se expresan en campos explícitos de la issue; no se presupone una configuración de GitHub Projects o milestones nativos.

La preparación distingue tareas listas, tareas por refinar y tareas bloqueadas. El estado abierto/cerrado de GitHub registra el cierre del trabajo; la asignación identifica quién lo lleva. No se inventan responsables, fechas ni porcentajes de avance.

## Cambios y revisiones

El repositorio vacío recibirá primero la documentación inicial en `main`. Los cambios siguientes se realizarán en ramas `codex/<tema>` o en la convención acordada con el colaborador, con una PR por resultado revisable.

Antes de editar, identificar callers, formatos, tests, documentación y contratos afectados. Conservar validación, recuperación y manejo de errores al mover código. Agrupar un gesto de edición en una operación de historial. Separar la actualización de una dependencia de cambios funcionales ajenos.

La descripción de PR deberá explicar el comportamiento final, la comprobación realizada y los límites conocidos. Una modificación que cambie datos, tiempos, protocolos o límites entre capas actualizará su ADR o documento normativo en la misma PR.

Al cerrar una tarea se debe poder comprobar:

- El resultado satisface todos los criterios de aceptación aplicables.
- La evidencia identifica commit, escenario y resultado; los casos omitidos están registrados.
- La documentación y las tareas afectadas están actualizadas.
- Los fallos o límites pendientes están enlazados y no ocultos bajo una afirmación de cobertura completa.

Para una tarea documental, la evidencia es la revisión de contenido, enlaces y coherencia. Para una función de audio, se añade la evidencia musical, DSP o de hardware que exija la issue.

## Workspace y dependencias futuros

El workspace se introducirá en M1. Las crates aparecerán cuando tengan responsabilidad real, implementación y pruebas; los módulos internos contendrán lo que todavía no justifique una crate propia. La [arquitectura](architecture.md) establece dirección de dependencias y excepciones FFI auditables.

- Centralizar versiones, metadatos y dependencias comunes en el manifiesto raíz cuando exista.
- Mantener el lockfile de aplicación y ejecutar comprobaciones reproducibles con `--locked`.
- Fijar dependencias Git a revisiones inmutables y documentar motivo y licencia.
- Registrar toolchain mínimo y targets soportados al introducirlos; no inferir soporte de plataforma por haber compilado una biblioteca.
- Actualizar dependencias mediante cambios revisables con las regresiones pertinentes; agrupar cambios relacionados y conservar una vía de reversión.
- Mantener independientes versión de aplicación, esquema de proyecto y protocolo de control.

CPAL/WASAPI y las bibliotecas de DSP, formatos o resampling siguen siendo propuestas de integración pendientes de validar. La elección de Rust nativo con egui/eframe sí está confirmada. No se instala un motor de REA ni una herramienta de audio para redactar documentación.

## Comprobaciones futuras

Los siguientes son objetivos del flujo de desarrollo, no comandos disponibles en la entrega documental:

| Comprobación prevista | Condición de incorporación |
|---|---|
| Formato, clippy y tests Rust con lockfile | Primer workspace funcional en M1. |
| Verificación de capas mediante metadata de Cargo | Primeras dependencias entre crates; registrar excepciones explícitas. |
| Corpus fijado por revisión y hash | Primer fixture externo utilizado. |
| Tests sin ventana y render offline | Núcleo musical y formato persistente operativos. |
| Interacciones y capturas egui | Primer flujo de interfaz de M2. |
| Comprobaciones de assets y atribución | Primer recurso incluido. |
| Empaquetado y smoke tests Windows | Primera versión distribuible, antes de publicarla. |

La futura herramienta `xtask` podrá agrupar estas comprobaciones cuando existan tareas reales que ejecutar. Sus subcomandos se documentarán desde su implementación y `--help`; no se publicarán instrucciones de ejecución ficticias.

## Formatos, corpus y recursos

Toda evolución de datos persistentes seguirá [project-format.md](project-format.md). Una actualización no descartará en silencio estado desconocido o incompatible. Las migraciones incluirán fixtures anteriores y pruebas de recuperación.

Los recursos incorporados deben tener permiso de redistribución y una fila en [ATTRIBUTION.md](../ATTRIBUTION.md). Los corpus externos se fijarán por revisión y hash. El material de observación de FL Studio seguirá el [método de investigación](reference/research-method.md); las guías privadas de Artcraft no están disponibles para este proyecto.

La licencia concreta del código se resolverá antes de publicación de código de aplicación; MIT/Apache-2.0 es una propuesta, no una licencia que esta documentación haya otorgado. El objetivo confirmado es código abierto y gratuito con recursos redistribuibles.

## Publicación y diagnóstico

Cada versión distribuible identificará versión, commit, plataforma, cambios y compatibilidad de datos. El empaquetado se derivará de metadatos centrales cuando exista el workspace, evitando números de versión repetidos manualmente.

Los informes de diagnóstico serán locales y revisables antes de compartir. Conservarán configuración técnica necesaria para reproducir el fallo y excluirán audio privado, tokens y rutas personales cuando no sean imprescindibles. No se subirá información automáticamente.

## Referencias de estructura

- [PhotoCraft: contribución](https://github.com/storytold/photocraft/blob/main/docs/contributing.md).
- [PhotoCraft: verificación de capas](https://github.com/storytold/photocraft/blob/main/xtask/src/layers.rs).
- [PhotoCraft: CI](https://github.com/storytold/photocraft/blob/main/.github/workflows/ci.yml).
- [FilmCraft: arquitectura](https://github.com/storytold/filmcraft/blob/main/docs/architecture.md).

Estas son referencias públicas de prácticas. Syntet tendrá sus propios contratos y verificaciones para audio; no se atribuye acceso a `craftrules` ni a planes locales de los autores.
