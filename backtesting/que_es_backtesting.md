# ¿Qué es el backtesting y cuáles son los errores más comunes?

## Introducción

En el mundo del trading algorítmico y cuantitativo, el **backtesting** es uno de los pilares fundamentales para validar cualquier estrategia de inversión. Pero su aparente sencillez esconde múltiples trampas. Si no se aplica con cuidado, el backtesting puede generar una peligrosa ilusión de rentabilidad.

En este artículo explicaremos qué es el backtesting, para qué sirve, por qué es indispensable, y detallaremos los errores más comunes que pueden invalidar completamente sus resultados. El objetivo es ayudarte a construir sistemas más robustos, realistas y resistentes al autoengaño.

***

## ¿Qué es el backtesting?

El **backtesting** es el proceso de simular el comportamiento pasado de una estrategia de trading utilizando datos históricos. La lógica es simple: si una estrategia no habría funcionado en el pasado, es improbable que funcione en el futuro.

Esto implica ejecutar las reglas de decisión de la estrategia (cuándo comprar, cuándo vender) como si hubieran sido aplicadas en tiempo real, pero utilizando datos del pasado. Es una forma de “viajar al pasado” con las reglas que usarías hoy y ver cómo habrían funcionado.

***

## ¿Para qué sirve el backtesting?

* **Validación preliminar**: antes de arriesgar dinero real, permite filtrar estrategias inviables.

* **Comparación objetiva**: ayuda a medir el rendimiento relativo entre diferentes enfoques.

* **Calibración de parámetros**: permite ajustar reglas y límites de riesgo con base en evidencia.

* **Entendimiento de riesgos**: permite ver drawdowns, volatilidad, y comportamiento en distintas fases del mercado.

 **Importante**: un backtest es sólo el **primer filtro**, no una garantía de éxito. Una estrategia puede pasar todos los tests y aun así fallar en condiciones reales. Un ejemplo clásico: estrategias de reversión que funcionaban en mercados de baja volatilidad y colapsan en eventos como 2020.

***

## Errores más comunes en backtesting

A continuación, listamos los errores más frecuentes que pueden invalidar los resultados de un backtest. Estos errores son también comunes en el trabajo de traders profesionales.

***

### 1. **Sesgo de anticipación**

Este sesgo ocurre cuando el sistema utiliza información futura (que no estaba disponible en el momento de la decisión) para ejecutar una operación. Esto puede suceder por errores en los datos (ej: timestamps mal alineados) o por uso indebido de variables como precios de cierre en tiempo real.

**Ejemplos:**

* Utilizar precios máximos y mínimos para operaciones en el mismo día.

* Usar la apertura del día siguiente para definir una entrada el día anterior.

* Seleccionar activos con buena performance reciente sin separar correctamente el set de datos.

**Cómo prevenirlo:**

* Verificar que todas las variables estén disponibles sólo hasta el instante `t`.

* Asegurarse de que la aplicación de backtest no “vea el futuro” al aplicar reglas.

* Implementar funciones de validación que detecten dependencias temporales incorrectas.

***

### 2. **Sesgo de supervivencia**

Este error se produce al usar una base de datos que sólo incluye activos que han sobrevivido hasta hoy. Esto distorsiona los resultados, ya que excluye activos que quebraron o fueron excluidos, que son parte importante del universo de inversión.

**Ejemplo cripto**: analizar sólo monedas que hoy siguen activas, ignorando fracasos como Bitconnect o OneCoin. También sucede con acciones que desaparecieron del índice S&P 500.

**Cómo prevenirlo:**

* Utilizar bases de datos históricas completas, incluyendo activos deslistados o inactivos.

* Verificar la cobertura temporal y de universo en los datasets.

***

### 3. **Sobreajuste (Overfitting / Curve fitting)**

Ocurre cuando la estrategia está tan ajustada a los datos históricos que sólo funciona en ellos. Se ha “aprendido” el ruido y no el patrón real del mercado. Esto es especialmente común cuando se usan demasiados indicadores o reglas.

**Síntoma típico**: una estrategia que rinde espectacular en el pasado pero falla inmediatamente en vivo.

**Cómo prevenirlo:**

* Mantener el modelo lo más simple posible.

* Separar los datos en muestra de entrenamiento y validación.

* Utilizar técnicas como walk-forward y validación cruzada.

***

### 4. **Sesgo de selección**

Este sesgo aparece cuando probamos muchas estrategias diferentes y elegimos la mejor sin tener en cuenta la probabilidad de obtener un buen resultado por puro azar. En realidad, estamos seleccionando el “mejor error”.

**Ejemplo real**: probar 50 combinaciones de medias móviles y elegir la que dio mejor Sharpe ratio.

**Cómo prevenirlo:**

* Aplicar pruebas estadísticas (como p-values o simulaciones Monte Carlo).

* Registrar cuántas estrategias fueron evaluadas antes de seleccionar una.

* Utilizar validación cruzada con distintas ventanas temporales.

***

### 5. **Ignorar costos reales de operación**

Muchos backtests olvidan incorporar:

* Comisiones

* Deslizamientos (slippage)

* Liquidez disponible

* Requerimientos de margen

Esto puede convertir una estrategia rentable en papel en una pérdida en la práctica.

**Cómo prevenirlo:**

* Incluir todos los costos en el modelo.

* Simular condiciones realistas de ejecución.

* Incorporar capas de simulación de ejecución (market vs limit orders).

***

### 6. **Elección inadecuada del periodo de prueba**

El rendimiento de una estrategia puede variar enormemente según el periodo elegido. Usar sólo datos de mercados alcistas o bajistas puede crear una falsa percepción de estabilidad.

**Cómo prevenirlo:**

* Usar periodos amplios y representativos.

* Separar datos en segmentos in-sample y out-of-sample.

* Realizar análisis de robustez en distintos regímenes de mercado.

* Combinar con análisis de estrés y simulación de escenarios extremos.

***

## Conclusión

El backtesting no es un oráculo ni un filtro mágico. Es una herramienta poderosa, pero fácilmente manipulable (intencional o accidentalmente) si no se aplica con rigurosidad. Identificar y evitar los errores más comunes es esencial para que el backtesting cumpla su verdadero propósito: **reducir la incertidumbre** antes de operar en el mundo real.
