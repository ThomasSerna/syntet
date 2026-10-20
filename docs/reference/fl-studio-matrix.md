# Matriz funcional de Syntet

Inventario aprobado el 2026-10-20: **23 épicas y 157 capacidades**. Cada capacidad tiene una tarea estable; la presencia en esta matriz expresa alcance, no implementación. La aceptación, dependencias operativas y evidencia de cada tarea pertenecen a su issue.

## Cómo leer la matriz

- La referencia funcional inicial es FL Studio 2026; la instalación identificada es 26.1.7.5654. La versión de las páginas públicas puede evolucionar: registrar la revisión al observar un comportamiento.
- Esta entrega revisa documentación pública. No se han ejecutado escenarios de FL Studio ni medido una aplicación Syntet. Las equivalencias finas permanecen por observar según el [método](research-method.md).
- Las áreas de calidad, agentes y mantenimiento son requisitos propios de Syntet inspirados en prácticas públicas de Artcraft; no afirman que sean funciones idénticas de FL Studio.
- E12 y E13 definen familias propias por capacidad, sin reproducir algoritmos, nombres o presets de plugins propietarios. E09 incluye investigación con decisión explícita de viabilidad antes de implementar análisis avanzado.
- El [producto](../product.md) fija límites y el [roadmap](../roadmap.md) define las entregas. La prioridad y preparación actuales se consultan en GitHub.

## E00 · Planificación y referencias

