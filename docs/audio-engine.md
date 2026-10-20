# Motor de audio y grabación

Estado: especificación de diseño y protocolo de validación; todavía no existe motor ejecutable. Fecha: 2026-10-20.

El [modelo de arquitectura](architecture.md) separa documento, edición y ejecución. Los casos y resultados exigidos se detallan en [pruebas](testing.md) y en las issues de E01, E10, E11, E14 y E21.

## Contrato de render

Reproducción y exportación ejecutarán la misma semántica de notas, clips, automatización, instrumentos y mezcla. El dispositivo no es el reloj lógico de una exportación. El motor acepta el tamaño de bloque efectivo; ningún tamaño interno fijo se confunde con latencia garantizada del hardware.

El diseño conservará posiciones musicales y posiciones enteras de muestras por separado. El mapa de tempo convertirá entre ambas con una política determinista de redondeo. Resolución musical, representación de rampas y orden de eventos simultáneos se cerrarán con ejemplos antes de implementar scheduling; note-off/note-on, saltos y fin de bucle necesitan resultados definidos.

El transporte distingue posición solicitada y posición procesada. Play, pausa, stop, seek y bucle documentarán qué ocurre con voces, colas, automatización y contador. Los cambios de tempo no deben crear notas duplicadas o sostenidas indefinidamente.

## Propiedad y tiempo real

Fuera del callback se realizan lectura, decodificación, asignación de memoria, construcción de grafos, serialización, creación y destrucción de plugins y preparación de recursos.

Dentro del callback se procesa audio con memoria preparada, trabajo acotado y comunicación no bloqueante. Las colas tienen capacidad y política de saturación explícitas: los eventos perdidos o los huecos de captura se contabilizan y comunican; no se ocultan mediante corrupción silenciosa de tiempo.

La retirada de planes y recursos vuelve al control o a un trabajador. No basta usar referencias compartidas si su último descarte puede liberar una sesión o un plugin grande desde el callback.

La UI toma snapshots de posición y medidores. Los medidores no bloquean el audio por un panel lento. Los diagnósticos del callback se transfieren a otro hilo antes de escribir logs.

## Dispositivos de Windows

CPAL con WASAPI compartido es la propuesta inicial. Se validarán enumeración, entrada/salida, formato efectivo, timestamps, errores y combinaciones de dispositivos en el PC objetivo antes de declararlo backend definitivo.

El tamaño de búfer solicitado no demuestra la periodicidad efectiva ni la latencia de extremo a extremo. No se presupuesta una API duplex, modo exclusivo o ASIO sin comprobar la versión publicada utilizada. Se registrarán versión de CPAL, driver, frecuencia, formato y período observados.

El proyecto inicial propone 48 kHz; la elección se negociará con los dispositivos o se convertirá fuera del callback según el adaptador. Importar 44,1 kHz, reproducir a otra frecuencia y exportar no debe cambiar tono o duración por error.

La primera grabación de voz reproduce el beat por auriculares y escucha la toma después. La monitorización de micrófono en vivo no es requisito de M2.

## Captura, alineación y deriva

Entrada y salida pueden tener callbacks y relojes distintos. Un ring buffer solo absorbe variación de entrega; no resuelve deriva sostenida.

El flujo previsto es:

1. El adaptador de entrada entrega bloques y anclas temporales a una cola preasignada.
2. Un trabajador escribe audio recuperable a disco sin esperar al editor.
3. La sesión relaciona anclas de captura con el transporte de reproducción.
4. Se estima y valida offset y deriva con una política documentada por adaptador.
5. La toma conserva fuente y metadatos de alineación; el ajuste o conversión no destruye la captura original.

No se restan timestamps de streams arbitrarios sin comprobar su dominio de reloj. Una conversión de frecuencia ajustable puede ser necesaria para dispositivos independientes; su calidad, capacidad de seguimiento y memoria se probarán.

Los huecos de captura se marcan en su posición temporal. Rellenarlos con silencio para preservar duración, si se adopta esa política, no convierte la toma en una captura sin pérdidas. El usuario recibe un resultado que permite identificar el tramo afectado.

## Grabaciones recuperables

La toma activa se escribe en un temporal propio y recuperable. Se actualizan cabecera y puntos de recuperación con una estrategia verificable. Al detener, se valida y finaliza antes de añadirla al proyecto como recurso terminado.

Un fallo de dispositivo, permisos, espacio o disco debe detener el trabajo con error visible y conservar lo escrito que pueda recuperarse. El proyecto previo permanece válido. La edición posterior usa clips y fades; los originales de todas las tomas se conservan salvo eliminación explícita por el usuario.

La grabación en bucle crea tomas identificables; seleccionar fragmentos para comping no destruye los demás. Punch y cuenta de entrada se especificarán respecto del transporte y su compensación.

## Mezcla y automatización

El grafo describe instrumentos y audio, inserts, envíos, buses y master. Se rechazan rutas no admitidas antes de ejecutar. Añadir sidechain y multi-I/O exige pruebas de topología y compensación; un cambio de cableado no debe invalidar silenciosamente un parámetro o un recurso.

Los parámetros poseen IDs, unidades, rangos y metadatos de automatización. La semántica de inicialización, superposición, seek y conversión entre eventos y clips se decidirá explícitamente en E14. Las actualizaciones continuas se suavizan según el parámetro; controles discretos conservan su naturaleza.

Los hosts de plugins crearán instancias y editores fuera del audio. La compensación incluirá caminos paralelos, sidechains y colas al exportar. El escaneo aislado es distinto de contener un crash durante process; esa segunda decisión exige una investigación propia.

## Puerta de M1

Antes de construir toda la UI se demostrará un proyecto mínimo con reproducción y exportación, captura a disco, alineación y recuperación. La evidencia incluirá:

- Comparación del render por diferentes particiones de bloque y semillas controladas.
- Captura prolongada y medición de offset/deriva; combinaciones de entrada/salida identificadas.
- Detección de pérdidas, saturación de colas y cambios de dispositivo.
- Fallos de disco, cancelación y grabación interrumpida con recuperación del material previo.
- Instrumentación que detecte operaciones indebidas del callback.

El escenario inicial de carga es una propuesta de 16 canales instrumentales más voz durante diez minutos. En M1 se usarán fuentes y procesadores sintéticos del harness; los instrumentos y editores de producto no son prerrequisito. No es un límite del formato ni una cifra de rendimiento demostrada. Una calibración exploratoria precederá la fijación de umbrales y condiciones; la prueba de aceptación será una corrida independiente con esos valores congelados. Se registrará cualquier resultado que obligue a revisar el backend.

Fuentes: [CPAL 0.18.2](https://docs.rs/cpal/0.18.2/cpal/), [ejemplo de streams separados](https://github.com/RustAudio/cpal/blob/v0.18.2/examples/feedback.rs), [latencia de Windows](https://learn.microsoft.com/en-us/windows-hardware/drivers/audio/low-latency-audio), [SoundCraft](https://github.com/storytold/soundcraft/blob/main/crates/playback/src/lib.rs). Son referencias de diseño; no mediciones de Syntet.
