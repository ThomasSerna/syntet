# Backlog y continuidad

El backlog completo se publica en [GitHub Issues](https://github.com/ThomasSerna/syntet/issues). Este documento es el índice de las 23 épicas; el [inventario funcional](reference/fl-studio-matrix.md) enlaza las 157 tareas. No se duplican aquí sus estados, responsables ni cuerpos.

## Elegir el siguiente trabajo

1. Revisar el hito en [roadmap](roadmap.md) y abrir la épica correspondiente.
2. Leer la issue de capacidad, su preparación y todas sus dependencias. Una tarea futura publicada no está automáticamente lista para implementar.
3. Tomar la tarea y coordinar propiedad de archivos antes de trabajo paralelo.
4. Aplicar la aceptación de la issue y el procedimiento de [desarrollo](development.md). Registrar evidencia, documentación afectada y siguiente paso al finalizar.

M0 entrega documentos e issues; M1 comienza la viabilidad del núcleo. La aplicación no está implementada.

## Índice por subsistema

| Área | Épica | Capacidades publicables |
|---|---|---|
| E00 · Planificación y referencias | SYN-E00 · publicación pendiente | 5 |
| E01 · Audio y transporte | SYN-E01 · publicación pendiente | 6 |
| E02 · Proyecto e historial | SYN-E02 · publicación pendiente | 6 |
| E03 · Channel Rack y patrones | SYN-E03 · publicación pendiente | 6 |
| E04 · Piano Roll y expresión | SYN-E04 · publicación pendiente | 6 |
| E05 · Herramientas de composición | SYN-E05 · publicación pendiente | 7 |
| E06 · Playlist y arreglos | SYN-E06 · publicación pendiente | 6 |
| E07 · Sampler y pads | SYN-E07 · publicación pendiente | 7 |
| E08 · Editor de audio y slicing | SYN-E08 · publicación pendiente | 6 |
| E09 · Tiempo, tono y análisis | SYN-E09 · publicación pendiente | 7 |
| E10 · Grabación y tomas | SYN-E10 · publicación pendiente | 7 |
| E11 · Mezcla y ruteo | SYN-E11 · publicación pendiente | 7 |
| E12 · Instrumentos internos | SYN-E12 · publicación pendiente | 7 |
| E13 · Efectos y medición | SYN-E13 · publicación pendiente | 7 |
| E14 · Automatización y modulación | SYN-E14 · publicación pendiente | 7 |
| E15 · MIDI y controladores | SYN-E15 · publicación pendiente | 7 |
| E16 · VST3 y CLAP | SYN-E16 · publicación pendiente | 8 |
| E17 · Biblioteca y contenido | SYN-E17 · publicación pendiente | 7 |
| E18 · Render e intercambio | SYN-E18 · publicación pendiente | 7 |
| E19 · Interfaz y aprendizaje | SYN-E19 · publicación pendiente | 8 |
| E20 · CLI, automatización y agentes | SYN-E20 · publicación pendiente | 7 |
| E21 · Calidad y rendimiento | SYN-E21 · publicación pendiente | 8 |
| E22 · Mantenimiento y distribución | SYN-E22 · publicación pendiente | 8 |

## Contrato de las issues

- **Identidad:** título con ID estable y marcador `<!-- syntet-id: SYN-… -->`. Las épicas usan SYN-E00…SYN-E22; las capacidades usan una secuencia global SYN-001… con asociación permanente.
- **Contenido:** resultado, alcance, épica, hito objetivo, prioridad, preparación, dependencias enlazadas, aceptación, verificación, documentación y decisiones pendientes.
- **Tipos:** documentación, implementación e investigación. P0 identifica fundamentos o integridad bloqueantes; P1 el flujo de producción; P2 profundidad o ampliaciones posteriores. Prioridad no significa permiso para saltar dependencias.
- **Preparación:** planificada/por refinar mientras falten decisiones o dependencias; lista cuando cumpla la definición de preparación de desarrollo. El estado abierto/cerrado de GitHub es la autoridad de finalización.
- **Etiquetas iniciales:** documentación usa `documentation`, implementación usa `enhancement`, investigación usa `question` y barreras accesibles añaden `accessibility`. Tipo, hito y prioridad también quedan explícitos en el cuerpo.
- **Relaciones:** cada capacidad tiene una épica principal y referencias de dependencia. Los enlaces funcionan sin exigir sub-issues, nuevas etiquetas ni GitHub Projects. Los hitos M0–M6 están definidos en el roadmap y en cada tarea; esta entrega no presupone milestones nativos de GitHub.

## Actualizar sin perder trabajo

Buscar el marcador entre issues abiertas y cerradas antes de crear. Una respuesta de creación perdida se reconcilia antes de repetir; un ID duplicado requiere resolución. Revisar cambios humanos antes de reemplazar un cuerpo. Los IDs conservan identidad aunque el título o el hito cambien.

Al cambiar alcance, actualizar documentos normativos e issues afectadas en la misma entrega. La aceptación detallada y evidencia siguen en GitHub; los índices enlazan su ubicación. El informe de [auditoría](reference/publication-audit.md) registra únicamente la verificación fechada de esta publicación.