Épica: SYN-E00 · publicación pendiente. Referencia: [Artcraft: guía pública](https://github.com/storytold/photocraft/blob/main/AGENTS.md).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Producto y vocabulario | Un colaborador identifica el usuario, el recorrido principal y los límites acordados sin reconstruir el chat. | SYN-001 · publicación pendiente |
| matriz funcional | Las 23 épicas y cada capacidad aprobada se pueden localizar por identidad y fuente. | SYN-002 · publicación pendiente |
| escenarios de caja negra | La investigación futura dispone de fichas que separan manual, observación e inferencia. | SYN-003 · publicación pendiente |
| arquitectura y ADR | La implementación futura tiene límites de datos, dependencias y responsabilidades verificables. | SYN-004 · publicación pendiente |
| publicación y auditoría del backlog | La planificación queda disponible en el remoto con cobertura completa, enlaces reales y continuidad operativa. | SYN-005 · publicación pendiente |

## E01 · Audio y transporte

Épica: SYN-E01 · publicación pendiente. Referencia: [FL: configuración de audio](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/envsettings_audio.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Configuración de dispositivos | El núcleo abre entrada y salida Windows compatibles y comunica fallos recuperables. | SYN-006 · publicación pendiente |
| procesamiento preparado para tiempo real | El callback procesa bloques sin depender del editor, disco ni trabajo de duración no acotada. | SYN-007 · publicación pendiente |
| scheduling preciso | Notas, samples y cambios de parámetros llegan al render en el instante musical previsto. | SYN-008 · publicación pendiente |
| reproducción, pausa, seek y bucle | El transporte se controla desde comandos y conserva un estado musical definido al saltar o detenerse. | SYN-009 · publicación pendiente |
| tempo, compás y metrónomo | Edición, transporte, grabación y exportación interpretan el mismo tiempo musical. | SYN-010 · publicación pendiente |
| diagnóstico de interrupciones | Una interrupción puede diagnosticarse y el usuario conoce cualquier pérdida de captura o reproducción. | SYN-011 · publicación pendiente |

## E02 · Proyecto e historial

Épica: SYN-E02 · publicación pendiente. Referencia: [FL: archivos y exportación](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/fformats_save_export.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Modelo musical independiente | Patrones, instrumentos, clips y canales de mezcla pueden relacionarse sin dependencias uno-a-uno impuestas. | SYN-012 · publicación pendiente |
| guardado y carga | Un proyecto reabierto conserva su significado musical y el último guardado válido sobrevive a errores. | SYN-013 · publicación pendiente |
| recursos portables | Un proyecto puede abrirse en otra ruta conservando sus recursos y detectando ausencias explícitamente. | SYN-014 · publicación pendiente |
| deshacer por gesto y transacciones | El historial revierte acciones completas preservando identidades y referencias del proyecto. | SYN-015 · publicación pendiente |
| autoguardado y recuperación | Una sesión interrumpida dispone de recuperación verificable sin sobrescribir su último guardado válido. | SYN-016 · publicación pendiente |
| migraciones y archivos incompatibles | La aplicación identifica la versión del proyecto y aplica únicamente migraciones soportadas y verificadas. | SYN-017 · publicación pendiente |

## E03 · Channel Rack y patrones

Épica: SYN-E03 · publicación pendiente. Referencia: [FL: flujo de trabajo](https://www.image-line.com/fl-studio-learning-content/fl-studio-online-manual/html/basics_workflow.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Gestión de canales | El usuario añade, sustituye y organiza instrumentos manteniendo control sobre notas y canales de mezcla. | SYN-018 · publicación pendiente |
| secuencias por pasos | Una persona crea un patrón de batería editable que el transporte reproduce con precisión. | SYN-019 · publicación pendiente |
| propiedades por golpe | Los golpes de un patrón pueden tener expresión individual sin duplicar canales. | SYN-020 · publicación pendiente |
| longitudes y resoluciones variables | Los patrones admiten diferentes duraciones y subdivisiones sin perder o desplazar golpes silenciosamente. | SYN-021 · publicación pendiente |
| swing y desplazamiento | Una batería adquiere groove reproducible sin cambiar arbitrariamente sus notas base. | SYN-022 · publicación pendiente |
| duplicación, división y variantes de patrones | El usuario reutiliza una idea o crea una variación independiente sin editar accidentalmente otras secciones. | SYN-023 · publicación pendiente |

## E04 · Piano Roll y expresión

Épica: SYN-E04 · publicación pendiente. Referencia: [FL: Piano Roll](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/pianoroll_menu.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Edición individual y múltiple | El usuario introduce y modifica frases mediante el mismo modelo musical que reproduce el secuenciador. | SYN-024 · publicación pendiente |
| selección y transformaciones básicas | La edición por bloques permite reorganizar frases conservando su expresión y relaciones temporales. | SYN-025 · publicación pendiente |
| zoom, scroll y snapping | La rejilla y el viewport permiten editar notas con precisión a distintas escalas. | SYN-026 · publicación pendiente |
| carriles de propiedades | Las propiedades de una frase se pueden inspeccionar y editar sin abrir cada nota. | SYN-027 · publicación pendiente |
| notas fantasma y ayudas de escala | El usuario compone con contexto armónico sin confundir referencias visuales con notas editables. | SYN-028 · publicación pendiente |
| legato y deslizamientos | Las frases pueden expresar conexiones y cambios continuos de altura con límites definidos por instrumento. | SYN-029 · publicación pendiente |

## E05 · Herramientas de composición

Épica: SYN-E05 · publicación pendiente. Referencia: [FL: herramientas de Piano Roll](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/pianoroll_menu.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Cuantización y grooves | El usuario corrige o imprime groove conservando control sobre qué parte de una nota cambia. | SYN-030 · publicación pendiente |
| humanización | El usuario obtiene variaciones de timing e intensidad que puede preescuchar, repetir o deshacer. | SYN-031 · publicación pendiente |
| chop y glue | Las herramientas de chop/glue reorganizan la articulación sin perder el contenido no seleccionado. | SYN-032 · publicación pendiente |
| arpegios y repeticiones | La generación musical produce notas normales que el usuario puede continuar editando. | SYN-033 · publicación pendiente |
| strum y flam | El usuario desplaza grupos de notas o añade golpes de adorno con resultados predecibles. | SYN-034 · publicación pendiente |
| inversiones y transformaciones | El usuario explora variantes temporales y melódicas sin depender de generación opaca. | SYN-035 · publicación pendiente |
| acordes y progresiones editables | Un principiante puede construir armonía y después editar cada nota sin servicios externos obligatorios. | SYN-036 · publicación pendiente |

## E06 · Playlist y arreglos

Épica: SYN-E06 · publicación pendiente. Referencia: [FL: Playlist](https://www.image-line.com/fl-studio-learning-content/fl-studio-online-manual/html/playlist.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Clips de patrones, audio y automatización | La Playlist combina contenido musical sin imponer que pista, instrumento y mezclador sean la misma entidad. | SYN-037 · publicación pendiente |
| edición y selección múltiple | El usuario copia, mueve y duplica secciones del arreglo como operaciones coherentes. | SYN-038 · publicación pendiente |
| cortes, trim y slip | La edición del arreglo cambia límites y offsets de clips conservando archivos originales. | SYN-039 · publicación pendiente |
| fades y crossfades | Las entradas, salidas y uniones de audio se editan sin alterar la grabación original. | SYN-040 · publicación pendiente |
| grupos, marcadores y secciones | El usuario reconoce y reorganiza la estructura de la canción sin perder contenido. | SYN-041 · publicación pendiente |
| arreglos alternativos | Una canción puede tener versiones de estructura sin perder recursos ni confundir cambios compartidos. | SYN-042 · publicación pendiente |

## E07 · Sampler y pads

Épica: SYN-E07 · publicación pendiente. Referencia: [FL: sampler](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/chansettings_sampler.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| One-shots y samples afinados | El sampler reproduce batería y material tonal desde fuentes propias o importadas con afinación definida. | SYN-043 · publicación pendiente |
| envolventes y filtros | La duración, dinámica y timbre de una muestra se controlan con parámetros persistentes y automatizables. | SYN-044 · publicación pendiente |
| mono, legato y portamento | El sampler permite bajos y frases conectadas con comportamiento de prioridad de notas definido. | SYN-045 · publicación pendiente |
| grupos de corte | Golpes como hi-hats abiertos y cerrados comparten reglas de corte configurables y persistentes. | SYN-046 · publicación pendiente |
| kits y mapeo de pads | El usuario agrupa sonidos de batería y los dispara mediante pads o notas asignadas. | SYN-047 · publicación pendiente |
| capas de velocidad y round-robin | Los golpes de un pad seleccionan muestras expresivas con límites y secuencia de alternancia reproducibles. | SYN-048 · publicación pendiente |
| instrumentos multisample | Un instrumento combina muestras afinadas por regiones manteniendo portabilidad y consistencia musical. | SYN-049 · publicación pendiente |

## E08 · Editor de audio y slicing

Épica: SYN-E08 · publicación pendiente. Referencia: [FL: editor Edison](https://www.image-line.com/fl-studio-learning-content/fl-studio-online-manual/html/plugins/Edison_3.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Edición con conservación del original | Crear versiones derivadas de una selección de audio con historial reversible. | SYN-050 · publicación pendiente |
| ganancia y normalización | Modificar el nivel de audio derivado con un objetivo explícito y reversible. | SYN-051 · publicación pendiente |
| reverse e inversión | Ofrecer reverse temporal e inversión de polaridad sobre una selección derivada. | SYN-052 · publicación pendiente |
| regiones, bucles y cruces por cero | Crear regiones y puntos de bucle editables manteniendo su posición exacta en la fuente. | SYN-053 · publicación pendiente |
| detección y edición de transitorios | Obtener marcadores de ataques editables para apoyar slicing y corrección temporal. | SYN-054 · publicación pendiente |
| conversión de slices a pads, clips o notas | Distribuir slices entre pads, clips o notas manteniendo el vínculo con la fuente. | SYN-055 · publicación pendiente |

## E09 · Tiempo, tono y análisis

Épica: SYN-E09 · publicación pendiente. Referencia: [FL: NewTone](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/plugins/Newtone.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Detección corregible de tempo y tonalidad | Proponer tempo y tonalidad de una fuente, conservando incertidumbre y elección del usuario. | SYN-056 · publicación pendiente |
| estiramiento temporal | Adaptar la duración de una fuente con un modo temporal explícito y una ruta reversible. | SYN-057 · publicación pendiente |
| cambio independiente de afinación | Transponer audio independientemente de su duración con original y parámetros recuperables. | SYN-058 · publicación pendiente |
| warp y cuantización de audio | Alinear ataques con una rejilla musical manteniendo marcadores y audio fuente recuperables. | SYN-059 · publicación pendiente |
| edición de afinación vocal | Permitir detectar y ajustar segmentos monofónicos de voz con límites de calidad explícitos. | SYN-060 · publicación pendiente |
| audio monofónico a MIDI | Crear notas con altura, inicio, fin y velocidad aproximada desde una fuente monofónica. | SYN-061 · publicación pendiente |
| investigación de separación de stems y limpieza avanzada | Decidir con evidencia si incorporar separación de fuentes y limpieza avanzada al producto. | SYN-062 · publicación pendiente |

## E10 · Grabación y tomas

Épica: SYN-E10 · publicación pendiente. Referencia: [FL: grabación de audio](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/recording_audio.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Armado y entradas mono/estéreo | Preparar una toma eligiendo pista, dispositivo y canal o pareja de canales. | SYN-063 · publicación pendiente |
| captura a disco | Escribir tomas recuperables a disco con memoria acotada y duración verificable. | SYN-064 · publicación pendiente |
| alineación y deriva | Relacionar la captura con el transporte sin asumir que ambos dispositivos comparten reloj. | SYN-065 · publicación pendiente |
| cuenta de entrada y punch | Iniciar y limitar una toma respecto del transporte sin recortar eventos incorrectamente. | SYN-066 · publicación pendiente |
| grabación en bucle | Grabar pasadas repetidas sin mezclar, sobrescribir o perder las anteriores. | SYN-067 · publicación pendiente |
| conservación y combinación de tomas | Construir una interpretación compuesta eligiendo segmentos de varias tomas. | SYN-068 · publicación pendiente |
| recuperación de grabaciones interrumpidas | Preservar y presentar la parte recuperable de una toma que no llegó a finalizar. | SYN-069 · publicación pendiente |

## E11 · Mezcla y ruteo

Épica: SYN-E11 · publicación pendiente. Referencia: [FL: mezclador](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/mixer.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Faders, pan, mute y solo | Mezclar canales con controles persistibles y semántica de solo documentada. | SYN-070 · publicación pendiente |
| cadenas de inserts | Construir cadenas de procesamiento por canal con bypass y orden explícitos. | SYN-071 · publicación pendiente |
| buses y envíos | Enviar audio a submezclas y procesamientos compartidos de forma trazable. | SYN-072 · publicación pendiente |
| sidechains | Usar otro canal como detector o entrada auxiliar de un procesador. | SYN-073 · publicación pendiente |
| múltiples entradas y salidas | Representar buses y canales de audio sin asumir siempre un par estéreo. | SYN-074 · publicación pendiente |
| visualización y validación del ruteo | Hacer inspeccionable el grafo y evitar conexiones que no puedan ejecutarse con seguridad. | SYN-075 · publicación pendiente |
| compensación de latencia | Compensar latencia declarada o manual en rutas paralelas, auxiliares y exportación. | SYN-076 · publicación pendiente |

## E12 · Instrumentos internos

Épica: SYN-E12 · publicación pendiente. Referencia: [FL: flujo de instrumentos](https://www.image-line.com/fl-studio-learning-content/fl-studio-online-manual/html/basics_workflow.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Síntesis sustractiva | Proporcionar osciladores, filtro y envolventes para melodías y bajos propios. | SYN-077 · publicación pendiente |
| percusión sintetizada | Generar percusión útil para beats sin depender de muestras propietarias. | SYN-078 · publicación pendiente |
| bajos 808 expresivos | Ofrecer bajos largos afinados adecuados para trap/drill y frases con deslizamientos. | SYN-079 · publicación pendiente |
| síntesis FM | Ampliar diseño sonoro mediante modulación de frecuencia con algoritmos documentados. | SYN-080 · publicación pendiente |
| wavetable | Usar tablas de onda propias y variar su posición durante una nota. | SYN-081 · publicación pendiente |
| modulación y gestión de voces | Controlar polifonía, robo de voces y moduladores sin asignar memoria en reproducción. | SYN-082 · publicación pendiente |
| presets propios | Reutilizar un sonido con identidad y parámetros versionados independientes de la UI. | SYN-083 · publicación pendiente |

## E13 · Efectos y medición

Épica: SYN-E13 · publicación pendiente. Referencia: [FL: procesamiento en mezcla](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/mixer.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| EQ y filtros | Dar control tonal de mezcla con parámetros estables y representación de respuesta. | SYN-084 · publicación pendiente |
| compresión, limitación y puerta | Ofrecer dinámica básica con detectores y envolventes verificables. | SYN-085 · publicación pendiente |
| delay | Crear repeticiones con tiempo libre o musical, feedback y mezcla persistibles. | SYN-086 · publicación pendiente |
| reverberación | Añadir espacio a la mezcla con comportamiento estable y cola exportable. | SYN-087 · publicación pendiente |
| chorus, flanger y phaser | Ofrecer chorus, flanger y phaser con comportamiento y estado propios. | SYN-088 · publicación pendiente |
| saturación y waveshaping | Diseñar distorsión con curvas propias, ganancia y calidad documentadas. | SYN-089 · publicación pendiente |
| medición de picos, loudness, espectro y estéreo | Mostrar picos, loudness, espectro y relación estéreo de manera interpretable. | SYN-090 · publicación pendiente |

## E14 · Automatización y modulación

Épica: SYN-E14 · publicación pendiente. Referencia: [FL: eventos de automatización](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/automation_eventeditor.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Parámetros con identidad estable | Identificar y describir parámetros de instrumentos, efectos y mezcla para guardar y automatizar. | SYN-091 · publicación pendiente |
| clips y curvas | Crear clips que controlen parámetros mediante segmentos temporales editables. | SYN-092 · publicación pendiente |
| grabación de movimientos | Capturar cambios de parámetros respecto del transporte para reproducirlos y editarlos. | SYN-093 · publicación pendiente |
| eventos dentro de patrones | Vincular cambios de controles a patrones reutilizables sin confundirlos con clips del arreglo. | SYN-094 · publicación pendiente |
| conversión entre eventos y clips | Trasladar una trayectoria entre eventos y clips declarando cualquier simplificación. | SYN-095 · publicación pendiente |
| macros, LFO y seguidores | Crear conexiones explícitas entre un controlador y destinos con rangos propios. | SYN-096 · publicación pendiente |
| comportamiento al iniciar, buscar y superponer automatizaciones | Hacer determinista el valor de un parámetro al iniciar, buscar, repetir o combinar fuentes de control. | SYN-097 · publicación pendiente |

## E15 · MIDI y controladores

Épica: SYN-E15 · publicación pendiente. Referencia: [FL: MIDI](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/envsettings_midi.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Dispositivos y ruteo | Seleccionar entradas/salidas MIDI y rutearlas sin mezclar identidades de puertos. | SYN-098 · publicación pendiente |
| notas, CC y expresión | Convertir eventos MIDI admitidos a eventos del motor sin perder canal ni orden temporal. | SYN-099 · publicación pendiente |
| grabación y overdub | Capturar interpretación MIDI en patrones con cuantización opcional y posibilidad de deshacer. | SYN-100 · publicación pendiente |
| entrada por pasos | Componer sin interpretación en tiempo real mediante eventos de un controlador. | SYN-101 · publicación pendiente |
| MIDI learn y mapas | Relacionar controles físicos con parámetros estables y curvas seleccionables. | SYN-102 · publicación pendiente |
| importación MIDI | Convertir pistas, canales, notas y tempo de archivos MIDI a entidades editables. | SYN-103 · publicación pendiente |
| salida y sincronización con hardware de estudio | Controlar instrumentos externos desde el transporte de estudio con latencia explícita. | SYN-104 · publicación pendiente |

## E16 · VST3 y CLAP

Épica: SYN-E16 · publicación pendiente. Referencia: [FL: alojamiento de plugins](https://www.image-line.com/fl-studio-learning-content/fl-studio-online-manual/html/plugins/wrapper.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Escaneo aislado y caché | Descubrir instrumentos y efectos externos sin que un escaneo fallido termine la sesión del usuario. | SYN-105 · publicación pendiente |
| alojamiento VST3 | Utilizar plugins VST3 como instrumentos o inserts de una sesión musical. | SYN-106 · publicación pendiente |
| alojamiento CLAP | Utilizar plugins CLAP sin introducir sus handles o extensiones en el modelo persistente. | SYN-107 · publicación pendiente |
| editores nativos | Editar plugins alojados desde sus interfaces de Windows dentro del flujo de Syntet. | SYN-108 · publicación pendiente |
| eventos, parámetros y buses | Conectar plugins al tiempo, eventos y ruteo del proyecto con correspondencias estables. | SYN-109 · publicación pendiente |
| persistencia del estado | Reabrir una sesión conserva los sonidos y ajustes que el usuario creó con plugins. | SYN-110 · publicación pendiente |
| recuperación de plugins ausentes o fallidos | Un plugin no disponible no impide recuperar y editar el resto del proyecto. | SYN-111 · publicación pendiente |
| evaluación del aislamiento durante procesamiento | Resolver si la ejecución de plugins requiere un proceso separado y qué garantías puede ofrecer el host. | SYN-112 · publicación pendiente |

## E17 · Biblioteca y contenido

Épica: SYN-E17 · publicación pendiente. Referencia: [FL: navegador](https://www.image-line.com/fl-studio-learning-content/fl-studio-online-manual/html/browser.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Indexación y búsqueda | Localizar sonidos, presets y proyectos por texto y tipo de recurso. | SYN-113 · publicación pendiente |
| tags y favoritos | Crear colecciones personales que faciliten volver a encontrar sonidos. | SYN-114 · publicación pendiente |
| preescucha | Evaluar samples y loops antes de incorporarlos al beat. | SYN-115 · publicación pendiente |
| banco inicial redistribuible | Crear un primer beat sin instalar bancos propietarios ni descargar contenido obligatorio. | SYN-116 · publicación pendiente |
| presets de instrumentos, kits, patrones y efectos | Reutilizar configuraciones de sonido, batería, patrones y cadenas de mezcla entre proyectos. | SYN-117 · publicación pendiente |
| recursos usados por proyecto | Entender la dependencia de samples, grabaciones y recursos externos antes de trasladar una sesión. | SYN-118 · publicación pendiente |
| localización y sustitución de archivos ausentes | Reabrir y reparar proyectos trasladados o con archivos retirados. | SYN-119 · publicación pendiente |

## E18 · Render e intercambio

Épica: SYN-E18 · publicación pendiente. Referencia: [FL: render y exportación](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/fformats_save_export.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| WAV de canción, patrón y selección | Obtener audio de un proyecto con el mismo procesamiento musical utilizado en reproducción. | SYN-120 · publicación pendiente |
| profundidad y frecuencia de muestras | Exportar archivos adecuados para intercambio conservando duración y tratamiento explícito de cuantización. | SYN-121 · publicación pendiente |
| colas de efectos | Evitar cortar o prolongar indefinidamente reverberaciones y delays al exportar. | SYN-122 · publicación pendiente |
| stems alineados | Intercambiar una producción como archivos separados que puedan alinearse en otra estación. | SYN-123 · publicación pendiente |
| exportación MIDI | Llevar composición MIDI de Syntet a otras herramientas sin confundir propiedades internas con eventos estándar. | SYN-124 · publicación pendiente |
| consolidación y congelación reversible | Reducir carga o preparar material de audio sin perder instrumentos, notas ni procesamiento originales. | SYN-125 · publicación pendiente |
| exportación en segundo plano y formatos adicionales | Continuar trabajando mientras se exporta con control de progreso y formatos adicionales autorizados. | SYN-126 · publicación pendiente |

## E19 · Interfaz y aprendizaje

Épica: SYN-E19 · publicación pendiente. Referencia: [egui: interacción y accesibilidad](https://docs.rs/egui_kittest/latest/egui_kittest/).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Espacio de trabajo y paneles | Acceder a patrones, Piano Roll, arreglo, mezcla y biblioteca sin perder la selección musical. | SYN-127 · publicación pendiente |
| atajos configurables | Editar con rapidez usando un mapa de teclado propio y recuperable. | SYN-128 · publicación pendiente |
| teclado y accesibilidad | Realizar el flujo musical principal sin depender exclusivamente del puntero o de señales visuales. | SYN-129 · publicación pendiente |
| DPI y contraste | Producir con tamaños de pantalla y escalas diferentes sin controles inaccesibles o estados ambiguos. | SYN-130 · publicación pendiente |
| español e inglés | Aprender y trabajar en cualquiera de los dos idiomas sin cambiar identidades del proyecto o de comandos. | SYN-131 · publicación pendiente |
| ayuda contextual | Entender qué hace una operación y cómo continuar cuando no puede realizarse. | SYN-132 · publicación pendiente |
| tutorial del primer tema | Una persona principiante termina una producción sin depender de un tutorial externo. | SYN-133 · publicación pendiente |
| plantillas y demostraciones propias | Aprender de proyectos completos de hip hop, trap y drill que puedan modificarse y redistribuirse. | SYN-134 · publicación pendiente |

## E20 · CLI, automatización y agentes

Épica: SYN-E20 · publicación pendiente. Referencia: [SoundCraft: control por comandos](https://github.com/storytold/soundcraft/blob/main/AGENTS.md).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Operaciones tipadas | Concentrar validación y cambios musicales en un único límite de comandos independiente de la UI. | SYN-135 · publicación pendiente |
| descubrimiento de comandos y parámetros | Permitir que interfaz y agentes conozcan qué operaciones existen y cómo invocarlas. | SYN-136 · publicación pendiente |
| CLI sin ventana | Reproducir operaciones del núcleo de forma automatizable sin una ventana o GPU obligatoria. | SYN-137 · publicación pendiente |
| inspección y render por lotes | Verificar fixtures y exportar varios proyectos de forma reproducible sin intervención de interfaz. | SYN-138 · publicación pendiente |
| protocolo local autenticado | Permitir automatización de la instancia activa conservando control explícito del usuario. | SYN-139 · publicación pendiente |
| MCP | Un agente puede descubrir y utilizar las operaciones musicales autorizadas sin otra implementación del motor. | SYN-140 · publicación pendiente |
| errores comunes y protección frente a ediciones sobre un estado desactualizado | La automatización y la edición interactiva no sobrescriben cambios recientes sin detectarlo. | SYN-141 · publicación pendiente |

## E21 · Calidad y rendimiento

Épica: SYN-E21 · publicación pendiente. Referencia: [FilmCraft: pruebas](https://github.com/storytold/filmcraft/blob/main/docs/testing.md).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Fixtures musicales y corpus | Evaluar cambios sobre entradas pequeñas, reproducibles y redistribuibles. | SYN-142 · publicación pendiente |
| pruebas DSP | Detectar errores de señal que no se descubren comprobando que un bloque produce audio. | SYN-143 · publicación pendiente |
| precisión temporal | Las notas y cambios temporales se ejecutan una sola vez en su posición prevista. | SYN-144 · publicación pendiente |
| equivalencia entre reproducción y render | Una exportación representa la producción escuchada en vez de un motor alternativo con comportamiento distinto. | SYN-145 · publicación pendiente |
| límites de CPU y memoria | Conocer la capacidad real del producto y la degradación ante presión de recursos. | SYN-146 · publicación pendiente |
| captura prolongada | Demostrar que el diseño de captura sostiene tomas útiles en el equipo objetivo. | SYN-147 · publicación pendiente |
| fallos de disco y dispositivos | Probar que los mecanismos de recuperación funcionan ante fallos reales del límite de entrada/salida. | SYN-148 · publicación pendiente |
| regresiones de interfaz y accesibilidad | Detectar cambios que rompan interacción y comprensión aunque el núcleo siga calculando correctamente. | SYN-149 · publicación pendiente |

## E22 · Mantenimiento y distribución

Épica: SYN-E22 · publicación pendiente. Referencia: [PhotoCraft: capas y mantenimiento](https://github.com/storytold/photocraft/blob/main/AGENTS.md).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Comprobación de capas | Mantener dominio, audio e interfaces separados al crecer el proyecto. | SYN-150 · publicación pendiente |
| CI y lockfile | Detectar regresiones del núcleo en cada cambio integrado. | SYN-151 · publicación pendiente |
| política de actualizaciones | Evitar que futuras actualizaciones introduzcan cambios de comportamiento o licencias inadvertidos. | SYN-152 · publicación pendiente |
| compatibilidad de datos y API | Actualizar Syntet sin cambiar silenciosamente el significado de proyectos o integraciones. | SYN-153 · publicación pendiente |
| empaquetado Windows | Utilizar la aplicación en un equipo limpio sin depender del entorno de desarrollo. | SYN-154 · publicación pendiente |
| versiones y notas de publicación | Saber qué se entrega, de qué commit proviene y qué datos/integraciones admite. | SYN-155 · publicación pendiente |
| diagnóstico reproducible | Investigar problemas de audio, recursos y compatibilidad sin compartir datos privados por defecto. | SYN-156 · publicación pendiente |
| preparación de futuros puertos | Preparar Linux y macOS sin confundir diseño portable con soporte de producto entregado. | SYN-157 · publicación pendiente |

## Cobertura y cambios

La matriz conserva las capacidades de la planificación aprobada, incluidas las de largo plazo. Incorporar o retirar una capacidad requiere actualizar producto cuando afecte alcance, añadir o modificar su issue y corregir este índice en la misma entrega. Los IDs no se reutilizan ni renumeran.

Exportar stems no equivale a separar una mezcla; edición de notas no equivale a herramientas creativas; grabar una toma no equivale a gestionar tomas. Performance Mode, actuaciones en directo, FLP y equivalentes individuales del catálogo propietario siguen fuera del alcance.

La auditoría de publicación está en [el informe](publication-audit.md); sus resultados son una fotografía fechada, no el estado operativo de las capacidades.
