# Simulador del Caso 4

## Ejecutar
Abre `index.html` en Chrome, Edge, Firefox o Safari reciente. No requiere servidor, dependencias, conexión a internet ni API.

## Controles
- Alternativa A, B o C.
- Horizonte H: 0 a 120 minutos.
- Demanda: entero no negativo múltiplo de 4.
- Ciclo automático: 12 a 20 minutos.

## Salidas
Cronograma de tareas manuales, eventos de máquina, lotes iniciados/terminados, piezas terminadas/faltantes, ocupación manual, utilización de la persona, piezas por hora-persona y comparación económica incremental de 20 sesiones.

## Convenciones
- A y C: L=4, U=2, F=2 min.
- B: L=2, U=2, F=2 min.
- El ciclo automático por defecto es 16 min.
- El acabado debe terminar estrictamente antes de H para contar el lote.
- La persona no realiza tareas manuales simultáneas.
- El filtro de inicio y recarga se aplica como se documenta en el README raíz.

## Validación
Comparar las pruebas i, ii y iii del checkpoint con el anexo patrón del docente. No considerar el simulador validado académicamente hasta documentar ese contraste.
