# Decisiones de arquitectura

Cada ADR conserva contexto, decisión, estado, consecuencias y validación pendiente. Una decisión sustituida se mantiene y enlaza su sucesora. Los acuerdos del producto están en [producto](../product.md); el estado operativo de las tareas está en GitHub Issues mediante el [backlog](../backlog.md).

| ADR | Estado | Decisión |
|---|---|---|
| [0001](0001-native-rust-ui.md) | Aceptado por el usuario | Rust nativo y egui/eframe con wgpu; Windows primero |
| [0002](0002-state-and-realtime.md) | Diseño adoptado; runtime por validar | Separar documento editable, operaciones y ejecución de audio |
| [0003](0003-versioned-projects.md) | Principios adoptados; esquema concreto propuesto | Persistencia independiente, versionada y recuperable |

Las versiones concretas de dependencias, resolución temporal, formato binario o JSON final, backend definitivo de audio y condiciones de aislamiento de plugins no quedan resueltas por citar una biblioteca. Su cierre exige una decisión y la evidencia de la tarea correspondiente.

Al añadir una decisión, registrar fecha, contexto, alternativas, elección, consecuencias y cómo se comprobará. La cantidad de ADR crece cuando una decisión real lo requiere.
