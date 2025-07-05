# Sharpe Ratio

**Cómo evaluar si tu estrategia compensa el riesgo que toma**

***

## ¿Qué es el Sharpe ratio?

El **Sharpe ratio** es una métrica clásica del análisis cuantitativo. Mide la rentabilidad **ajustada por el riesgo** de una estrategia o activo. No se trata solo de cuánto ganás, sino de **cuánto ganás por cada unidad de riesgo que asumís**.

$$Sharpe Ratio = \frac {R−R_f}{\sigma}$$

**Donde:**

* $R$ es el **retorno promedio** de la estrategia

* $R_f$​ es el **retorno libre de riesgo** (puede ser 0 si no se ajusta)

* $\sigma$ es la **desviación estándar** de los retornos

 Si el Sharpe ratio es 1.5, significa que por cada unidad de riesgo, ganás 1.5 unidades de retorno. Si es menor a 1, la estrategia puede ser ineficiente o inestable.

***

**Aplicación al trading cuantitativo**

El Sharpe Ratio permite comparar estrategias más allá de sus retornos brutos. Una estrategia puede parecer rentable, pero si lo hace con alta volatilidad, su Sharpe Ratio será bajo. Esto penaliza estrategias que logran ganancias a costa de grandes fluctuaciones. En algoritmos de trading, donde se prueban múltiples modelos, esta métrica ayuda a seleccionar estrategias más estables y sostenibles.

Cuants utiliza el Sharpe Ratio no como fin en sí mismo, sino como una medida auxiliar para explorar la consistencia de un sistema, detectar sobreajuste o evaluar si un incremento de retorno se justifica por unidad de riesgo asumido.

## ¿Cómo se calcula?

```python
import numpy as np

def sharpe_ratio(returns, risk_free_rate=0):
    excess_returns = returns - risk_free_rate
    return np.mean(excess_returns) / np.std(excess_returns)

# Simulación simple
np.random.seed(42)
daily_returns = np.random.normal(loc=0.001, scale=0.02, size=252)  # 252 días
sharpe = sharpe_ratio(daily_returns)
print(f"Sharpe Ratio diario: {sharpe:.2f}")
print(f"Sharpe Ratio anualizado: {sharpe * np.sqrt(252):.2f}")

```

Si querés ajustarlo por una tasa libre de riesgo (por ejemplo, 3% anual), debés restar esa tasa ajustada al periodo del retorno.

## ¿Por qué importa en trading cuantitativo?

* Compara estrategias con diferente volatilidad: dos estrategias con la misma rentabilidad pueden tener riesgos muy distintos.

* Ayuda a seleccionar entre alternativas con diferente perfil de riesgo-retorno.

* Es fundamental en optimización de portafolios y estrategias.

### Ejemplo práctico

|Estrategia	|Retorno medio diario	|Desviación	|Sharpe |
|----------|-------------------|----------|-------|
|A	|0.10%	|1.00%	|0.10 |
|B	|0.08%	|0.40%	|0.20|

Aunque A tiene mayor rentabilidad, B es más eficiente por unidad de riesgo.

### Limitaciones

* Asume retornos normalmente distribuidos

* No diferencia entre riesgo "bueno" (ganancias inesperadas) y "malo" (pérdidas)

* Puede ser engañoso si el rendimiento no es estable o tiene colas pesadas

El Sharpe ratio no mide cuánto ganás. Mide si vale la pena lo que estás arriesgando para ganarlo.

