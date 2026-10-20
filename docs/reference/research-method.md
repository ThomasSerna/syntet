# Investigación de referencia y caja negra

Este método convierte documentación y comportamiento observable en especificaciones propias. El inventario está en la [matriz funcional](fl-studio-matrix.md); producto y límites están en [producto](../product.md). GitHub Issues conserva responsables, ejecución y evidencia.

## Fuentes y autoridad

1. Las decisiones del usuario fijan el objetivo de Syntet.
2. Los manuales oficiales de Image-Line describen la referencia documentada de FL Studio.
3. Los escenarios observados identifican comportamiento de una versión y configuración concretas.
4. Las guías y el código públicos de Artcraft aportan prácticas de ingeniería; no prueban estabilidad ni equivalencia de Syntet.
5. Una decisión de Syntet puede diferir de la referencia si está explicada y vinculada a su issue o ADR.

La referencia inicial instalada es FL Studio 26.1.7.5654. El manual web puede evolucionar de forma independiente. Registrar URL, fecha de consulta, versión/edición cuando estén disponibles y límites de cobertura. Una ausencia en una búsqueda parcial no demuestra que una función no exista.

## Procedimiento por capacidad

1. Seleccionar la fila de la matriz y leer su issue; definir la pregunta y el resultado a observar.
2. Consultar el manual oficial y anotar lo que establece y lo que deja sin resolver.
3. Preparar un escenario pequeño con notas, señales y grabaciones propios. Anotar estado inicial, entradas, pasos y resultado esperado.
4. Cuando exista acceso de observación compatible, reproducir los pasos en FL Studio y conservar evidencia vinculada a versión y configuración. Si no se puede observar, registrar el límite y mantener la afirmación como documentada o pendiente.
5. Redactar el comportamiento de Syntet con sus límites, errores y verificación. Separar diferencias intencionales de defectos pendientes.
6. Añadir los enlaces a la issue y a la matriz; cerrar la investigación únicamente cuando la evidencia responda a su pregunta o delimite explícitamente lo desconocido.

La finalización documental no marca implementada ni validada una capacidad musical. Para entregar una función se necesitarán pruebas propias y los escenarios de [verificación](../testing.md).

## Registro mínimo de evidencia

| Campo | Contenido |
|---|---|
| Capacidad / issue | ID estable y URL. |
| Pregunta | Afirmación concreta que se quiere comprobar. |
| Autoridad | Documentación, observación controlada o inferencia de ingeniería. |
| Referencia | Versión, edición, configuración y fecha; URL y fecha de consulta para el manual. |
| Estado inicial | Proyecto propio, recursos y ajustes necesarios para reproducir. |
| Procedimiento | Pasos ordenados, entradas y operaciones. |
| Resultado | Comportamiento observado o documentado; artefacto que lo respalda. |
| Límites | Lo que no se observó, diferencias de versión y dudas restantes. |
| Decisión Syntet | Resultado previsto, diferencia intencional y enlace a ADR cuando corresponda. |

## Límites del método

Se adopta observación de caja negra: documentación pública y escenarios visibles con material de prueba propio. No se descompilan binarios ni se copian recursos, código, presets, iconos o bibliotecas de la instalación propietaria. No se presentan capturas de referencia como arte propio ni se incluyen en el repositorio sin comprobar sus condiciones de publicación. Las pruebas y demostraciones redistribuidas usarán material propio o con permiso suficiente.

