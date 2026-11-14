# Caso 4: Capa a Capa y la tercera impresora

Repositorio de trabajo para el análisis y simulación del Caso 4 de Estudio del Trabajo.

## Aplicación

La aplicación web está en [app/index.html](app/index.html). Es un archivo HTML autónomo: no requiere instalar paquetes ni servicios externos.

**Para ejecutarla:** descarga el archivo `app/index.html` y ábrelo en un navegador moderno. También puede publicarse como sitio estático con GitHub Pages configurando la carpeta `/root` si se mueve el archivo a la raíz, o `/docs` si se copia allí; la carpeta actual `/app` no es una fuente seleccionable directamente en la configuración estándar de Pages.

## Qué permite analizar
- Alternativas A (2 impresoras), B (plantilla de kits, L = 2 min) y C (3 impresoras).
- Horizonte H entre 0 y 120 min, demanda múltiplo de 4 y ciclo automático entre 12 y 20 min.
- Cronograma de actividades manuales, eventos de máquina, lotes iniciados y terminados, piezas faltantes, ocupación de la persona y piezas por hora-persona.
- Comparación incremental de 20 sesiones con 12 u.m. por pieza adicional e inversiones A = 0, B = 360 y C = 1.200 u.m.

## Estructura
- `datos/tiempos.csv`: observaciones de cronometraje del caso.
- `calculos/validacion_manual.md`: predicciones manuales del checkpoint.
- `diagramas/`: espacio para cursograma y diagramas persona–máquinas.
- `app/index.html`: simulador web autónomo.

## Datos base del cronometraje
Seis observaciones por elemento, valoración R = 100 % y suplemento a = 20 %:
- Preparar lote (pasos 1–3): promedio 60 s; tiempo estándar 72 s = 1,2 min.
- Cargar y confirmar (paso 4): promedio 140 s; tiempo estándar 168 s = 2,8 min.
- Descargar y trasladar (pasos 6–8): tiempo estándar 120 s = 2 min.
- Inspeccionar y embalar (pasos 9–10): tiempo estándar 120 s = 2 min.

Para A y C: L = 4 min, U = 2 min y F = 2 min. Para B se modela L = 2 min según el supuesto indicado en el caso. El ciclo automático base es 16 min y no requiere atención.

## Reglas y límites del modelo
1. Una sola persona realiza una actividad manual a la vez.
2. El ciclo automático no ocupa a la persona.
3. Se descuenta la demanda al iniciar un lote y cada lote produce 4 piezas.
4. Se aplica el filtro de inicio del caso: desde el inicio de carga debe caber L + ciclo + U + F dentro de H; en recarga, la comprobación se hace desde el instante posterior a la descarga.
5. El criterio implementado para contar piezas es estricto: el acabado debe terminar **antes** de H. Un acabado exactamente en H no se cuenta.
6. El tiempo libre no se trata como ahorro de nómina; las horas de personal son fijas.
7. La política implementada sigue el recorrido cíclico de máquinas M1–M2–M3 y debe contrastarse con el anexo patrón del docente. No se afirma optimalidad.

## Validación pendiente
Las tres pruebas manuales del archivo `calculos/validacion_manual.md` deben compararse con el anexo patrón liberado por el docente. En particular, confirmar el caso frontera en que un acabado termina exactamente en H. Registrar aquí o en el archivo de validación cualquier corrección acordada.

## Economía
El resultado incremental a 20 sesiones se calcula como:
`20 × 12 u.m. × (piezas de la alternativa − piezas de A) − inversión`.
No es utilidad total ni ahorro de mano de obra.

## Cómo contribuir
Mantén unidades claras, registra las diferencias contra el anexo patrón y conserva los cronogramas manuales como evidencia de validación.
