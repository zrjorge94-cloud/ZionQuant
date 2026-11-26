# Caso 2 · El indicador que miraba el futuro

**El hallazgo inicial:** las señales con un indicador de un marco temporal mayor "en contra" perdían de media −0,11 R por operación. Parecía un filtro perfecto para *no entrar*.

## El error
El indicador se calculaba con una vela de un marco mayor que **todavía no había cerrado** en el momento de entrar. Es decir, usaba precio que aún no existía. El mismo fallo afectaba a otros indicadores del estudio.

## Con los datos bien medidos
Usando la **última vela cerrada antes de la entrada**:

| | Con el indicador "en contra" | Resto |
|---|---|---|
| Resultado medio | **+0,14 R/op** | +0,24 R/op |
| ¿Gana al azar? | No (p = 0,12; 11 variantes probadas) | — |

Las señales "malas" eran **ganadoras**. Aplicar el filtro habría eliminado 268 operaciones y unos +38 R de beneficio, y la caída máxima habría empeorado.

## Lección
Antes de creer un resultado pregúntate: **¿este dato existía en el momento exacto de entrar?** En marcos temporales mayores que el de la entrada (H1, H4, D1), usa siempre la vela ya cerrada.
