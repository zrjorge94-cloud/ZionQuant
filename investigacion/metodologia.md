# Metodología: cómo pruebo una idea antes de arriesgar dinero

Separo dos papeles: quien **investiga** una idea no puede ser quien la **aprueba**. Cada estudio pasa por una auditoría independiente cuyo trabajo es intentar tumbarlo.

## 1. Hipótesis que se pueda tumbar
Una frase que pueda resultar falsa, con su **mecanismo**: por qué debería funcionar y quién estaría al otro lado de la operación.

## 2. Registro previo, antes de mirar
Reglas exactas, pocas variantes declaradas y qué resultado la confirmaría o la tumbaría. Todo se escribe **con fecha antes de ver los datos**. Lo que aparece mirando se trata como hipótesis nueva, nunca como conclusión.

## 3. Datos separados
Periodo de **diseño**, de **validación** y un **holdout** que no se toca hasta el final, o un walk-forward. Si es posible, otro bróker para comprobar que el efecto no depende del feed.

## 4. Rival al azar
Mismas fechas, mismo número de compras y ventas, mismo riesgo y misma gestión, pero entrando al azar, con más de 1.000 repeticiones. Si la regla no gana claramente al azar, la entrada no aporta.

## 5. Costes altos y estabilidad
Spread y deslizamiento pesimistas. Resultados **por año** y por periodo: una ventaja que solo existe en uno o dos años no es una ventaja.

## 6. Pruebas múltiples
Si pruebo 50 variantes, alguna saldrá "significativa" por azar. Corrijo por el número de pruebas (Holm, Benjamini-Hochberg o el ratio de Sharpe deflactado).

## 7. Sin mirar adelante
Cada dato tiene que existir **en el momento de entrar**: la última vela *cerrada*, no la que está en curso. Es el error más común y el más caro (ver el [caso 2](caso_rsi_mira_adelante.md)).

## 8. Auditoría independiente
El auditor rehace los cálculos y da un veredicto: **APTO / CON RESERVAS / NO APTO**. Ese veredicto es el criterio con el que decido qué va a dinero real, pero **no siempre se cumple**. Cuando decido operar en real algo que no tiene veredicto APTO, lo trato como una **excepción**: la dejo escrita con fecha, motivo y riesgo asumido, y la publico.

**Estado a 25-nov-2026 (cuenta real pequeña, 3 sistemas):**

| Sistema | Situación |
|---|---|
| Uno | APTO CON RESERVAS |
| Otro | Calificado como «solo forward / validación adicional». Pasó a real por decisión propia, para validar su ejecución con el lote más pequeño posible |
| El tercero | Todavía sin auditoría formal de sobreajuste |

Los tres son excepciones parciales a mi propia regla. Las asumo sabiendo que la cuenta es pequeña y que su objetivo es validar la ejecución en real, no crecer.

## 9. Congelar y medir en vivo
Lo que pasa a operación se congela: nada de retocar parámetros por una mala racha. La congelación actual dura **hasta el 14-feb-2027**. En vivo comparo lo esperado con lo real, módulo a módulo.

**Excepción registrada:** el 21-nov-2026 cambié qué módulos operan en la cuenta real, antes de empezar a operar con sistemas en ella. Cualquier otra excepción tiene que quedar escrita y con fecha antes de aplicarse.
