# Roadmap por resultados

La meta es una estación de producción musical amplia. La primera producción completa es un hito intermedio, no el límite del producto. Las 23 épicas del [backlog](backlog.md) cubren capacidades de varios hitos; cerrar una versión no exige terminar todas sus épicas.

El estado operativo, responsables y evidencia están en [GitHub Issues](https://github.com/ThomasSerna/syntet/issues). Este documento define resultados y puertas de salida, sin duplicar los estados de cada tarea. No se han acordado fechas de entrega ni estimaciones de esfuerzo.

## M0 · Planificación publicada

**Entrega actual:** documentación del producto y arquitectura, decisiones registradas, matriz funcional y backlog completo publicado en GitHub.

La salida exige una issue por capacidad conocida, una épica principal por tarea, dependencias válidas y un índice con URLs reales. Las decisiones confirmadas se distinguen de propuestas y experimentos. Se comprobarán enlaces, IDs y ausencia de ciclos; una publicación parcial permanecerá identificada como parcial.

M0 no crea la aplicación, el workspace ni resultados de rendimiento. La evidencia de cierre es documental y de publicación.

## M1 · Fundamentos verificables

Introducir el workspace y demostrar mediante recorridos sin ventana el modelo musical, comandos, tiempo, persistencia, reproducción, exportación y captura.

La salida exige un patrón y material de audio originales que puedan reproducirse, guardarse, reabrirse y exportarse con el mismo núcleo de procesamiento. Una toma debe escribirse de forma recuperable y permitir comprobar su alineación y deriva. Las comprobaciones de capas y CI acompañan el núcleo desde esta etapa.

El experimento con dispositivos decidirá si CPAL/WASAPI compartido satisface la primera grabación; cualquier alternativa y sus consecuencias quedarán registradas antes de ampliar el adaptador. La seguridad del callback y la recuperación son condiciones de avance, no tareas pospuestas a una versión profesional.

## M2 · Primera producción completa

Construir un flujo real para principiantes: escoger sonidos, programar batería y melodía, organizar secciones, grabar voz sin monitorización en vivo, mezclar, guardar, recuperar y exportar.

Incluye las partes iniciales de Channel Rack, Piano Roll, Playlist, sampler, instrumentos y efectos esenciales, automatización básica, biblioteca, formatos de intercambio y control programático. La interfaz y el tutorial estarán en español e inglés.

La salida exige completar ese recorrido desde la interfaz en Windows y repetirlo con el control programático aplicable; el proyecto reabierto conserva su estado. Teclado, etiquetas accesibles y escalado se verifican con el flujo, no después de añadir todas las funciones.

## M3 · Composición y sampling avanzados

Ampliar herramientas creativas de notas, variaciones, slicing, edición de ondas, capas y multisampling, así como diseño sonoro y organización de presets.

La salida exige transformar material editable con preescucha y deshacer, conservar originales y recuperar instrumentos y recursos después de guardar. Cada herramienta tendrá ejemplos musicales y límites explícitos; no se consideran equivalentes dos herramientas por compartir un nombre.

## M4 · Producción de estudio ampliada

Incorporar gestión de tomas, automatización avanzada, buses, envíos, sidechains y controladores MIDI de estudio.

La salida exige proyectos con composición, voz y procesamiento paralelo coherentes en reproducción y exportación. El desconectar un controlador o un dispositivo no deja notas sostenidas ni destruye el proyecto. Las rutas y automatizaciones mantienen su identidad al reordenar, traducir y reabrir la sesión.

## M5 · Plugins y procesamiento avanzado

Integrar VST3 y CLAP, sus editores y estado, latencias y rutas de buses, junto con las capacidades avanzadas de tiempo y tono acordadas.

La salida exige una matriz de plugins representativos verificados: cargar, tocar, automatizar, guardar, reabrir y exportar. El escaneo se aísla y los plugins ausentes conservan su estado recuperable. La contención de fallos durante procesamiento tiene una investigación propia y no se promete como consecuencia del escaneo aislado.

La separación de stems, limpieza avanzada y otros algoritmos condicionados por modelos o calidad se investigarán con corpus, licencias y costes medidos antes de comprometer una implementación. Exportar stems de pistas y separar una mezcla existente seguirán siendo capacidades distintas.

## M6 · Consolidación y distribución

Ampliar los proyectos y combinaciones comprobados, consolidar rendimiento y recuperación y preparar distribución Windows, versiones y mantenimiento.

La salida exige empaquetado probado desde una instalación limpia, pruebas representativas de sesiones y hardware, historial de compatibilidad de archivos y protocolo, y diagnóstico revisable. Los presupuestos de CPU, memoria y latencia deberán estar sustentados por mediciones reproducibles.

La arquitectura conservará el camino a Linux y macOS. Un puerto requiere sus propias comprobaciones de dispositivos, ventanas, plugins y distribución; la preparación arquitectónica no cuenta como soporte entregado.

## Dependencias entre entregas

M0 prepara M1; M1 demuestra los límites técnicos que sostienen M2. M3 y M4 amplían el flujo de M2 y podrán tener tareas independientes en paralelo. M5 requiere identidad de parámetros, persistencia y grafo de audio ya comprobados. M6 incorpora consolidación transversal y su salida final reúne las evidencias del producto ampliado.

Un criterio de integridad puede bloquear cualquier hito posterior. Una dependencia entre tareas identifica un prerrequisito concreto, no obliga a terminar una épica completa. Las tareas de calidad, documentación y accesibilidad acompañan cada capacidad aunque también exista una épica de consolidación.

## Continuidad de trabajo

Se comienza por una tarea lista, con responsable y alcance claros. Al completar una entrega se comprueba aceptación, se enlaza evidencia y se registra el siguiente paso. Los cambios de alcance se deciden en producto y ADR y se propagan a las issues afectadas.

Las reglas operativas están en [development.md](development.md); los escenarios de validación, en [testing.md](testing.md). Los límites acordados —producción de estudio, formato propio y cobertura por capacidades— permanecen en [product.md](product.md).
