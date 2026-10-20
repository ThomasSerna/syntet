# Producto: Syntet

Estado: planificación; aplicación aún sin implementar. Este documento fija la intención del producto. La ejecución y la evidencia de cada capacidad pertenecen a [GitHub Issues](https://github.com/ThomasSerna/syntet/issues).

## Propósito y usuarios

Syntet será una estación de producción musical nativa en Rust para crear beats, grabar voces, editar, mezclar y exportar temas completos. La audiencia inicial son principiantes de hip hop, trap y drill. El aprendizaje inicial no limita la profundidad futura: el backlog incluye producción de estudio avanzada.

El recorrido principal empieza con un kit, continúa con batería, bajo y melodía, organiza secciones en el arreglo, graba una voz y termina con una mezcla exportada y un proyecto editable que se puede reabrir. El tutorial será opcional y utilizará las operaciones reales del editor.

## Decisiones confirmadas

| Aspecto | Acuerdo |
|---|---|
| Plataforma | Windows primero, preservando límites que permitan futuros puertos. |
| Implementación | Proyecto propio modular en Rust; interfaz nativa egui/eframe con wgpu. |
| Referencias | Flujo musical de FL Studio y prácticas públicas de las Craft Apps de Artcraft. |
| Organización musical | Instrumentos, patrones, clips y canales de mezcla independientes; valores iniciales sencillos y ayuda progresiva. |
| Experiencia | Identidad visual propia, conceptos familiares y herramientas accesibles para principiantes. |
| Idiomas | Interfaz y ayuda en español e inglés desde la primera versión utilizable. |
| Primera producción | Beat completo y grabación de voz con el audio actual del PC; escuchar la voz después de grabar. |
| Contenido | Kits, instrumentos, presets, loops y ejemplos propios o redistribuibles; prioridad a hip hop, trap y drill. |
| Intercambio | Audio, MIDI y stems; formato propio para proyectos editables. |
| Agentes | Operaciones compartidas entre interfaz, CLI y automatización desde el núcleo. |
| Distribución | Aplicación abierta y gratuita, con licencia permisiva para el código. |
| Entregas | Progresivas; audio y persistencia se validan antes de construir toda la interfaz. |
| Plugins | VST3 y CLAP en una etapa posterior al primer núcleo funcional. |
| Cobertura | Equivalencia por capacidades musicales, sin exigir un sustituto de cada plugin de fábrica. |

La elección de egui se tomó después de comparar Iced y Slint. Es una elección de interfaz, no evidencia de rendimiento ni de accesibilidad de los controles que todavía debemos crear. La primera aproximación de pantallas será un prototipo nativo directo, después de comprobar el núcleo.

## Alcance comprometido

La [matriz de referencia](reference/fl-studio-matrix.md) define el inventario de capacidades. Incluye secuenciación, edición de notas, arreglos, sampling, síntesis, grabación y tomas, edición de audio, mezcla y ruteo, efectos, automatización, MIDI, plugins, biblioteca, render, aprendizaje, agentes y mantenimiento.

Una capacidad figura en el alcance aunque su implementación sea posterior. Las capacidades de análisis avanzado requieren investigación previa de calidad, viabilidad y licencias; su issue no constituye una promesa de una técnica o modelo concretos.

Quedan fuera del alcance acordado abrir o guardar FLP, actuaciones en directo y Performance Mode, y reproducir exactamente el catálogo de plugins propietarios. Exportar stems y separar una mezcla existente en stems son capacidades distintas. La grabación inicial no exige monitorización de voz en vivo; cualquier ampliación deberá medirse aparte.

## Propuestas y aspectos por validar

| Tema | Estado y siguiente comprobación |
|---|---|
| CPAL y WASAPI compartido | Base propuesta de audio Windows; comprobar formatos efectivos, captura, relojes y fallos en el equipo objetivo. |
| Formato portable versionado | Se propone manifiesto separado del modelo de ejecución y recursos asociados; el contrato detallado se valida antes de estabilizarlo. |
| Licencia exacta | MIT/Apache-2.0 es una propuesta; la familia permisiva está acordada, pero aún no se ha elegido ni añadido un archivo LICENSE. |
| Versiones de dependencias | Se fijarán al crear el workspace y comprobar compatibilidad; la documentación de planificación no equivale a un lockfile validado. |
| Latencia, carga y memoria | Se establecerán mediante escenarios reproducibles y mediciones; no se prometen cifras basadas en el lenguaje o el tamaño nominal de búfer. |
| Accesibilidad de editores | Teclado y semántica accesible son requisitos; verificar Piano Roll, secuenciador, mezclador y flujos con controles reales. |

## Criterios de éxito

- Una persona principiante puede completar el recorrido principal con el tutorial, guardar y reabrir el proyecto sin perder contenido ni estado musical.
- Edición, automatización y exportación mantienen el mismo significado musical, también después de deshacer, buscar en la canción o cambiar de dispositivo.
- Un fallo de archivo, disco, dispositivo o plugin produce información accionable y conserva el trabajo recuperable.
- Las capacidades avanzadas tienen resultados, dependencias y evidencia; la presencia de un menú no demuestra que una función esté lista.
- El formato, los parámetros y las operaciones pueden evolucionar sin vincular los datos del usuario a detalles de la interfaz o a handles de ejecución.

## Vocabulario compartido

| Término | Significado en Syntet |
|---|---|
| Instrumento | Fuente sonora controlada por eventos; puede ser sampler, síntesis propia o plugin. |
| Patrón | Contenido musical reutilizable con eventos dirigidos a uno o varios instrumentos. |
| Clip | Instancia de contenido situada en el arreglo, con posición, región y propiedades propias. |
| Pista de arreglo | Organización visual y temporal de clips; no impone un instrumento o canal de mezcla único. |
| Canal de mezcla | Ruta de procesamiento de audio con nivel, efectos y conexiones. |
| Recurso | Archivo o estado necesario para reproducir o editar el proyecto, identificado independientemente de su ruta. |
| Toma | Captura original identificable; puede participar en varios clips y montajes sin perder su fuente. |
| Stem exportado | Audio de una agrupación definida del proyecto, con rango y alineación compatibles con los demás stems. |
| Separación de stems | Estimación de componentes de una mezcla ya existente; distinta de exportar sus pistas originales. |

Las relaciones e invariantes se desarrollan en [arquitectura](architecture.md). La terminología de la interfaz y sus traducciones conservarán estas identidades.

## Evidencia disponible y límites

Se revisaron fuentes públicas de PhotoCraft, VectorCraft, FilmCraft y SoundCraft. Las normas compartidas privadas `craftrules` y los planes locales originales no estuvieron disponibles. SoundCraft es una referencia técnica de audio orientada a Pro Tools; Syntet conserva su modelo propio centrado en patrones.

La instalación local identificada para una futura observación de FL Studio es 26.1.7.5654. Esto identifica una referencia, pero no prueba que se hayan observado o medido sus recorridos. Registrar edición, configuración y fecha en cada sesión de investigación.

Fuentes primarias: [PhotoCraft AGENTS](https://github.com/storytold/photocraft/blob/main/AGENTS.md), [FilmCraft arquitectura](https://github.com/storytold/filmcraft/blob/main/docs/architecture.md), [SoundCraft AGENTS](https://github.com/storytold/soundcraft/blob/main/AGENTS.md), [flujo de FL Studio](https://www.image-line.com/fl-studio-learning-content/fl-studio-online-manual/html/basics_workflow.htm).
