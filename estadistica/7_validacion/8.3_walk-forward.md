# Walk-Forward Analysis: validar una estrategia fuera del backtest

El **Walk-Forward Analysis** (WFA) es un método de validación **out-of-sample** que consiste en **entrenar una estrategia sobre un período inicial y testearla en un período siguiente inmediato**, repitiendo este proceso en ventanas móviles.

Su propósito es simular cómo se comportaría la estrategia en un entorno real, donde las decisiones se toman solo con datos pasados y **no se optimiza sobre lo que ya ocurrió**.

Es un paso más exigente que la validación cruzada: **preserva el orden temporal** y evita el riesgo de sobreajuste por backtest intensivo.

***

## Aplicación al trading cuantitativo

El WFA permite responder la pregunta clave:

¿Cómo se comporta mi estrategia cuando ya no tiene la respuesta en la parte de atrás del libro?

En Cuants, se lo utiliza para:

* Evaluar **consistencia y estabilidad fuera del conjunto de entrenamiento**

* Comparar estrategias que rinden bien en el pasado pero fallan al “caminar hacia adelante”

* Exponer sistemas que solo funcionan bajo condiciones de optimización muy específicas

***

## Esquema básico del método

1. **Dividir la serie temporal en bloques solapados o secuenciales**

2. Para cada bloque:

   * **Entrenar** (optimizar parámetros o calibrar) en la ventana A

   * **Testear** (sin ajustar nada) en la ventana B

3. Repetir el proceso moviendo la ventana hacia adelante

4. Evaluar resultados agregados del out-of-sample

***

## Ejemplo aplicado (pseudocódigo)

```python
# Supongamos una serie de retornos diarios con 1000 datos
# Ventana de entrenamiento: 250 días (1 año)
# Ventana de testeo: 50 días

train_size = 250
test_size = 50

for start in range(0, len(datos) - train_size - test_size, test_size):
    train_data = datos[start : start + train_size]
    test_data  = datos[start + train_size : start + train_size + test_size]

    modelo = entrenar_modelo(train_data)
    resultados = aplicar_modelo(modelo, test_data)
    guardar_metricas(resultados)
```
Se puede aplicar con sistemas técnicos, ML, reglas fijas, etc.

***

## Ventajas del Walk-Forward

* **Simula la operativa real**, sin “ver el futuro”

* Evalúa si los parámetros óptimos son estables

* Expone si la estrategia solo funcionaba en un régimen de mercado específico

* Recolecta resultados reales de performance out-of-sample

***

## Riesgos y malentendidos

* Si no se guarda independencia entre bloques, **puede haber fuga de información**

* Si los parámetros se recalibran en cada bloque, **se debe tener cuidado con la adaptabilidad artificial**

* No es una solución mágica: **si el modelo es frágil, WFA lo revela, no lo corrige**

***
