# Verificación y evidencia

Esta guía define cómo se comprobará Syntet. La entrega inicial contiene documentación y planificación: todavía no existe un ejecutable, un workspace Cargo ni resultados de pruebas de audio. Los escenarios siguientes son requisitos y propuestas de validación, no mediciones realizadas.

## Qué demuestra una capacidad

Una función pasa de implementada a verificada cuando satisface la aceptación de su issue con evidencia reproducible. Un menú conectado, una captura o una PR integrada no demuestran por sí solos precisión musical, compatibilidad ni estabilidad.

La evidencia debe indicar commit, configuración, entrada, operación, resultado esperado y resultado obtenido. Las pruebas de hardware añaden sistema, dispositivo, controlador, frecuencia, canales y período efectivo. Se conservarán limitaciones y casos omitidos junto al resultado.

GitHub Issues conserva la aceptación y la evidencia operativa. La [matriz funcional](reference/fl-studio-matrix.md) relaciona capacidades y referencias; el [roadmap](roadmap.md) define los resultados de cada entrega.

## Comprobación de esta entrega documental

- Los documentos enlazados existen y sus enlaces relativos resuelven dentro del repositorio.
- Los IDs de épicas y capacidades son únicos; cada capacidad tiene una issue y una épica principal.
- Las dependencias existen, carecen de ciclos y no convierten una función avanzada en requisito accidental del primer flujo.
- La matriz, el índice local y GitHub identifican el mismo conjunto de capacidades.
- Cada issue tiene objetivo, alcance, hito, prioridad, dependencias, aceptación y evidencia esperada.
- Las decisiones confirmadas, las propuestas y los aspectos pendientes de validación están diferenciados.
- No se anuncian APIs, comandos, tests, assets o funcionalidades de aplicación inexistentes.
- Una publicación interrumpida se detecta mediante los marcadores estables antes de repetir creaciones.

El informe de publicación debe registrar conteos, enlaces y comprobaciones efectivamente realizadas. Una auditoría documental no cuenta como prueba del motor.

## Corpus musical

El corpus se construirá con señales sintéticas, proyectos originales y archivos con permiso de redistribución. Cada fixture externo tendrá origen, licencia, revisión o versión y hash; los sonidos originales tendrán autoría registrada en [ATTRIBUTION.md](../ATTRIBUTION.md).

Se fijarán semillas para generadores aleatorios. Se empezará con entradas pequeñas que permitan inspeccionar el resultado: impulsos, silencio, tonos conocidos, patrones cortos, notas superpuestas y clips con límites exactos. Se incorporarán corpus grandes cuando exista una pregunta de compatibilidad o rendimiento concreta.

No se copiarán bancos, presets ni proyectos de demostración de FL Studio. Las observaciones de caja negra seguirán el [método de investigación](reference/research-method.md).

## Pruebas por límite

| Área | Escenarios y comprobaciones |
|---|---|
| Tiempo y scheduling | Notas en límites de bloque, seek, repetición, cambios de tempo y compás; ausencia de eventos perdidos o duplicados; conversión musical/muestras coherente. |
| Modelo y comandos | IDs válidos, operaciones inválidas sin cambios parciales, selección múltiple, copias compartidas e independientes; deshacer/rehacer restaura el estado musical y agrupa un gesto continuo. |
| DSP e instrumentos | Afinación con tonos conocidos, respuesta a impulsos, ganancia, silencio, niveles extremos, polifonía y retiro de voces; salida finita y estado determinista cuando corresponda. |
| Automatización | Curvas y eventos al iniciar, buscar o repetir; límites de parámetros; identidad estable después de guardar y reabrir. |
| Persistencia | Round-trip completo, recursos relativos, rutas movidas, plugin o sample ausente, versión futura, migración y truncamiento; conservar el último proyecto válido ante un fallo. |
| Grabación | Captura por bloques, discontinuidades, alineación con transporte, relojes distintos, disco lleno y cierre inesperado; preservar la parte recuperable de cada toma. |
| Render | Misma planificación y DSP en reproducción y exportación; semillas y eventos idénticos; duraciones, colas y stems alineados. |
| Plugins | Matriz de plugins representativos por formato; buses, parámetros, transporte, estado, editor, latencia y fallos de escaneo; no generalizar compatibilidad a plugins no probados. |
| Importación y control | Archivos truncados, tamaños excesivos, referencias inválidas, números no finitos y comandos malformados; errores acotados sin pérdida del proyecto. |

Las tolerancias numéricas se fijarán por algoritmo y propósito antes de aceptar el test. No se elegirá un margen amplio para ocultar una diferencia desconocida. La comparación de render solo admitirá las diferencias justificadas por formato de salida, redondeo o algoritmos expresamente no deterministas.

