# Arquitectura de Syntet

Estado: diseño de referencia aprobado; implementación y rendimiento pendientes de validación. Fecha: 2026-10-20.

Leer primero [producto](product.md). Para decisiones y alternativas, consultar [ADR](adr/README.md). El [backlog](backlog.md) enlaza el trabajo ejecutable.

## Modelo de responsabilidades

Syntet es una aplicación nativa Rust con egui/eframe y wgpu. La interfaz, los dispositivos y los plugins son fronteras del sistema; el proyecto musical y sus operaciones permanecen independientes de ellos.

| Límite lógico | Responsabilidad | Dependencias permitidas |
|---|---|---|
| Fundamentos | Tiempo musical y de muestras, unidades, IDs y eventos | Biblioteca estándar y dependencias de propósito acotado |
| Proyecto | Instrumentos, patrones, notas, clips, pistas, parámetros, recursos y ruteo como datos | Fundamentos |
| Edición | Validación de operaciones, transacciones y deshacer/rehacer | Proyecto y fundamentos |
| DSP y render | Voces, efectos, planes de ejecución y mezcla | Proyecto, fundamentos y primitivas DSP |
| Persistencia y recursos | Esquema en disco, migraciones, importación, cachés y trabajos de archivos | Proyecto y fundamentos; render para exportación |
| Sesión y coordinación | Comandos, revisiones, trabajos, transporte y publicación de planes | Edición, render y servicios |
| Adaptadores | Audio del sistema, MIDI, hosts de plugins y particularidades del SO | Contratos del núcleo que implementan |
| Interfaces | egui, CLI, protocolo local y MCP | Servicios públicos de la sesión |

La tabla define dirección y responsabilidades, no una obligación de crear una crate por fila. Una implementación inicial puede agrupar módulos cohesivos; se separarán cuando haya implementación real, dependencias específicas o aislamiento comprobable. El verificador de capas futuro comprobará el grafo Cargo y sus excepciones explícitas.

## Entidades e invariantes

- Un instrumento produce sonido; un patrón contiene eventos que pueden dirigirse a varios instrumentos.
- Un clip referencia contenido y lo coloca en el arreglo. Recortar o repetir un clip conserva la identidad del contenido fuente salvo una operación explícita de copia independiente.
- Una pista de arreglo organiza clips. Un canal de mezcla procesa audio. Su relación no es obligatoriamente uno a uno.
- La ayuda para principiantes puede enlazar instrumento, pista y canal, sin eliminar el modelo flexible.
- Las notas y automatizaciones usan tiempo musical; el transporte convierte posiciones al tiempo de muestras mediante un mapa de tempo.
- Los parámetros usan IDs estables, unidades, rangos y valores válidos. Ni traducciones ni posiciones de controles forman su identidad.
- Los recursos originales permanecen identificables; una edición derivada no sobrescribe el archivo fuente.
- Se validan referencias, rangos, longitudes, valores finitos y ruteo. Un ciclo no admitido produce un error explicable antes de publicar un plan de audio.

Estas identidades se mantienen al guardar, deshacer, importar y automatizar. No se serializan handles de plugins, streams, objetos egui, buffers decodificados ni el grafo ejecutable.

## Edición y control

Las interfaces traducen sus entradas a operaciones tipadas de edición. JSON se interpreta y valida únicamente en el adaptador de automatización. Los nombres de tipos y métodos concretos se fijarán al implementar; los contratos de este documento describen comportamiento.

Una operación sigue esta secuencia:

1. Comprobar parámetros, referencias, revisión del proyecto y habilitación.
2. Preparar el cambio sin modificar parcialmente el documento.
3. Aplicar la transacción, incrementar la revisión y registrar historial.
4. Notificar resultado y cambios observables a las interfaces.
5. Preparar en segundo plano los recursos o planes de audio necesarios.

Un arrastre continuo constituye un paso de deshacer. El historial musical no incluye cada frame de pintura ni cambia el reloj de reproducción. Una solicitud de agente basada en una revisión antigua recibe un conflicto y conserva el proyecto; el cliente debe inspeccionar antes de reenviar una edición.

Los trabajos largos tienen identidad, progreso, cancelación y resultado explícitos. El hilo de interfaz permanece disponible mientras se decodifica, exporta o analiza audio.

## Estado y concurrencia

Se distinguen tres estados:

| Estado | Dueño | Propósito |
|---|---|---|
| Documento autoritativo | Sesión/editor | Edición, historial, guardado e inspección |
| Plan preparado y estado DSP | Motor de render | Ejecución musical y señal |
| Estado de vista y trabajo | Interfaz o servicio correspondiente | Selección visual, ventanas, progreso y cachés |

El editor publica planes preparados o mensajes de parámetros por canales acotados. El callback no toma el lock del documento, compila grafos ni hace serialización. Recursos grandes y plugins se preparan y retiran fuera del callback; intercambiar una referencia no debe provocar allí la destrucción del último propietario.

El motor musical y DSP se comparte entre reproducción y render offline. Dispositivos, disco y velocidad de ejecución cambian mediante adaptadores. Los detalles de scheduling y captura se especifican en [motor de audio](audio-engine.md).

## Extensión y compatibilidad

- Incorporar un instrumento o efecto exige contrato de parámetros estable, estado persistible y pruebas de señal, además de su UI.
- Incorporar un plugin externo agrega un host contenido. La FFI eventual queda aislada detrás de una API segura, con propiedad y ciclo de vida documentados.
- Incorporar un formato agrega un adaptador de importación/exportación y fixtures; no convierte la estructura en memoria en formato público.
- App, archivo y protocolo tienen versiones independientes.
- Un cambio incompatible documenta migración, rechazo seguro y escenarios de regresión antes de integrarse.
- Las dependencias se centralizan; el lockfile y las actualizaciones se revisan junto a las pruebas afectadas.

No se crea un ABI propio de plugins ni un framework genérico de extensiones en esta entrega.

## Decisiones y evidencia

| Decisión | Estado |
|---|---|
| Rust nativo, egui/eframe y wgpu; Windows primero | Confirmada por el usuario; [ADR 0001](adr/0001-native-rust-ui.md) |
| Separación entre documento, edición y render | Diseño adoptado; pruebas de runtime pendientes; [ADR 0002](adr/0002-state-and-realtime.md) |
| Esquema persistente independiente y versionado | Principio adoptado; contenedor exacto propuesto; [ADR 0003](adr/0003-versioned-projects.md) |
| Backend CPAL/WASAPI, colas y primitivas DSP concretas | Propuestas por validar en M1 |

Fuentes de estructura: [PhotoCraft AGENTS](https://github.com/storytold/photocraft/blob/main/AGENTS.md), [verificador de capas](https://github.com/storytold/photocraft/blob/main/xtask/src/layers.rs), [arquitectura de FilmCraft](https://github.com/storytold/filmcraft/blob/main/docs/architecture.md), [SoundCraft AGENTS](https://github.com/storytold/soundcraft/blob/main/AGENTS.md). Las normas privadas craftrules y planes locales originales de Artcraft no se revisaron.
