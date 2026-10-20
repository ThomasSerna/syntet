# Matriz funcional de Syntet

Inventario aprobado el 2026-10-20: **23 épicas y 157 capacidades**. Cada capacidad tiene una tarea estable; la presencia en esta matriz expresa alcance, no implementación. La aceptación, dependencias operativas y evidencia de cada tarea pertenecen a su issue.

## Cómo leer la matriz

- La referencia funcional inicial es FL Studio 2026; la instalación identificada es 26.1.7.5654. La versión de las páginas públicas puede evolucionar: registrar la revisión al observar un comportamiento.
- Esta entrega revisa documentación pública. No se han ejecutado escenarios de FL Studio ni medido una aplicación Syntet. Las equivalencias finas permanecen por observar según el [método](research-method.md).
- Las áreas de calidad, agentes y mantenimiento son requisitos propios de Syntet inspirados en prácticas públicas de Artcraft; no afirman que sean funciones idénticas de FL Studio.
- E12 y E13 definen familias propias por capacidad, sin reproducir algoritmos, nombres o presets de plugins propietarios. E09 incluye investigación con decisión explícita de viabilidad antes de implementar análisis avanzado.
- El [producto](../product.md) fija límites y el [roadmap](../roadmap.md) define las entregas. La prioridad y preparación actuales se consultan en GitHub.

## E00 · Planificación y referencias

