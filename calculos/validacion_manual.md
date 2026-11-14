# Validación manual — checkpoint

> Predicción manual desarrollada a partir de las reglas del Caso 4. Debe conservarse como versión previa al anexo patrón y revisarse con el docente antes de programar.

## 1. Tiempos estándar

Seis observaciones por elemento, valoración R = 100 % y suplemento a = 20 %:

| Elemento | Promedio | TN | TE |
|---|---:|---:|---:|
| Preparar lote (pasos 1–3) | 60 s | 60 s | 72 s = 1,2 min |
| Cargar y confirmar (paso 4) | 140 s | 140 s | 168 s = 2,8 min |
| Descargar (pasos 6–8) | 100 s | 100 s | 120 s = 2 min |
| Inspeccionar y embalar (pasos 9–10) | 100 s | 100 s | 120 s = 2 min |

Para A:
- **L = preparación + carga = 1,2 + 2,8 = 4 min** de ocupación manual por lote.
- **U = 2 min** de descarga y traslado.
- **F = 2 min** de inspección y embalaje.
- Ciclo automático = **16 min**, sin atención de la persona.
- Contenido manual por lote = L + U + F = **8 min**.
- Tiempo de un lote aislado = L + 16 + U + F = **24 min** (no significa 24 min de trabajo manual).

La preparación y la carga se muestran por separado para hacer visible cuándo la impresora queda ocupada: preparación 1,2 min fuera de máquina; carga 2,8 min con la máquina; luego ciclo automático de 16 min.

## 2. Convención usada para las pruebas

- La persona ejecuta una sola actividad manual a la vez.
- Cada lote requiere primero preparación (1,2 min) y carga (2,8 min); el ciclo automático de 16 min comienza al terminar la carga.
- Al terminar el ciclo, descarga/traslado U (2 min) y acabado F (2 min) son consecutivos. El acabado no ocupa impresora.
- Se aplica la secuencia de despacho M1–M2–M1…, esperando cuando la máquina visitada aún imprime.
- La demanda se descuenta al iniciar cada lote.
- **Criterio literal del enunciado:** se cuentan lotes acabados antes de H. Por tanto, un acabado que termina exactamente en H se señala como límite, pero no se cuenta en el resultado estricto. Confirmar con el docente si en el anexo patrón se interpreta “dentro de H” como inclusivo.

## 3. Pruebas manuales — alternativa A, ciclo 16 min

### Prueba i — H = 24 min; demanda = 4 piezas (1 lote)

| Tiempo | Persona | M1 | Resultado |
|---|---|---|---|
| 0–1,2 | Preparar lote 1 | Libre | Preparación |
| 1,2–4 | Cargar lote 1 | Carga | M1 inicia ciclo al min 4 |
| 4–20 | Espera de impresión | Automático | Ciclo M1 |
| 20–22 | Descargar/trasladar lote 1 (U) | Descarga | Lote fuera de máquina |
| 22–24 | Inspeccionar/embalar (F) | Libre | Acabado termina exactamente en H |

- Lotes iniciados: **1**.
- Lotes terminados estrictamente antes de H: **0**; el único lote termina en t = 24, justo en el límite.
- Piezas contadas: **0**; faltantes bajo el criterio estricto: **4**.
- Ocupación manual: **8 min** (4 min L + 2 min U + 2 min F).
- Si el docente confirma que la igualdad con H sí cuenta, el resultado alternativo sería 1 lote = 4 piezas terminadas.

### Prueba ii — H = 23 min; demanda = 4 piezas (1 lote)

| Tiempo | Persona | M1 | Resultado |
|---|---|---|---|
| 0–1,2 | Preparar lote 1 | Libre | Preparación |
| 1,2–4 | Cargar lote 1 | Carga | M1 inicia ciclo al min 4 |
| 4–20 | Espera de impresión | Automático | Ciclo M1 |
| 20–22 | Descargar/trasladar lote 1 (U) | Descarga | Lote fuera de máquina |
| 22–24 | Inspeccionar/embalar (F) | Libre | Termina después de H |

- Lotes iniciados: **1**.
- Lotes terminados antes de H: **0**.
- Piezas contadas: **0**; faltantes: **4**.
- Ocupación manual ejecutada dentro de la ventana: **7 min** (L = 4 min y U = 2 min, más 1 min de F entre t = 22 y H = 23). El bloque F completo requiere 2 min y termina en t = 24; si se reporta trabajo estándar comprometido del lote, son 8 min, pero solo 7 min transcurren antes del cierre.

### Prueba iii — H = 30 min; demanda = 8 piezas (2 lotes)

La carga inicial sigue el orden M1 y después M2.

| Tiempo | Persona | M1 | M2 | Resultado |
|---|---|---|---|---|
| 0–1,2 | Preparar lote 1 | Libre | Libre | Preparación lote 1 |
| 1,2–4 | Cargar lote 1 | Carga | Libre | Ciclo M1: 4–20 |
| 4–5,2 | Preparar lote 2 | Automático | Libre | Preparación lote 2 |
| 5,2–8 | Cargar lote 2 | Automático | Carga | Ciclo M2: 8–24 |
| 8–20 | Esperar fin de M1 | Automático | Automático | No hay trabajo manual disponible |
| 20–22 | Descargar/trasladar lote 1 (U) | Descarga | Automático | Lote 1 fuera de máquina |
| 22–24 | Acabar lote 1 (F) | Libre | Automático | Lote 1 terminado en t = 24 |
| 24–26 | Descargar/trasladar lote 2 (U) | Libre | Descarga | Lote 2 fuera de máquina |
| 26–28 | Acabar lote 2 (F) | Libre | Libre | Lote 2 terminado en t = 28 |
| 28–30 | Sin trabajo pendiente | Libre | Libre | Fin de ventana |

- Lotes iniciados: **2**.
- Lotes terminados antes de H: **2**.
- Piezas terminadas: **8**; faltantes: **0**.
- Ocupación manual: **16 min** (dos lotes × 8 min).
- Último acabado: **t = 28 min**.

## 4. Resumen de resultados esperados

| Prueba | Lotes iniciados | Lotes terminados (criterio estricto) | Piezas terminadas | Faltantes | Ocupación manual estándar comprometida |
|---|---:|---:|---:|---:|---:|
| i: H=24, D=4 | 1 | 0* | 0* | 4* | 8 min |
| ii: H=23, D=4 | 1 | 0 | 0 | 4 | 8 min (7 min transcurridos dentro de H) |
| iii: H=30, D=8 | 2 | 2 | 8 | 0 | 16 min |

* Caso de frontera: el lote termina exactamente en H = 24. Si la regla de evaluación admite igualdad, la prueba i entrega 4 piezas y tiene 0 faltantes. La frase del caso “antes de H” se ha aplicado literalmente en la columna principal.

## 5. Observaciones para la revisión docente

1. Confirmar si un lote cuyo acabado termina exactamente en H se considera entregado. El texto del caso usa “antes de H”; por eso se separó el caso de frontera.
2. Confirmar que la ocupación manual se reporte como estándar comprometido por lote (8 min) y, cuando el horizonte corta una actividad, también como minutos efectivamente transcurridos dentro de H.
3. Estas tres pruebas son únicamente el checkpoint de alternativa A. No constituyen resultados de la comparación completa A/B/C ni una demostración de optimalidad de la política.

## 6. Registro del equipo

- Fecha:
- Integrantes y roles:
- Predicción inicial del equipo:
- Procedimiento y cronograma elaborado:
- Observaciones de la revisión docente:
- Contraste con el anexo patrón:
- Diferencias y correcciones:
