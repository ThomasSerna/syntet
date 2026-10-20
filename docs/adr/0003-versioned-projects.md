# ADR 0003: persistencia independiente y recuperable

Fecha: 2026-10-20. Estado: principios adoptados; contenedor y esquema concretos propuestos.

## Contexto

El proyecto debe conservar edición musical, recursos y futuro estado de plugins durante la evolución de Syntet. Serializar el objeto completo de runtime acoplaría archivos a buffers, UI y dispositivos. Un refactor interno no debe romper proyectos guardados.

## Decisión

Definir un esquema persistente explícito con versión propia, separado de la aplicación y del protocolo de control. Mantener IDs estables, migraciones probadas y recuperación ante fallos. Rechazar versiones no admitidas sin descartar datos desconocidos.

La propuesta inicial es una carpeta portable con manifiesto JSON .syntet y recursos propios. La extensión final, campos, límites y convención de carpetas se cerrarán en la tarea de formato antes de implementarse.

## Alternativas consideradas

Persistir directamente la sesión en memoria evita un mapeo inicial, pero impide controlar compatibilidad y datos efímeros. Un contenedor comprimido único simplifica distribución, pero complica escritura y recuperación de tomas activas; podrá evaluarse como empaquetado posterior sin cambiar el modelo musical.

## Consecuencias

Guardar requiere validar y preparar recursos antes de reemplazar el manifiesto. El mecanismo seguro de reemplazo se verificará en Windows. Autoguardado y recuperación conservarán una versión válida; recursos ausentes y plugins fallidos preservarán referencias y estado.

## Validación pendiente

Round-trip de proyecto, cambio de ruta, recursos ausentes, permisos y disco lleno; interrupciones durante guardado y captura; migraciones desde fixtures y rechazo de archivos futuros. La elección final del contenedor queda condicionada a estas necesidades, no a una API ya existente.

Referencias: [formato del proyecto](../project-format.md), [manifest de PhotoCraft](https://github.com/storytold/photocraft/blob/main/crates/format/src/manifest.rs), [migraciones de PhotoCraft](https://github.com/storytold/photocraft/blob/main/crates/format/src/migrate.rs).
