# Riesgo en una cuenta pequeña: qué esperar antes de empezar

Antes de operar en real con una cuenta de ~50 USD a **lote mínimo fijo**, simulé qué rachas y caídas son *normales*. El objetivo: no abandonar el sistema en una racha que en realidad era esperable.

**Supuestos:** varios módulos de entrada en el Nasdaq (unas 90-170 operaciones al año), operaciones históricas de 2018-2026 remuestreadas por semanas y 2.000 años simulados. Con lote mínimo cada operación arriesga entre un 2 % y un 7 % de la cuenta según la distancia al stop, y ese porcentaje baja solo a medida que la cuenta crece.

## Un año simulado
| | Mediana | Año malo (1 de cada 10) |
|---|---|---|
| Caída desde el máximo | −18 % | −32 % (−50 % en 1 de cada 100) |
| Peor semana | −12 % | — |
| Semanas negativas seguidas | 3 | 5 |
| Meses negativos seguidos | 2 | 3 |
| Terminar el año en pérdida | 2-3 % de probabilidad | — |

En el backtest del año en curso, la peor racha fue de **8 pérdidas seguidas (≈ −28 % de la cuenta)**, y hubo unas 10 rachas de 4 o más pérdidas en el año.

## Lo que me llevo
- Con un acierto de ~42-48 %, perder 4-5 veces seguidas es **rutina**, no una señal de que el sistema se rompió.
- Lo que rompe una cuenta pequeña no suele ser la estrategia, sino **cambiar las reglas en mitad de la racha**: subir el lote para recuperar o saltarse señales.
- Escribir estos rangos **antes de empezar** permite comparar la racha real con lo esperado, en vez de con el miedo.