## Seguridad de tiempo real

La arquitectura se describe en [audio-engine.md](audio-engine.md). Las pruebas del callback deberán cubrir preparación, reproducción, cambios de parámetros, seek y sustitución de recursos.

- Instrumentar asignaciones y desasignaciones realizadas por código propio en las rutas de audio después de preparar el proyecto.
- Comprobar que serialización, acceso a disco, decodificación, construcción del grafo y destrucción de recursos grandes ocurren fuera del callback.
- Saturar las colas acotadas y comprobar una política explícita de error, coalescencia o reintento; no perder cambios silenciosamente.
- Medir tiempo de procesamiento por bloque y contar interrupciones, pérdidas y discontinuidades, conservando la configuración efectiva.
- Comprobar que la exportación funciona sin abrir un dispositivo de audio.

Una biblioteca que se declara apta para tiempo real no sustituye estas verificaciones de su integración.

## Escenario inicial de hardware

Escenario propuesto para M1/M2: reproducir dieciséis canales instrumentales representativos mientras se captura una voz durante diez minutos, primero sin monitorización de micrófono. El objetivo es validar el audio actual del PC sin exigir una interfaz externa.

Se registrarán carga de voces y efectos, configuración de entrada/salida, frecuencia del proyecto y dispositivos, tamaño solicitado y período observado, duración, pérdidas de captura, interrupciones y consumo de recursos. No se deducirá latencia real de un tamaño nominal de búfer.

La alineación se medirá con impulsos y un recorrido de loopback documentado. La simulación automatizada cubrirá relojes con deriva; la prueba física comprobará el adaptador y los timestamps reales. Si falta el recorrido físico necesario, el caso se marca pendiente, no aprobado. Una calibración exploratoria de M1 informará los umbrales; después se fijarán en la issue y se ejecutará una corrida de aceptación independiente. Los umbrales no se ajustarán retrospectivamente para convertir un fallo en aprobación.

En M1 se utilizan fuentes, voces y procesadores sintéticos del harness. No se exige que existan los instrumentos, efectos ni editores de producto que llegarán en M2 o después; el escenario de carga se repetirá con ellos cuando estén disponibles.

Se repetirán escenarios con permiso de micrófono denegado, dispositivo ausente/desconectado, cambio de formato, sobrecarga, espacio agotado y cierre durante una toma. Cada fallo deberá producir un estado visible y conservar los datos recuperables; no basta con evitar un panic.

## Interfaz, idiomas y accesibilidad

Los tests de dominio serán la primera opción para lógica musical. Se usarán interacciones de interfaz para verificar lo que realmente depende de foco, puntero, teclado, disposición y accesibilidad.

El recorrido mínimo incluye activar pasos, editar y desplazar notas, cambiar zoom y scroll, colocar clips, ajustar mezcla, grabar, guardar y exportar. Se comprobará en español e inglés y a escalas de Windows 100 %, 150 % y 200 %. Los controles personalizados deberán exponer nombre, estado y valor; se comprobarán con navegación por teclado y NVDA en Windows.

Las capturas usarán datos y configuración fijados. Se inspeccionará una tanda de vistas representativas, se agruparán correcciones y se hará una confirmación; las diferencias de GPU se investigarán antes de modificar tolerancias. El soporte AccessKit no demuestra automáticamente accesibilidad del Piano Roll.

## Regresiones y mantenimiento

Cada corrección de pérdida de datos, crash o precisión musical incluirá un caso pequeño que reproduzca el fallo anterior. Los cambios de formato incluirán fixtures anteriores y el resultado esperado de migración. Los cambios DSP actualizarán su evidencia de señal; los cambios de dependencia volverán a comprobar las rutas afectadas.

La futura CI ejecutará comprobaciones reproducibles de formato, lint, capas, corpus y tests con dependencias fijadas. La validación con hardware se registrará aparte de los tests automatizados: un runner sin dispositivo no demuestra grabación real.

## Referencias

- [Pruebas de FilmCraft](https://github.com/storytold/filmcraft/blob/main/docs/testing.md): corpus, pruebas por subsistema y evidencia.
- [Evaluación de PhotoCraft](https://github.com/storytold/photocraft/blob/main/docs/target-app-parity.md): diferencia entre cobertura funcional y preparación real.
- [egui_kittest](https://docs.rs/egui_kittest/latest/egui_kittest/): interacciones, árbol accesible y capturas; versión a fijar cuando exista el workspace.
- [Audio en FL Studio](https://www.image-line.com/fl-studio-learning/fl-studio-online-manual/html/envsettings_audio.htm): relación entre configuración, latencia y fallos de audio.
