# ADR 0002: documento, edición y ejecución separados

Fecha: 2026-10-20. Estado: diseño adoptado; viabilidad del runtime pendiente de M1.

## Contexto

El editor, la grabación, la exportación y los agentes necesitan una semántica musical común. Un callback dependiente del lock del proyecto, la UI o el disco tendría trabajo impredecible. Además, deshacer una edición no es reiniciar el estado de reproducción.

## Decisión

Mantener un documento autoritativo independiente de UI y dispositivos. Las interfaces utilizan operaciones tipadas y transacciones. La sesión prepara planes y recursos fuera del callback y publica mensajes acotados o planes de ejecución listos.

El callback procesa la señal y devuelve recursos retirados al control; no realiza disco, serialización, asignaciones en régimen estable ni liberaciones grandes. El mismo render musical y DSP sirve a escucha y exportación.

## Alternativas consideradas

Compartir un documento mutable con locks simplifica un prototipo, pero no cumple la propiedad temporal requerida. Procesar comandos JSON directamente en audio mezcla fronteras de confianza y trabajo no acotado. Duplicar un motor para exportación permitiría divergencias musicales y de automatización.

## Consecuencias

Documento, estado DSP, cachés y vista tienen dueños distintos. La compilación de planes y su retirada necesitan ciclo de vida probado. Los parámetros usan IDs estables y metadatos independientes de la UI. El motor debe aceptar bloques efectivos distintos y conservar semántica en seek, bucle y cancelación.

## Validación pendiente

Detectar asignaciones y bloqueos indebidos, probar saturación de colas, recursos retirados y ediciones simultáneas con reproducción. Comparar render por bloques y offline; medir captura alineada y deriva. CPAL/WASAPI es una propuesta de adaptador, no una conclusión de estas pruebas.

Referencias: [arquitectura](../architecture.md), [motor de audio](../audio-engine.md), [SoundCraft AGENTS](https://github.com/storytold/soundcraft/blob/main/AGENTS.md).
