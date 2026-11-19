# Caso 1 · La "alta confirmación" que no lo era

**La idea:** subir el riesgo solo en las señales "de alta confirmación" para hacer crecer más rápido una cuenta pequeña.

## Lo que encontró la investigación
Con unas 760 operaciones históricas (2018-2026) de varios módulos de entrada en la apertura de Nueva York salieron dos candidatas:

- **Segunda señal del día en la misma dirección que otro módulo:** rendía unas 4 veces más por operación y el acierto subía del 52 % al 67 %.
- **Contexto de premercado a favor** en el módulo principal: unas 7 veces más por operación, y positivo en 8 de 9 años.

Una simulación de un año decía que subir el riesgo en esas señales mejoraba el saldo final casi sin aumentar la caída. Parecía ideal.

## Lo que encontró la auditoría (veredicto: NO APTO)
1. **Miraba el futuro.** Más de la mitad de las "segundas señales" eran en realidad la *primera* del día. En el momento de entrar no se podía saber que vendría otra. Lo que se medía era "días de tendencia", algo que no se puede aprovechar en tiempo real.
2. **Bien medida, se deshace.** Contando solo la segunda señal y las siguientes, el efecto bajaba al 11 % de las señales y dejaba de ser significativo.
3. **Comparación inflada.** La mejora del premercado se medía contra un grupo que incluía casos que ya se filtraban. Frente al grupo comparable, la diferencia no era significativa.
4. **Demasiadas pruebas.** Con unas 50 pruebas por módulo, nada sobrevivía a la corrección por pruebas múltiples.
5. **No se podía ejecutar.** Con lote mínimo, el siguiente escalón de riesgo era el doble del lote, no un +2 %.

## Lección
Una regla que "duplica" el rendimiento en un backtest debe despertar **sospecha, no entusiasmo**. La decisión final fue **riesgo plano** en todas las señales.