Los recursos candidatos se registran por autor, origen, licencia y versión antes de incorporarlos. Gratis y royalty-free no significan permiso para redistribuir una biblioteca. La documentación de Image-Line distingue esos usos: [aclaración de contenido](https://support.image-line.com/action/knowledgebase?ans=717). El control de atribución de Syntet estará en [ATTRIBUTION](../../ATTRIBUTION.md).

La disponibilidad de REA no garantiza que su observación de interfaz nativa sea compatible con Windows o que un proveedor de análisis esté configurado. La presente entrega no instala proveedores, modifica FL Studio ni declara haber medido audio. Si falta una vía de observación, la investigación puede avanzar mediante documentación y debe conservar el pendiente de runtime.

## Fichas preparadas para observación y verificación

Las seis fichas siguientes son procedimientos preparados, no resultados ejecutados. Su estado inicial es **runtime FL pendiente; implementación y validación de Syntet pendientes**. Al usarlas, crear un registro de evidencia separado con los campos anteriores y los pasos concretos de la interfaz observada. Los resultados previstos de Syntet no constituyen afirmaciones sobre la aceptación o el comportamiento de FL Studio.

Material común propio: preparar `ref-tone.wav`, mono, 48 kHz, PCM de 24 bits, duración de 1 segundo, seno de 440 Hz a -18 dBFS de pico y fades lineales de 10 ms en ambos extremos. Esta es la receta de una fixture futura; no se ha generado ni añadido el archivo en esta entrega. Registrar herramienta de generación, parámetros y hash al producirla. En cada ficha usar un proyecto nuevo, tempo de 120 BPM y compás 4/4, salvo indicación distinta.

### REF-01 · Patrón compartido frente a copia independiente

**Pregunta:** ¿qué ediciones afectan a dos clips que referencian el mismo patrón y cuáles quedan limitadas a una copia independiente?

**Estado inicial:** un sampler con `ref-tone.wav`; patrón P de un compás con notas de un octavo de pulso en los pulsos 0 y 2. Dos clips, A y B, referencian P en los compases 1 y 3 de una pista de arreglo. Conservar una captura o listado de esas referencias.

**Pasos:**

1. Añadir al patrón P una nota en el pulso 1. Reproducir y registrar A y B por separado.
2. Convertir B en una copia de contenido independiente, llamada P2; registrar el procedimiento utilizado y las identidades resultantes.
3. Añadir a P2 una nota en el pulso 3, sin editar P. Reproducir A y B de nuevo.
4. Deshacer la última inserción, rehacerla, guardar y reabrir el proyecto. Volver a inspeccionar las notas y referencias de ambos clips.

**Resultado previsto de Syntet:** el paso 1 cambia el contenido reproducido por ambos clips. Después de independizar B, la nota del pulso 3 aparece solo en B. Undo, redo y reapertura conservan tanto las notas como la relación compartida o independiente de cada clip.

**Evidencia a recoger:** versión/edición, listado de notas y referencias antes/después, procedimiento para crear contenido único y render propio de A/B. Registrar por separado cualquier diferencia de FL observada. **Runtime FL: pendiente.**

### REF-02 · Instrumento, pista de arreglo y canal de mezcla

**Pregunta:** ¿puede cambiarse la organización visual del arreglo sin cambiar el instrumento ni su destino de mezcla?

**Estado inicial:** dos instrumentos propios I1 e I2 que usan `ref-tone.wav`; I1 toca C4 y está asignado al canal de mezcla M1; I2 toca C5 y está asignado a M2. Un patrón contiene una nota de cada instrumento en pulsos distintos. Dos clips de ese patrón están en pistas de arreglo T1 y T2. Desactivar efectos y normalización para facilitar la comparación.

**Pasos:**

1. Reproducir ambos clips y registrar actividad de M1 y M2. Exportar una referencia de audio propia.
2. Mover el clip de T2 a T1 y después reordenar y renombrar T1; mantener posiciones musicales, instrumentos y ruteo.
3. Reproducir y exportar con los mismos ajustes. Comparar contenido y actividad de mezcla con el paso 1.
4. Cambiar explícitamente el destino de I2 a M1. Reproducir, deshacer el cambio y comprobar que vuelve a M2.

**Resultado previsto de Syntet:** el cambio de pista o nombre no altera notas, sonido ni ruteo. Solo la edición explícita del paso 4 modifica el destino de I2; undo lo restaura. La configuración permite varias notas/instrumentos por patrón y clips en pistas diferentes sin una relación uno-a-uno obligatoria.

**Evidencia a recoger:** referencias de instrumento/patrón/clip/canal, capturas de medidores y comparación de renders propios con ajustes y tolerancia anotados. Si la referencia dispone de pistas enlazadas, registrar si estaban activadas antes de interpretar el resultado. **Runtime FL: pendiente.**

### REF-03 · Cuantización de inicios y deshacer de una frase

**Pregunta:** ¿la cuantización modifica únicamente los atributos elegidos y puede deshacerse como una operación completa?

**Estado inicial:** frase propia de un compás con cuatro notas. Expresar posiciones y duraciones en pulsos de negra: C4 en 0,10 con duración 0,40 y velocidad MIDI 70; E4 en 1,18 con duración 0,55 y velocidad 80; G4 en 1,88 con duración 0,35 y velocidad 90; B4 en 3,07 con duración 0,70 y velocidad 100. Registrar las posiciones efectivas si la rejilla interna redondea esos valores.

**Pasos:**

1. Seleccionar las cuatro notas y conservar un listado de inicio, duración, altura y velocidad.
2. Cuantizar solo los inicios a la negra más cercana, intensidad del 100 %, sin swing ni humanización. Registrar cualquier ajuste equivalente necesario en la referencia.
3. Inspeccionar los cuatro atributos y reproducir la frase cuantizada.
4. Deshacer una vez y comparar con el listado inicial; rehacer una vez y comparar con el resultado cuantizado.

**Resultado previsto de Syntet:** los inicios quedan en los pulsos 0, 1, 2 y 3. Duración, altura y velocidad permanecen iguales. Un solo undo recupera todas las posiciones originales y un redo vuelve al resultado cuantizado.

**Evidencia a recoger:** listas de eventos antes/después/undo/redo, configuración de cuantización y grabación o capturas del gesto. No inferir equivalencia desde el nombre de la herramienta si sus ajustes difieren. **Runtime FL: pendiente.**

### REF-04 · Alineación de captura y conservación de tomas

**Pregunta:** ¿cómo se mide el desfase de la grabación respecto al transporte y se conservan las tomas al grabar en bucle?

**Estado inicial:** proyecto propio con diez minutos de pulsos de prueba. Preparar una señal mono a 48 kHz con un pulso de seno de 1 kHz y 10 ms, pico de -18 dBFS y fades de 2 ms, cada segundo desde t=0 hasta t=599 s. Añadir dos pulsos a t=0,10 y 0,20 s y otros dos a t=599,10 y 599,20 s para identificar los extremos. Usar el micrófono del equipo captando su salida a un nivel controlado, sin monitorización de entrada; registrar los dispositivos, la ruta acústica y cualquier procesamiento del sistema. La receta no constituye una medición de latencia.

**Pasos:**

1. Armar una pista mono vacía y grabar la señal completa con una cuenta de entrada de un compás. Conservar la captura original y los ajustes efectivos de entrada/salida.
2. Medir el offset entre el primer grupo emitido y capturado, y repetir con el último. Registrar ambos offsets y su diferencia; identificar los pulsos por sus grupos, sin asumir que los relojes están sincronizados.
3. En otro proyecto propio, establecer un bucle de cuatro compases y grabar tres pasadas vocales diciendo «toma uno», «toma dos» y «toma tres» en sus respectivas vueltas.
4. Seleccionar y reproducir cada toma por separado, guardar y reabrir; comprobar que las tres siguen disponibles. Conservar los archivos originales incluso si la interfaz propone otra organización.

**Resultado previsto de Syntet:** la captura conserva su duración y declara pérdidas si ocurren. Puede medirse y compensarse alineación/deriva mediante una política documentada, sin inventar una cifra de latencia por el búfer nominal. Las tres tomas permanecen independientes y seleccionables después de reabrir, con monitorización en vivo apagada. La selección/combinación de tomas es una capacidad prevista de Syntet, no una afirmación sobre la UI de FL.

**Evidencia a recoger:** señal y capturas propias con hashes, dispositivos, frecuencias efectivas, duración, offsets inicial/final, incidencias y organización de las tomas. La ruta acústica añade su propio retardo y no equivale por sí sola a medir latencia eléctrica de ida/vuelta. Si no hay entrada utilizable, dejar el caso sin ejecutar y registrar el impedimento. **Runtime FL: pendiente.**

### REF-05 · Guardado, traslado y localización de recursos

**Pregunta:** ¿qué recursos permiten reabrir un proyecto en otra ruta y cómo se conserva el documento cuando falta una fuente?

**Estado inicial:** carpeta de prueba A con un proyecto propio de dos clips: uno usa una copia incorporada de `ref-tone.wav`; el otro referencia un archivo externo propio distinto, `ref-external.wav`, con hash conocido. Registrar las notas, posiciones, offsets y recursos. Preparar una copia B en otra ruta usando únicamente estos datos de prueba.

**Pasos:**

1. Guardar A, cerrar y reabrir; comparar con el registro inicial.
2. Recopilar los recursos incorporados al copiar a B. Hacer temporalmente inaccesible A solo para esta prueba —por ejemplo, renombrando su carpeta de fixture— y abrir B; conservar todos los originales.
3. Hacer inaccesible únicamente el recurso externo de la fixture y reabrir B. Registrar el error o estado del clip y la referencia conservada.
4. Localizar una copia de ese recurso con el mismo hash en otra ruta, vincularla, guardar B y reabrir. Restaurar después los nombres de las carpetas de prueba.

**Resultado previsto de Syntet:** B reproduce su recurso incorporado sin depender de A. La ausencia externa se identifica sin perder el clip ni sobrescribir el último proyecto válido. Volver a vincular la misma fuente restaura reproducción, offsets y propiedades; el nuevo guardado conserva esa resolución. Las diferencias del formato o del flujo de recopilación observado en FL se documentan por separado.

**Evidencia a recoger:** estructura de directorios de fixture, hashes, inventario semántico antes/después, pasos de recopilación/relink y capturas del estado ausente. No publicar rutas personales ni probar renombrado sobre proyectos reales del usuario. **Runtime FL: pendiente.**

### REF-06 · Automatización, mezcla, stems y MIDI

**Pregunta:** ¿la automatización de volumen conserva su significado en reproducción y exportación, y qué alineación y contenido preservan la mezcla, las pistas separadas y el MIDI?

**Estado inicial:** proyecto propio de ocho compases a 120 BPM y 4/4 —intervalo de 0 a 16 segundos— con dos instrumentos que usan `ref-tone.wav`. I1 dispara una nota de un pulso al principio de cada compás y va al canal M1; I2 dispara una nota una octava más alta en el tercer pulso de cada compás y va a M2. Sin efectos, envíos, normalización ni compensaciones manuales; master a 0 dB. Automatizar M1 mediante una rampa lineal en dB de 0 dB en t=0 a -6 dB en t=8 s, manteniendo -6 dB hasta el final. Registrar nota raíz, alturas y velocidades efectivas. El fixture evita procesamiento compartido para permitir una comparación aditiva inequívoca.

**Pasos:**

1. Reproducir desde el principio; después buscar a t=10 s y comprobar el valor de M1. Registrar curva y puntos efectivos si la referencia representa el volumen en otra unidad.
2. Exportar la mezcla del intervalo exacto de ocho compases a WAV, 48 kHz, PCM de 24 bits, con normalización desactivada y colas limitadas al intervalo. Registrar las opciones realmente disponibles.
3. Exportar M1 y M2 como stems secos del mismo intervalo, manteniendo silencio inicial y duración común. Importarlos en un proyecto vacío a t=0 con ganancia unitaria; comparar su suma con la mezcla del paso 2 y medir la atenuación de los golpes de I1 antes y después de la rampa.
4. Exportar las notas y el tempo a MIDI estándar e importarlos en otro proyecto vacío. Comparar posiciones, alturas, velocidades, duraciones y tempo con el listado de eventos original; registrar cómo se representan instrumentos/canales y qué datos no son intercambiables.

**Resultado previsto de Syntet:** buscar a t=10 s establece M1 en -6 dB sin requerir reproducir la rampa completa. Mezcla y stems respetan la automatización y tienen la misma referencia temporal; los stems de este fixture suman la mezcla dentro de una tolerancia de cuantización documentada. MIDI conserva notas y tempo soportados, pero no se presupone que transporte el audio del sampler ni la automatización de un parámetro interno sin mapeo MIDI explícito. Estos stems se renderizan desde fuentes y ruteo conocidos: la ficha no ejecuta ni requiere separar instrumentos de una mezcla existente.

**Evidencia a recoger:** proyecto y fuentes propios con hashes; puntos/valores de automatización; listado de eventos MIDI antes/después; ajustes de render; frecuencia, profundidad, longitud y offset de cada WAV; comparación de suma y mediciones de nivel. Documentar cualquier diferencia de FL sin declarar equivalencia desde los nombres de opciones. **Runtime FL: pendiente.**

### Cierre de la preparación documental

La tarea documental de escenarios queda comprobable cuando REF-01..06 contienen pregunta, material propio reproducible, pasos, resultado previsto de Syntet y evidencia a recoger, y todos conservan su estado de runtime pendiente. Ejecutar una ficha añadirá su evidencia y límites; no cambiará retroactivamente una previsión en observación. Nuevas fichas cubrirán sampling y automatización/ruteo avanzados al llegar sus respectivas tareas.

## Referencias públicas iniciales

| Área | Fuente oficial |
|---|---|
| Principios Artcraft | [PhotoCraft AGENTS](https://github.com/storytold/photocraft/blob/main/AGENTS.md), [SoundCraft AGENTS](https://github.com/storytold/soundcraft/blob/main/AGENTS.md). |
| Arquitectura y progreso | [FilmCraft arquitectura](https://github.com/storytold/filmcraft/blob/main/docs/architecture.md), [evaluación de PhotoCraft](https://github.com/storytold/photocraft/blob/main/docs/target-app-parity.md). |
| Flujo y arreglo | [Flujo de FL Studio](https://www.image-line.com/fl-studio-learning-content/fl-studio-online-manual/html/basics_workflow.htm), [Playlist](https://www.image-line.com/fl-studio-learning-content/fl-studio-online-manual/html/playlist.htm). |
| Notas y composición | [Piano Roll](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/pianoroll_menu.htm). |
| Grabación y entrega | [Grabación de audio](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/recording_audio.htm), [exportación](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/fformats_save_export.htm). |
| Sampling | [Sampler](https://www.image-line.com/fl-studio-learning-content/fl-studio-online-manual/html/chansettings_sampler.htm), [FPC](https://www.image-line.com/fl-studio-learning-content/fl-studio-online-manual/html/plugins/FPC.htm). |

`craftrules` y los planes locales originales de Artcraft no son fuentes disponibles. No sustituir ese límite por una afirmación de revisión completa.
