# Caso 4: Capa a Capa y la tercera impresora

Repositorio de trabajo para el análisis del Caso 4 de Estudio del Trabajo.

## Objetivo
Comparar las alternativas A (continuar con 2 impresoras), B (plantilla de kits) y C (incorporar una tercera impresora), considerando tiempos, despacho de lotes, cumplimiento de la demanda, ocupación de la persona e inversión.

## Estructura
- `datos/tiempos.csv`: observaciones de cronometraje del caso.
- `calculos/validacion_manual.md`: espacio para documentar cálculos y pruebas manuales del checkpoint.
- `diagramas/`: cursograma y diagramas persona–máquinas.
- `app/`: se reservará para la aplicación después de validar el modelo.

## Datos base del cronometraje
Seis observaciones por elemento, valoración R = 100 % y suplemento a = 20 %:
- Preparar lote (pasos 1–3): promedio 60 s; tiempo estándar 72 s.
- Cargar y confirmar (paso 4): promedio 140 s; tiempo estándar 168 s.
- Descargar y trasladar (pasos 6–8): promedio 100 s; tiempo estándar 120 s.
- Inspeccionar y embalar (pasos 9–10): promedio 100 s; tiempo estándar 120 s.

Para la alternativa A: L = 4 min, U = 2 min y F = 2 min. El ciclo automático base es de 16 min y no requiere atención de la persona.

## Reglas de trabajo
1. Completar y revisar los cálculos y cronogramas manuales antes de programar.
2. Registrar las predicciones de las pruebas del checkpoint antes de consultar el anexo de resultados patrón.
3. No asumir que un lote iniciado termina dentro del horizonte: solo contar piezas de lotes cuyo acabado finalice antes de H.
4. No contar el tiempo libre de la persona como ahorro de caja; las horas de personal son fijas.
5. No afirmar optimalidad de una política sin un cronograma verificable.

## Estado
**Preparación inicial del repositorio.** Aún no contiene una aplicación ni resultados de simulación. El código se desarrollará después del checkpoint y de la revisión docente.

## Cómo contribuir
Añade cálculos, datos y diagramas con unidades claras. Documenta supuestos y valida cada resultado con un cronograma persona–máquinas.