Épica: [SYN-E00 · #1](https://github.com/ThomasSerna/syntet/issues/1). Referencia: [Artcraft: guía pública](https://github.com/storytold/photocraft/blob/main/AGENTS.md).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Producto y vocabulario | Un colaborador identifica el usuario, el recorrido principal y los límites acordados sin reconstruir el chat. | [SYN-001 · #24](https://github.com/ThomasSerna/syntet/issues/24) |
| matriz funcional | Las 23 épicas y cada capacidad aprobada se pueden localizar por identidad y fuente. | [SYN-002 · #25](https://github.com/ThomasSerna/syntet/issues/25) |
| escenarios de caja negra | La investigación futura dispone de fichas que separan manual, observación e inferencia. | [SYN-003 · #26](https://github.com/ThomasSerna/syntet/issues/26) |
| arquitectura y ADR | La implementación futura tiene límites de datos, dependencias y responsabilidades verificables. | [SYN-004 · #27](https://github.com/ThomasSerna/syntet/issues/27) |
| publicación y auditoría del backlog | La planificación queda disponible en el remoto con cobertura completa, enlaces reales y continuidad operativa. | [SYN-005 · #28](https://github.com/ThomasSerna/syntet/issues/28) |

## E01 · Audio y transporte

Épica: [SYN-E01 · #2](https://github.com/ThomasSerna/syntet/issues/2). Referencia: [FL: configuración de audio](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/envsettings_audio.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Configuración de dispositivos | El núcleo abre entrada y salida Windows compatibles y comunica fallos recuperables. | [SYN-006 · #29](https://github.com/ThomasSerna/syntet/issues/29) |
| procesamiento preparado para tiempo real | El callback procesa bloques sin depender del editor, disco ni trabajo de duración no acotada. | [SYN-007 · #30](https://github.com/ThomasSerna/syntet/issues/30) |
| scheduling preciso | Notas, samples y cambios de parámetros llegan al render en el instante musical previsto. | [SYN-008 · #33](https://github.com/ThomasSerna/syntet/issues/33) |
| reproducción, pausa, seek y bucle | El transporte se controla desde comandos y conserva un estado musical definido al saltar o detenerse. | [SYN-009 · #35](https://github.com/ThomasSerna/syntet/issues/35) |
| tempo, compás y metrónomo | Edición, transporte, grabación y exportación interpretan el mismo tiempo musical. | [SYN-010 · #32](https://github.com/ThomasSerna/syntet/issues/32) |
| diagnóstico de interrupciones | Una interrupción puede diagnosticarse y el usuario conoce cualquier pérdida de captura o reproducción. | [SYN-011 · #36](https://github.com/ThomasSerna/syntet/issues/36) |

## E02 · Proyecto e historial

Épica: [SYN-E02 · #3](https://github.com/ThomasSerna/syntet/issues/3). Referencia: [FL: archivos y exportación](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/fformats_save_export.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Modelo musical independiente | Patrones, instrumentos, clips y canales de mezcla pueden relacionarse sin dependencias uno-a-uno impuestas. | [SYN-012 · #31](https://github.com/ThomasSerna/syntet/issues/31) |
| guardado y carga | Un proyecto reabierto conserva su significado musical y el último guardado válido sobrevive a errores. | [SYN-013 · #37](https://github.com/ThomasSerna/syntet/issues/37) |
| recursos portables | Un proyecto puede abrirse en otra ruta conservando sus recursos y detectando ausencias explícitamente. | [SYN-014 · #38](https://github.com/ThomasSerna/syntet/issues/38) |
| deshacer por gesto y transacciones | El historial revierte acciones completas preservando identidades y referencias del proyecto. | [SYN-015 · #39](https://github.com/ThomasSerna/syntet/issues/39) |
| autoguardado y recuperación | Una sesión interrumpida dispone de recuperación verificable sin sobrescribir su último guardado válido. | [SYN-016 · #40](https://github.com/ThomasSerna/syntet/issues/40) |
| migraciones y archivos incompatibles | La aplicación identifica la versión del proyecto y aplica únicamente migraciones soportadas y verificadas. | [SYN-017 · #41](https://github.com/ThomasSerna/syntet/issues/41) |

## E03 · Channel Rack y patrones

Épica: [SYN-E03 · #4](https://github.com/ThomasSerna/syntet/issues/4). Referencia: [FL: flujo de trabajo](https://www.image-line.com/fl-studio-learning-content/fl-studio-online-manual/html/basics_workflow.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Gestión de canales | El usuario añade, sustituye y organiza instrumentos manteniendo control sobre notas y canales de mezcla. | [SYN-018 · #42](https://github.com/ThomasSerna/syntet/issues/42) |
| secuencias por pasos | Una persona crea un patrón de batería editable que el transporte reproduce con precisión. | [SYN-019 · #43](https://github.com/ThomasSerna/syntet/issues/43) |
| propiedades por golpe | Los golpes de un patrón pueden tener expresión individual sin duplicar canales. | [SYN-020 · #45](https://github.com/ThomasSerna/syntet/issues/45) |
| longitudes y resoluciones variables | Los patrones admiten diferentes duraciones y subdivisiones sin perder o desplazar golpes silenciosamente. | [SYN-021 · #46](https://github.com/ThomasSerna/syntet/issues/46) |
| swing y desplazamiento | Una batería adquiere groove reproducible sin cambiar arbitrariamente sus notas base. | [SYN-022 · #47](https://github.com/ThomasSerna/syntet/issues/47) |
| duplicación, división y variantes de patrones | El usuario reutiliza una idea o crea una variación independiente sin editar accidentalmente otras secciones. | [SYN-023 · #48](https://github.com/ThomasSerna/syntet/issues/48) |

## E04 · Piano Roll y expresión

Épica: [SYN-E04 · #5](https://github.com/ThomasSerna/syntet/issues/5). Referencia: [FL: Piano Roll](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/pianoroll_menu.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Edición individual y múltiple | El usuario introduce y modifica frases mediante el mismo modelo musical que reproduce el secuenciador. | [SYN-024 · #49](https://github.com/ThomasSerna/syntet/issues/49) |
| selección y transformaciones básicas | La edición por bloques permite reorganizar frases conservando su expresión y relaciones temporales. | [SYN-025 · #50](https://github.com/ThomasSerna/syntet/issues/50) |
| zoom, scroll y snapping | La rejilla y el viewport permiten editar notas con precisión a distintas escalas. | [SYN-026 · #51](https://github.com/ThomasSerna/syntet/issues/51) |
| carriles de propiedades | Las propiedades de una frase se pueden inspeccionar y editar sin abrir cada nota. | [SYN-027 · #52](https://github.com/ThomasSerna/syntet/issues/52) |
| notas fantasma y ayudas de escala | El usuario compone con contexto armónico sin confundir referencias visuales con notas editables. | [SYN-028 · #53](https://github.com/ThomasSerna/syntet/issues/53) |
| legato y deslizamientos | Las frases pueden expresar conexiones y cambios continuos de altura con límites definidos por instrumento. | [SYN-029 · #56](https://github.com/ThomasSerna/syntet/issues/56) |

## E05 · Herramientas de composición

Épica: [SYN-E05 · #6](https://github.com/ThomasSerna/syntet/issues/6). Referencia: [FL: herramientas de Piano Roll](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/pianoroll_menu.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Cuantización y grooves | El usuario corrige o imprime groove conservando control sobre qué parte de una nota cambia. | [SYN-030 · #57](https://github.com/ThomasSerna/syntet/issues/57) |
| humanización | El usuario obtiene variaciones de timing e intensidad que puede preescuchar, repetir o deshacer. | [SYN-031 · #58](https://github.com/ThomasSerna/syntet/issues/58) |
| chop y glue | Las herramientas de chop/glue reorganizan la articulación sin perder el contenido no seleccionado. | [SYN-032 · #59](https://github.com/ThomasSerna/syntet/issues/59) |
| arpegios y repeticiones | La generación musical produce notas normales que el usuario puede continuar editando. | [SYN-033 · #60](https://github.com/ThomasSerna/syntet/issues/60) |
| strum y flam | El usuario desplaza grupos de notas o añade golpes de adorno con resultados predecibles. | [SYN-034 · #61](https://github.com/ThomasSerna/syntet/issues/61) |
| inversiones y transformaciones | El usuario explora variantes temporales y melódicas sin depender de generación opaca. | [SYN-035 · #62](https://github.com/ThomasSerna/syntet/issues/62) |
| acordes y progresiones editables | Un principiante puede construir armonía y después editar cada nota sin servicios externos obligatorios. | [SYN-036 · #63](https://github.com/ThomasSerna/syntet/issues/63) |

## E06 · Playlist y arreglos

Épica: [SYN-E06 · #7](https://github.com/ThomasSerna/syntet/issues/7). Referencia: [FL: Playlist](https://www.image-line.com/fl-studio-learning-content/fl-studio-online-manual/html/playlist.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Clips de patrones, audio y automatización | La Playlist combina contenido musical sin imponer que pista, instrumento y mezclador sean la misma entidad. | [SYN-037 · #66](https://github.com/ThomasSerna/syntet/issues/66) |
| edición y selección múltiple | El usuario copia, mueve y duplica secciones del arreglo como operaciones coherentes. | [SYN-038 · #67](https://github.com/ThomasSerna/syntet/issues/67) |
| cortes, trim y slip | La edición del arreglo cambia límites y offsets de clips conservando archivos originales. | [SYN-039 · #68](https://github.com/ThomasSerna/syntet/issues/68) |
| fades y crossfades | Las entradas, salidas y uniones de audio se editan sin alterar la grabación original. | [SYN-040 · #69](https://github.com/ThomasSerna/syntet/issues/69) |
| grupos, marcadores y secciones | El usuario reconoce y reorganiza la estructura de la canción sin perder contenido. | [SYN-041 · #70](https://github.com/ThomasSerna/syntet/issues/70) |
| arreglos alternativos | Una canción puede tener versiones de estructura sin perder recursos ni confundir cambios compartidos. | [SYN-042 · #71](https://github.com/ThomasSerna/syntet/issues/71) |

## E07 · Sampler y pads

Épica: [SYN-E07 · #8](https://github.com/ThomasSerna/syntet/issues/8). Referencia: [FL: sampler](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/chansettings_sampler.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| One-shots y samples afinados | El sampler reproduce batería y material tonal desde fuentes propias o importadas con afinación definida. | [SYN-043 · #54](https://github.com/ThomasSerna/syntet/issues/54) |
| envolventes y filtros | La duración, dinámica y timbre de una muestra se controlan con parámetros persistentes y automatizables. | [SYN-044 · #72](https://github.com/ThomasSerna/syntet/issues/72) |
| mono, legato y portamento | El sampler permite bajos y frases conectadas con comportamiento de prioridad de notas definido. | [SYN-045 · #55](https://github.com/ThomasSerna/syntet/issues/55) |
| grupos de corte | Golpes como hi-hats abiertos y cerrados comparten reglas de corte configurables y persistentes. | [SYN-046 · #73](https://github.com/ThomasSerna/syntet/issues/73) |
| kits y mapeo de pads | El usuario agrupa sonidos de batería y los dispara mediante pads o notas asignadas. | [SYN-047 · #74](https://github.com/ThomasSerna/syntet/issues/74) |
| capas de velocidad y round-robin | Los golpes de un pad seleccionan muestras expresivas con límites y secuencia de alternancia reproducibles. | [SYN-048 · #75](https://github.com/ThomasSerna/syntet/issues/75) |
| instrumentos multisample | Un instrumento combina muestras afinadas por regiones manteniendo portabilidad y consistencia musical. | [SYN-049 · #76](https://github.com/ThomasSerna/syntet/issues/76) |

## E08 · Editor de audio y slicing

Épica: [SYN-E08 · #9](https://github.com/ThomasSerna/syntet/issues/9). Referencia: [FL: editor Edison](https://www.image-line.com/fl-studio-learning-content/fl-studio-online-manual/html/plugins/Edison_3.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Edición con conservación del original | Crear versiones derivadas de una selección de audio con historial reversible. | [SYN-050 · #77](https://github.com/ThomasSerna/syntet/issues/77) |
| ganancia y normalización | Modificar el nivel de audio derivado con un objetivo explícito y reversible. | [SYN-051 · #78](https://github.com/ThomasSerna/syntet/issues/78) |
| reverse e inversión | Ofrecer reverse temporal e inversión de polaridad sobre una selección derivada. | [SYN-052 · #79](https://github.com/ThomasSerna/syntet/issues/79) |
| regiones, bucles y cruces por cero | Crear regiones y puntos de bucle editables manteniendo su posición exacta en la fuente. | [SYN-053 · #80](https://github.com/ThomasSerna/syntet/issues/80) |
| detección y edición de transitorios | Obtener marcadores de ataques editables para apoyar slicing y corrección temporal. | [SYN-054 · #81](https://github.com/ThomasSerna/syntet/issues/81) |
| conversión de slices a pads, clips o notas | Distribuir slices entre pads, clips o notas manteniendo el vínculo con la fuente. | [SYN-055 · #82](https://github.com/ThomasSerna/syntet/issues/82) |

## E09 · Tiempo, tono y análisis

Épica: [SYN-E09 · #10](https://github.com/ThomasSerna/syntet/issues/10). Referencia: [FL: NewTone](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/plugins/Newtone.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Detección corregible de tempo y tonalidad | Proponer tempo y tonalidad de una fuente, conservando incertidumbre y elección del usuario. | [SYN-056 · #83](https://github.com/ThomasSerna/syntet/issues/83) |
| estiramiento temporal | Adaptar la duración de una fuente con un modo temporal explícito y una ruta reversible. | [SYN-057 · #84](https://github.com/ThomasSerna/syntet/issues/84) |
| cambio independiente de afinación | Transponer audio independientemente de su duración con original y parámetros recuperables. | [SYN-058 · #85](https://github.com/ThomasSerna/syntet/issues/85) |
| warp y cuantización de audio | Alinear ataques con una rejilla musical manteniendo marcadores y audio fuente recuperables. | [SYN-059 · #86](https://github.com/ThomasSerna/syntet/issues/86) |
| edición de afinación vocal | Permitir detectar y ajustar segmentos monofónicos de voz con límites de calidad explícitos. | [SYN-060 · #88](https://github.com/ThomasSerna/syntet/issues/88) |
| audio monofónico a MIDI | Crear notas con altura, inicio, fin y velocidad aproximada desde una fuente monofónica. | [SYN-061 · #89](https://github.com/ThomasSerna/syntet/issues/89) |
| investigación de separación de stems y limpieza avanzada | Decidir con evidencia si incorporar separación de fuentes y limpieza avanzada al producto. | [SYN-062 · #90](https://github.com/ThomasSerna/syntet/issues/90) |

## E10 · Grabación y tomas

Épica: [SYN-E10 · #11](https://github.com/ThomasSerna/syntet/issues/11). Referencia: [FL: grabación de audio](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/recording_audio.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Armado y entradas mono/estéreo | Preparar una toma eligiendo pista, dispositivo y canal o pareja de canales. | [SYN-063 · #91](https://github.com/ThomasSerna/syntet/issues/91) |
| captura a disco | Escribir tomas recuperables a disco con memoria acotada y duración verificable. | [SYN-064 · #87](https://github.com/ThomasSerna/syntet/issues/87) |
| alineación y deriva | Relacionar la captura con el transporte sin asumir que ambos dispositivos comparten reloj. | [SYN-065 · #92](https://github.com/ThomasSerna/syntet/issues/92) |
| cuenta de entrada y punch | Iniciar y limitar una toma respecto del transporte sin recortar eventos incorrectamente. | [SYN-066 · #93](https://github.com/ThomasSerna/syntet/issues/93) |
| grabación en bucle | Grabar pasadas repetidas sin mezclar, sobrescribir o perder las anteriores. | [SYN-067 · #94](https://github.com/ThomasSerna/syntet/issues/94) |
| conservación y combinación de tomas | Construir una interpretación compuesta eligiendo segmentos de varias tomas. | [SYN-068 · #95](https://github.com/ThomasSerna/syntet/issues/95) |
| recuperación de grabaciones interrumpidas | Preservar y presentar la parte recuperable de una toma que no llegó a finalizar. | [SYN-069 · #96](https://github.com/ThomasSerna/syntet/issues/96) |

## E11 · Mezcla y ruteo

Épica: [SYN-E11 · #12](https://github.com/ThomasSerna/syntet/issues/12). Referencia: [FL: mezclador](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/mixer.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Faders, pan, mute y solo | Mezclar canales con controles persistibles y semántica de solo documentada. | [SYN-070 · #97](https://github.com/ThomasSerna/syntet/issues/97) |
| cadenas de inserts | Construir cadenas de procesamiento por canal con bypass y orden explícitos. | [SYN-071 · #98](https://github.com/ThomasSerna/syntet/issues/98) |
| buses y envíos | Enviar audio a submezclas y procesamientos compartidos de forma trazable. | [SYN-072 · #99](https://github.com/ThomasSerna/syntet/issues/99) |
| sidechains | Usar otro canal como detector o entrada auxiliar de un procesador. | [SYN-073 · #100](https://github.com/ThomasSerna/syntet/issues/100) |
| múltiples entradas y salidas | Representar buses y canales de audio sin asumir siempre un par estéreo. | [SYN-074 · #101](https://github.com/ThomasSerna/syntet/issues/101) |
| visualización y validación del ruteo | Hacer inspeccionable el grafo y evitar conexiones que no puedan ejecutarse con seguridad. | [SYN-075 · #102](https://github.com/ThomasSerna/syntet/issues/102) |
| compensación de latencia | Compensar latencia declarada o manual en rutas paralelas, auxiliares y exportación. | [SYN-076 · #103](https://github.com/ThomasSerna/syntet/issues/103) |

## E12 · Instrumentos internos

Épica: [SYN-E12 · #13](https://github.com/ThomasSerna/syntet/issues/13). Referencia: [FL: flujo de instrumentos](https://www.image-line.com/fl-studio-learning-content/fl-studio-online-manual/html/basics_workflow.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Síntesis sustractiva | Proporcionar osciladores, filtro y envolventes para melodías y bajos propios. | [SYN-077 · #104](https://github.com/ThomasSerna/syntet/issues/104) |
| percusión sintetizada | Generar percusión útil para beats sin depender de muestras propietarias. | [SYN-078 · #105](https://github.com/ThomasSerna/syntet/issues/105) |
| bajos 808 expresivos | Ofrecer bajos largos afinados adecuados para trap/drill y frases con deslizamientos. | [SYN-079 · #106](https://github.com/ThomasSerna/syntet/issues/106) |
| síntesis FM | Ampliar diseño sonoro mediante modulación de frecuencia con algoritmos documentados. | [SYN-080 · #108](https://github.com/ThomasSerna/syntet/issues/108) |
| wavetable | Usar tablas de onda propias y variar su posición durante una nota. | [SYN-081 · #109](https://github.com/ThomasSerna/syntet/issues/109) |
| modulación y gestión de voces | Controlar polifonía, robo de voces y moduladores sin asignar memoria en reproducción. | [SYN-082 · #107](https://github.com/ThomasSerna/syntet/issues/107) |
| presets propios | Reutilizar un sonido con identidad y parámetros versionados independientes de la UI. | [SYN-083 · #110](https://github.com/ThomasSerna/syntet/issues/110) |

## E13 · Efectos y medición

Épica: [SYN-E13 · #14](https://github.com/ThomasSerna/syntet/issues/14). Referencia: [FL: procesamiento en mezcla](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/mixer.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| EQ y filtros | Dar control tonal de mezcla con parámetros estables y representación de respuesta. | [SYN-084 · #111](https://github.com/ThomasSerna/syntet/issues/111) |
| compresión, limitación y puerta | Ofrecer dinámica básica con detectores y envolventes verificables. | [SYN-085 · #112](https://github.com/ThomasSerna/syntet/issues/112) |
| delay | Crear repeticiones con tiempo libre o musical, feedback y mezcla persistibles. | [SYN-086 · #113](https://github.com/ThomasSerna/syntet/issues/113) |
| reverberación | Añadir espacio a la mezcla con comportamiento estable y cola exportable. | [SYN-087 · #114](https://github.com/ThomasSerna/syntet/issues/114) |
| chorus, flanger y phaser | Ofrecer chorus, flanger y phaser con comportamiento y estado propios. | [SYN-088 · #115](https://github.com/ThomasSerna/syntet/issues/115) |
| saturación y waveshaping | Diseñar distorsión con curvas propias, ganancia y calidad documentadas. | [SYN-089 · #116](https://github.com/ThomasSerna/syntet/issues/116) |
| medición de picos, loudness, espectro y estéreo | Mostrar picos, loudness, espectro y relación estéreo de manera interpretable. | [SYN-090 · #117](https://github.com/ThomasSerna/syntet/issues/117) |

## E14 · Automatización y modulación

Épica: [SYN-E14 · #15](https://github.com/ThomasSerna/syntet/issues/15). Referencia: [FL: eventos de automatización](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/automation_eventeditor.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Parámetros con identidad estable | Identificar y describir parámetros de instrumentos, efectos y mezcla para guardar y automatizar. | [SYN-091 · #44](https://github.com/ThomasSerna/syntet/issues/44) |
| clips y curvas | Crear clips que controlen parámetros mediante segmentos temporales editables. | [SYN-092 · #65](https://github.com/ThomasSerna/syntet/issues/65) |
| grabación de movimientos | Capturar cambios de parámetros respecto del transporte para reproducirlos y editarlos. | [SYN-093 · #118](https://github.com/ThomasSerna/syntet/issues/118) |
| eventos dentro de patrones | Vincular cambios de controles a patrones reutilizables sin confundirlos con clips del arreglo. | [SYN-094 · #119](https://github.com/ThomasSerna/syntet/issues/119) |
| conversión entre eventos y clips | Trasladar una trayectoria entre eventos y clips declarando cualquier simplificación. | [SYN-095 · #120](https://github.com/ThomasSerna/syntet/issues/120) |
| macros, LFO y seguidores | Crear conexiones explícitas entre un controlador y destinos con rangos propios. | [SYN-096 · #121](https://github.com/ThomasSerna/syntet/issues/121) |
| comportamiento al iniciar, buscar y superponer automatizaciones | Hacer determinista el valor de un parámetro al iniciar, buscar, repetir o combinar fuentes de control. | [SYN-097 · #64](https://github.com/ThomasSerna/syntet/issues/64) |

## E15 · MIDI y controladores

Épica: [SYN-E15 · #16](https://github.com/ThomasSerna/syntet/issues/16). Referencia: [FL: MIDI](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/envsettings_midi.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Dispositivos y ruteo | Seleccionar entradas/salidas MIDI y rutearlas sin mezclar identidades de puertos. | [SYN-098 · #122](https://github.com/ThomasSerna/syntet/issues/122) |
| notas, CC y expresión | Convertir eventos MIDI admitidos a eventos del motor sin perder canal ni orden temporal. | [SYN-099 · #123](https://github.com/ThomasSerna/syntet/issues/123) |
| grabación y overdub | Capturar interpretación MIDI en patrones con cuantización opcional y posibilidad de deshacer. | [SYN-100 · #124](https://github.com/ThomasSerna/syntet/issues/124) |
| entrada por pasos | Componer sin interpretación en tiempo real mediante eventos de un controlador. | [SYN-101 · #125](https://github.com/ThomasSerna/syntet/issues/125) |
| MIDI learn y mapas | Relacionar controles físicos con parámetros estables y curvas seleccionables. | [SYN-102 · #126](https://github.com/ThomasSerna/syntet/issues/126) |
| importación MIDI | Convertir pistas, canales, notas y tempo de archivos MIDI a entidades editables. | [SYN-103 · #127](https://github.com/ThomasSerna/syntet/issues/127) |
| salida y sincronización con hardware de estudio | Controlar instrumentos externos desde el transporte de estudio con latencia explícita. | [SYN-104 · #128](https://github.com/ThomasSerna/syntet/issues/128) |

## E16 · VST3 y CLAP

Épica: [SYN-E16 · #17](https://github.com/ThomasSerna/syntet/issues/17). Referencia: [FL: alojamiento de plugins](https://www.image-line.com/fl-studio-learning-content/fl-studio-online-manual/html/plugins/wrapper.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Escaneo aislado y caché | Descubrir instrumentos y efectos externos sin que un escaneo fallido termine la sesión del usuario. | [SYN-105 · #129](https://github.com/ThomasSerna/syntet/issues/129) |
| alojamiento VST3 | Utilizar plugins VST3 como instrumentos o inserts de una sesión musical. | [SYN-106 · #130](https://github.com/ThomasSerna/syntet/issues/130) |
| alojamiento CLAP | Utilizar plugins CLAP sin introducir sus handles o extensiones en el modelo persistente. | [SYN-107 · #131](https://github.com/ThomasSerna/syntet/issues/131) |
| editores nativos | Editar plugins alojados desde sus interfaces de Windows dentro del flujo de Syntet. | [SYN-108 · #133](https://github.com/ThomasSerna/syntet/issues/133) |
| eventos, parámetros y buses | Conectar plugins al tiempo, eventos y ruteo del proyecto con correspondencias estables. | [SYN-109 · #134](https://github.com/ThomasSerna/syntet/issues/134) |
| persistencia del estado | Reabrir una sesión conserva los sonidos y ajustes que el usuario creó con plugins. | [SYN-110 · #135](https://github.com/ThomasSerna/syntet/issues/135) |
| recuperación de plugins ausentes o fallidos | Un plugin no disponible no impide recuperar y editar el resto del proyecto. | [SYN-111 · #136](https://github.com/ThomasSerna/syntet/issues/136) |
| evaluación del aislamiento durante procesamiento | Resolver si la ejecución de plugins requiere un proceso separado y qué garantías puede ofrecer el host. | [SYN-112 · #137](https://github.com/ThomasSerna/syntet/issues/137) |

## E17 · Biblioteca y contenido

Épica: [SYN-E17 · #18](https://github.com/ThomasSerna/syntet/issues/18). Referencia: [FL: navegador](https://www.image-line.com/fl-studio-learning-content/fl-studio-online-manual/html/browser.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Indexación y búsqueda | Localizar sonidos, presets y proyectos por texto y tipo de recurso. | [SYN-113 · #138](https://github.com/ThomasSerna/syntet/issues/138) |
| tags y favoritos | Crear colecciones personales que faciliten volver a encontrar sonidos. | [SYN-114 · #139](https://github.com/ThomasSerna/syntet/issues/139) |
| preescucha | Evaluar samples y loops antes de incorporarlos al beat. | [SYN-115 · #140](https://github.com/ThomasSerna/syntet/issues/140) |
| banco inicial redistribuible | Crear un primer beat sin instalar bancos propietarios ni descargar contenido obligatorio. | [SYN-116 · #141](https://github.com/ThomasSerna/syntet/issues/141) |
| presets de instrumentos, kits, patrones y efectos | Reutilizar configuraciones de sonido, batería, patrones y cadenas de mezcla entre proyectos. | [SYN-117 · #142](https://github.com/ThomasSerna/syntet/issues/142) |
| recursos usados por proyecto | Entender la dependencia de samples, grabaciones y recursos externos antes de trasladar una sesión. | [SYN-118 · #143](https://github.com/ThomasSerna/syntet/issues/143) |
| localización y sustitución de archivos ausentes | Reabrir y reparar proyectos trasladados o con archivos retirados. | [SYN-119 · #144](https://github.com/ThomasSerna/syntet/issues/144) |

## E18 · Render e intercambio

Épica: [SYN-E18 · #19](https://github.com/ThomasSerna/syntet/issues/19). Referencia: [FL: render y exportación](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/fformats_save_export.htm).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| WAV de canción, patrón y selección | Obtener audio de un proyecto con el mismo procesamiento musical utilizado en reproducción. | [SYN-120 · #145](https://github.com/ThomasSerna/syntet/issues/145) |
| profundidad y frecuencia de muestras | Exportar archivos adecuados para intercambio conservando duración y tratamiento explícito de cuantización. | [SYN-121 · #146](https://github.com/ThomasSerna/syntet/issues/146) |
| colas de efectos | Evitar cortar o prolongar indefinidamente reverberaciones y delays al exportar. | [SYN-122 · #147](https://github.com/ThomasSerna/syntet/issues/147) |
| stems alineados | Intercambiar una producción como archivos separados que puedan alinearse en otra estación. | [SYN-123 · #148](https://github.com/ThomasSerna/syntet/issues/148) |
| exportación MIDI | Llevar composición MIDI de Syntet a otras herramientas sin confundir propiedades internas con eventos estándar. | [SYN-124 · #149](https://github.com/ThomasSerna/syntet/issues/149) |
| consolidación y congelación reversible | Reducir carga o preparar material de audio sin perder instrumentos, notas ni procesamiento originales. | [SYN-125 · #150](https://github.com/ThomasSerna/syntet/issues/150) |
| exportación en segundo plano y formatos adicionales | Continuar trabajando mientras se exporta con control de progreso y formatos adicionales autorizados. | [SYN-126 · #153](https://github.com/ThomasSerna/syntet/issues/153) |

## E19 · Interfaz y aprendizaje

Épica: [SYN-E19 · #20](https://github.com/ThomasSerna/syntet/issues/20). Referencia: [egui: interacción y accesibilidad](https://docs.rs/egui_kittest/latest/egui_kittest/).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Espacio de trabajo y paneles | Acceder a patrones, Piano Roll, arreglo, mezcla y biblioteca sin perder la selección musical. | [SYN-127 · #132](https://github.com/ThomasSerna/syntet/issues/132) |
| atajos configurables | Editar con rapidez usando un mapa de teclado propio y recuperable. | [SYN-128 · #155](https://github.com/ThomasSerna/syntet/issues/155) |
| teclado y accesibilidad | Realizar el flujo musical principal sin depender exclusivamente del puntero o de señales visuales. | [SYN-129 · #156](https://github.com/ThomasSerna/syntet/issues/156) |
| DPI y contraste | Producir con tamaños de pantalla y escalas diferentes sin controles inaccesibles o estados ambiguos. | [SYN-130 · #157](https://github.com/ThomasSerna/syntet/issues/157) |
| español e inglés | Aprender y trabajar en cualquiera de los dos idiomas sin cambiar identidades del proyecto o de comandos. | [SYN-131 · #158](https://github.com/ThomasSerna/syntet/issues/158) |
| ayuda contextual | Entender qué hace una operación y cómo continuar cuando no puede realizarse. | [SYN-132 · #159](https://github.com/ThomasSerna/syntet/issues/159) |
| tutorial del primer tema | Una persona principiante termina una producción sin depender de un tutorial externo. | [SYN-133 · #160](https://github.com/ThomasSerna/syntet/issues/160) |
| plantillas y demostraciones propias | Aprender de proyectos completos de hip hop, trap y drill que puedan modificarse y redistribuirse. | [SYN-134 · #161](https://github.com/ThomasSerna/syntet/issues/161) |

## E20 · CLI, automatización y agentes

Épica: [SYN-E20 · #21](https://github.com/ThomasSerna/syntet/issues/21). Referencia: [SoundCraft: control por comandos](https://github.com/storytold/soundcraft/blob/main/AGENTS.md).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Operaciones tipadas | Concentrar validación y cambios musicales en un único límite de comandos independiente de la UI. | [SYN-135 · #34](https://github.com/ThomasSerna/syntet/issues/34) |
| descubrimiento de comandos y parámetros | Permitir que interfaz y agentes conozcan qué operaciones existen y cómo invocarlas. | [SYN-136 · #154](https://github.com/ThomasSerna/syntet/issues/154) |
| CLI sin ventana | Reproducir operaciones del núcleo de forma automatizable sin una ventana o GPU obligatoria. | [SYN-137 · #162](https://github.com/ThomasSerna/syntet/issues/162) |
| inspección y render por lotes | Verificar fixtures y exportar varios proyectos de forma reproducible sin intervención de interfaz. | [SYN-138 · #163](https://github.com/ThomasSerna/syntet/issues/163) |
| protocolo local autenticado | Permitir automatización de la instancia activa conservando control explícito del usuario. | [SYN-139 · #164](https://github.com/ThomasSerna/syntet/issues/164) |
| MCP | Un agente puede descubrir y utilizar las operaciones musicales autorizadas sin otra implementación del motor. | [SYN-140 · #165](https://github.com/ThomasSerna/syntet/issues/165) |
| errores comunes y protección frente a ediciones sobre un estado desactualizado | La automatización y la edición interactiva no sobrescriben cambios recientes sin detectarlo. | [SYN-141 · #151](https://github.com/ThomasSerna/syntet/issues/151) |

## E21 · Calidad y rendimiento

Épica: [SYN-E21 · #22](https://github.com/ThomasSerna/syntet/issues/22). Referencia: [FilmCraft: pruebas](https://github.com/storytold/filmcraft/blob/main/docs/testing.md).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Fixtures musicales y corpus | Evaluar cambios sobre entradas pequeñas, reproducibles y redistribuibles. | [SYN-142 · #166](https://github.com/ThomasSerna/syntet/issues/166) |
| pruebas DSP | Detectar errores de señal que no se descubren comprobando que un bloque produce audio. | [SYN-143 · #167](https://github.com/ThomasSerna/syntet/issues/167) |
| precisión temporal | Las notas y cambios temporales se ejecutan una sola vez en su posición prevista. | [SYN-144 · #168](https://github.com/ThomasSerna/syntet/issues/168) |
| equivalencia entre reproducción y render | Una exportación representa la producción escuchada en vez de un motor alternativo con comportamiento distinto. | [SYN-145 · #169](https://github.com/ThomasSerna/syntet/issues/169) |
| límites de CPU y memoria | Conocer la capacidad real del producto y la degradación ante presión de recursos. | [SYN-146 · #170](https://github.com/ThomasSerna/syntet/issues/170) |
| captura prolongada | Demostrar que el diseño de captura sostiene tomas útiles en el equipo objetivo. | [SYN-147 · #171](https://github.com/ThomasSerna/syntet/issues/171) |
| fallos de disco y dispositivos | Probar que los mecanismos de recuperación funcionan ante fallos reales del límite de entrada/salida. | [SYN-148 · #172](https://github.com/ThomasSerna/syntet/issues/172) |
| regresiones de interfaz y accesibilidad | Detectar cambios que rompan interacción y comprensión aunque el núcleo siga calculando correctamente. | [SYN-149 · #173](https://github.com/ThomasSerna/syntet/issues/173) |

## E22 · Mantenimiento y distribución

Épica: [SYN-E22 · #23](https://github.com/ThomasSerna/syntet/issues/23). Referencia: [PhotoCraft: capas y mantenimiento](https://github.com/storytold/photocraft/blob/main/AGENTS.md).

| Capacidad | Equivalencia o resultado previsto en Syntet | Tarea y evidencia |
|---|---|---|
| Comprobación de capas | Mantener dominio, audio e interfaces separados al crecer el proyecto. | [SYN-150 · #174](https://github.com/ThomasSerna/syntet/issues/174) |
| CI y lockfile | Detectar regresiones del núcleo en cada cambio integrado. | [SYN-151 · #175](https://github.com/ThomasSerna/syntet/issues/175) |
| política de actualizaciones | Evitar que futuras actualizaciones introduzcan cambios de comportamiento o licencias inadvertidos. | [SYN-152 · #152](https://github.com/ThomasSerna/syntet/issues/152) |
| compatibilidad de datos y API | Actualizar Syntet sin cambiar silenciosamente el significado de proyectos o integraciones. | [SYN-153 · #176](https://github.com/ThomasSerna/syntet/issues/176) |
| empaquetado Windows | Utilizar la aplicación en un equipo limpio sin depender del entorno de desarrollo. | [SYN-154 · #177](https://github.com/ThomasSerna/syntet/issues/177) |
| versiones y notas de publicación | Saber qué se entrega, de qué commit proviene y qué datos/integraciones admite. | [SYN-155 · #178](https://github.com/ThomasSerna/syntet/issues/178) |
| diagnóstico reproducible | Investigar problemas de audio, recursos y compatibilidad sin compartir datos privados por defecto. | [SYN-156 · #179](https://github.com/ThomasSerna/syntet/issues/179) |
| preparación de futuros puertos | Preparar Linux y macOS sin confundir diseño portable con soporte de producto entregado. | [SYN-157 · #180](https://github.com/ThomasSerna/syntet/issues/180) |

## Cobertura y cambios

La matriz conserva las capacidades de la planificación aprobada, incluidas las de largo plazo. Incorporar o retirar una capacidad requiere actualizar producto cuando afecte alcance, añadir o modificar su issue y corregir este índice en la misma entrega. Los IDs no se reutilizan ni renumeran.

Exportar stems no equivale a separar una mezcla; edición de notas no equivale a herramientas creativas; grabar una toma no equivale a gestionar tomas. Performance Mode, actuaciones en directo, FLP y equivalentes individuales del catálogo propietario siguen fuera del alcance.

La auditoría de publicación está en [el informe](publication-audit.md); sus resultados son una fotografía fechada, no el estado operativo de las capacidades.
