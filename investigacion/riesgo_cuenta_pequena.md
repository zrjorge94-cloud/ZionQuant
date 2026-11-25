# Riesgo en una cuenta pequeña: qué esperar

> **Fecha de corte: 25-nov-2026.** Esta versión sustituye a la del 18-nov-2026, que describía una configuración anterior (5 módulos) y ya no está vigente. Esa versión sigue en el historial de Git; sus cifras no se volvieron a reproducir en esta revisión.

## Qué configuración describe
Una cuenta real pequeña (capital inicial de unos 51 USD) con **3 sistemas de apertura del Nasdaq**, desde el 21-nov-2026.
- El lote varía según el sistema, entre 0,01 y 0,03.
- Los sistemas y sus parámetros son privados.

## Riesgo de una operación (no es el riesgo total)
- Con una cuenta pequeña, los tamaños mínimos disponibles limitan la capacidad de ajustar el riesgo monetario. El porcentaje expuesto depende del lote utilizado, la distancia al stop y el saldo disponible en ese momento.
- **Ejemplo real:** una entrada del 24-nov-2026 tenía un riesgo calculado de **7,43 USD** hasta su stop. El porcentaje respecto al saldo de ese momento no se publica, porque el denominador no está documentado en la fuente consultada.
- Eso es **una operación**. El riesgo simultáneo de los 3 sistemas abiertos a la vez todavía **no está medido**, así que no lo publico.
- En el backtest, la mayor pérdida de una sola operación fue de **12,51 USD**, el 25 % de 50 USD.

## Lo que dice el backtest
Probador de MetaTrader 5 con ticks reales del bróker, del 2-ene al 16-nov-2026. Es un solo año de datos y mide resultados **históricos**.

| Métrica | Valor |
|---|---|
| Operaciones | 272 |
| Acierto | 47,8 % |
| Factor de beneficio | 1,44 |
| Caída máxima (balance cerrado, desde 50 USD) | −24,3 % |
| Peor racha de pérdidas seguidas | 9 |
| Peor día · peor semana | −13,48 USD · −16,61 USD (27 % y 33 % de 50 USD) |

## Simulación de caídas (Monte Carlo)
Estima escenarios **condicionados por sus supuestos**; no es una predicción.

**Método:**
- 20.000 trayectorias que remuestrean bloques de días hábiles reales del backtest.
- Cada trayectoria parte de 50 USD.
- Cada operación conserva su resultado en USD.
- La caída se mide desde el máximo de la cuenta.

| Escenario | Probabilidad de caer un 45 % o más desde el máximo |
|---|---|
| Hasta el 14-feb-2027 (~58 días hábiles) | 24,8 % |
| 1 año (bloques de 5 días) | 39,1 % |
| 1 año (bloques de 20 días) | 25,8 % |
| 1 año, con la ventaja reducida a la mitad* | 67,3 % |

\* **Cómo se reduce la ventaja:**
- El backtest ganó de media 0,438 USD por operación.
- En este escenario se restan 0,219 USD (la mitad) al resultado de **cada** operación, ganadora o perdedora, antes de simular.
- Es un **deterioro mecánico de la expectativa**, no una simulación completa del deterioro de una estrategia.

**Cómo leer estas cifras:**
- El 39 % **no** es la probabilidad de perder la cuenta. Es la de pasar, en algún momento del año, por una caída del 45 % desde el máximo.
- En la simulación sin aplicar la regla de parada, terminar con 5 USD o menos ocurre en el 5,9 % de las trayectorias. Este resultado es hipotético y no representa el escenario de una cuenta que respeta la regla de detenerse al alcanzar un drawdown del 45 %.
- Las cifras son **optimistas**:
  - los sistemas se eligieron mirando los resultados de 2026 (selección retrospectiva);
  - no incluyen las pérdidas flotantes;
  - se basan en un solo año.
- La realidad puede ser peor.

**Limitaciones adicionales del modelo:**
- La simulación no reproduce la activación de la regla de parada por drawdown del 45 %.
- La simulación no reproduce los mecanismos internos de reducción de riesgo de los sistemas ni las posibles diferencias entre los lotes ejecutados en el backtest y los que podrían ejecutarse en condiciones reales.
- El escenario de ventaja reducida a la mitad resta una cantidad fija a cada operación. No representa todos los posibles deterioros de una estrategia, como cambios en el acierto o en la distribución de las rachas.
- El remuestreo utiliza únicamente los días disponibles en el período estudiado. No contempla condiciones de mercado que no estén representadas en esa muestra.

## Regla escrita antes de seguir
Si la cuenta cae un **45 % desde su máximo**, se para. Lo decidí el 24-nov-2026, antes de que ocurra.

## Lo que me llevo
- El backtest mide el pasado, la simulación estima escenarios bajo supuestos, y la operativa real **todavía tiene que demostrar** que reproduce esos resultados.
- Con un acierto cercano al 48 %, perder 4 o 5 veces seguidas es **rutina**, no una señal de que el sistema se rompió.
- Con una cuenta tan pequeña, el riesgo es alto **por diseño**. Es una cuenta para validar la ejecución en real, no para crecer rápido.
- Lo que rompe una cuenta pequeña no suele ser la estrategia, sino **cambiar las reglas en mitad de la racha**.
- Escribir estos rangos **antes** me permite comparar la racha real con lo esperado, y no con el miedo.
