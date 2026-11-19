# Caso 2 · El indicador que miraba el futuro

**El hallazgo inicial:** las señales con el RSI de 1 hora "en contra" perdían de media −0,11 R por operación. Parecía un filtro perfecto para *no entrar*.

## El error
La entrada era a las 9:30, pero el RSI se calculaba con la vela de 1 hora de las 9:00, **que cierra a las 9:59**. Es decir, usaba 30 minutos de precio que todavía no existían al entrar. El mismo fallo afectaba a otros dos indicadores del estudio (una media móvil de 3 horas y el ADX).

## Con los datos bien medidos
Usando la **última vela cerrada antes de la entrada**:

| | Con el RSI "en contra" | Resto |
|---|---|---|
| Resultado medio | **+0,14 R/op** | +0,24 R/op |
| ¿Gana al azar? | No (p = 0,12; 11 variantes probadas) | — |

Las señales "malas" eran **ganadoras**. Aplicar el filtro habría eliminado 268 operaciones y unos +38 R de beneficio, y la caída máxima habría empeorado.

## Lección
Antes de creer un resultado pregúntate: **¿este dato existía en el momento exacto de entrar?** En marcos temporales mayores que el de la entrada (H1, H4, D1), usa siempre la vela ya cerrada.
