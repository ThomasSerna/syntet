# Proyecto, recursos y recuperación

Estado: contrato de comportamiento; contenedor y esquema exactos propuestos, sujetos a ADR antes de implementar. Fecha: 2026-10-20.

La aplicación tendrá su propio formato editable e intercambio de audio/MIDI/stems. La compatibilidad FLP permanece fuera del alcance acordado. Consultar [arquitectura](architecture.md), [ADR 0003](adr/0003-versioned-projects.md) y [pruebas](testing.md).

## Forma propuesta

Una carpeta portable contendría un manifiesto JSON con extensión .syntet, los recursos del proyecto y las grabaciones. Los nombres de archivos, campos, extensiones auxiliares y versión inicial se definirán en la tarea de esquema; este ejemplo no es una API implementada.

El manifiesto persistente representará identidades y relaciones: instrumentos, patrones, notas, clips, pistas de arreglo, canales de mezcla, parámetros, automatización, tempo, compás y recursos. El estado de plugins se almacenará como recurso opaco con identidad de proveedor y formato; no como un handle de runtime.

El esquema en disco no se deriva de serializar indiscriminadamente la sesión en memoria. Buffers, streams, objetos UI, planes de ejecución y cachés reconstruibles quedan fuera. Preferencias de dispositivo y distribución de ventanas no deberán hacer inutilizable un proyecto en otro equipo.

## Identidad y rutas

- Cada recurso tiene identidad estable, tipo, referencia, tamaño o límites admitidos y datos suficientes para verificar que corresponde al original esperado.
- El modo portable copia recursos dentro del proyecto mediante rutas relativas comprobadas.
- Un modo de referencia externa, si se añade, declara sus dependencias y permite recogerlas en una carpeta portable.
- La resolución de rutas valida traversal, rutas fuera del destino y colisiones antes de copiar o extraer archivos.
- El original de un sample o una toma se conserva. Transformaciones destructivas aparentes producen una fuente derivada identificable.
- Las cachés se pueden reconstruir y limpiar sin perder contenido musical.

Mover una carpeta de proyecto a otra ruta debe conservar notas, relaciones, presets y audio. Una coincidencia de nombre no basta para sustituir un recurso distinto.

## Guardado seguro

El guardado valida el documento y prepara recursos completos antes de publicar un nuevo manifiesto. El temporal se crea en el mismo volumen y se sincroniza según las garantías comprobadas del sistema.

El reemplazo del manifiesto exige una primitiva segura verificada en Windows. No se supone que cualquier rename o movimiento entre volúmenes sea atómico. El último proyecto válido no se trunca para comenzar a escribir el siguiente.

La finalización registra solo recursos terminados. Un fallo de espacio, permisos, antivirus, interrupción o cierre durante el reemplazo conserva una versión válida recuperable y explica qué operación falló. Los temporales propios se identifican para recuperación o limpieza posterior; nunca se eliminan archivos ajenos por una coincidencia de nombre.

Las exportaciones siguen el mismo principio: archivo parcial propio, validación y finalización. Cancelar conserva el proyecto y no presenta una salida incompleta como terminada.

## Autoguardado y recuperación

Autoguardado y guardado explícito son operaciones distintas. El autoguardado trabaja sobre un snapshot coherente fuera del audio y conserva una revisión identificada, con retención y espacio acotados.

Al iniciar tras una interrupción, la aplicación puede ofrecer la revisión recuperable y el archivo original para que el usuario elija. La recuperación no sobrescribe automáticamente el último guardado válido. Grabaciones parciales se presentan como tales con duración recuperada y huecos conocidos.

El historial de deshacer en memoria no sustituye el autoguardado. Su persistencia entre sesiones sería una decisión adicional; la primera versión exige conservar el contenido actual y sus recursos.

## Versiones y migraciones

Se separan versión de aplicación, versión de esquema del proyecto y versión del protocolo de control.

- Una versión anterior admitida se migra de forma explícita y comprobada con fixtures.
- La migración conserva el archivo original hasta que la nueva representación se guarde de forma segura.
- Una versión más nueva no admitida se rechaza con un diagnóstico claro o se abre en un modo limitado decidido expresamente; nunca se guarda descartando datos desconocidos.
- Las migraciones son secuenciales, deterministas y tienen pruebas de sus límites.
- Una estructura inválida, referencia inexistente, tamaño excesivo o número no finito devuelve un error acotado.

Cada cambio de esquema incluye fixture previo, resultado esperado, compatibilidad declarada y procedimiento de recuperación. La migración no altera la música como efecto colateral de un refactor interno.

## Recursos y plugins ausentes

El proyecto debe poder inspeccionarse aunque falten samples o plugins. Las referencias, parámetros y estado opaco se conservan y se informa el contenido afectado. La ausencia no autoriza borrar notas ni reemplazar automáticamente un instrumento por otro incompatible.

Relink valida que el nuevo recurso es aceptable y muestra el cambio; la sustitución es una edición deshacible. Los plugins no se descargan automáticamente al abrir un proyecto.

## Aceptación mínima de persistencia

1. Guardar, cerrar y reabrir conserva el contenido musical y las identidades del proyecto.
2. Copiarlo a otra ruta reproduce el mismo resultado dentro de la tolerancia acordada.
3. Un sample ausente puede relocalizarse sin tocar el último guardado válido.
4. Un guardado interrumpido, disco lleno o error de reemplazo mantiene una versión recuperable.
5. Archivos hostiles o de versión futura no provocan pérdida silenciosa de datos.
6. Migrar fixtures anteriores conserva notas, duración, parámetros y recursos según su contrato.

Referencias de Artcraft: [esquema persistente de PhotoCraft](https://github.com/storytold/photocraft/blob/main/crates/format/src/manifest.rs), [migraciones](https://github.com/storytold/photocraft/blob/main/crates/format/src/migrate.rs). La forma propuesta de Syntet sigue pendiente de implementación y pruebas.
