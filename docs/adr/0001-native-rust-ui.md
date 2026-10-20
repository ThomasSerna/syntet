# ADR 0001: interfaz nativa Rust

Fecha: 2026-10-20. Estado: aceptado por el usuario.

## Contexto

Syntet necesita un editor musical con secuenciador, Piano Roll, arreglo y mezclador. El usuario pidió una base inspirada en las Craft Apps, Rust nativo, Windows primero y una experiencia familiar con identidad propia. Tras comparar egui/eframe, Iced y Slint, eligió egui/eframe.

## Decisión

Utilizar Rust con egui/eframe y wgpu para la aplicación de escritorio. El núcleo musical permanecerá independiente de la UI. La primera experiencia se validará con un prototipo nativo directo después de comprobar audio y persistencia.

La UI y su ayuda estarán disponibles en español e inglés. Cada control personalizado tendrá nombres accesibles, navegación y alternativas de teclado apropiadas. Los identificadores de dominio no dependen del texto traducido.

## Alternativas consideradas

Iced ofrece un modelo explícito de mensajes y Canvas; su accesibilidad upstream y las necesidades de widgets musicales requerían comprobación adicional. Slint aporta herramientas declarativas, pero incorpora su DSL y una licencia diferente. El usuario prefirió continuidad con la base de Artcraft después de conocer estas diferencias.

## Consecuencias

Los editores musicales y la identidad visual se implementarán en Syntet. Disponer de AccessKit no demuestra por sí solo que un Piano Roll personalizado sea accesible. Egui permanecerá contenido en la capa de interfaz, de modo que su evolución no cambie el formato de proyecto ni la semántica de edición.

## Validación pendiente

Probar selección, arrastre, zoom, teclado y foco en Windows; nombres y estados con lector de pantalla; distribución en español/inglés y escalas DPI. Fijar versiones compatibles al iniciar la implementación. No se han medido FPS, consumo o experiencia accesible.

Referencias: [egui](https://github.com/emilk/egui), [egui_kittest](https://docs.rs/egui_kittest/latest/egui_kittest/), [PhotoCraft AGENTS](https://github.com/storytold/photocraft/blob/main/AGENTS.md).
