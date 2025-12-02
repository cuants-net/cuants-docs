
# Regresión de Poisson

La regresión de Poisson es una herramienta estadística esencial cuando queremos modelar eventos **contables**: situaciones donde el resultado es un número entero no negativo (0, 1, 2, 3, ...), como la **cantidad de veces que ocurre algo**.

***

## ¿Para qué sirve?

Sirve para responder preguntas como:

* ¿Qué condiciones aumentan o reducen la **cantidad de veces** que un patrón técnico se activa?
* ¿Cuántos falsos rompimientos ocurren por día en una zona de liquidez?
* ¿Qué variables influyen en la **frecuencia de aparición** de una señal discrecional?

Es decir: **modelamos frecuencias**, no proporciones ni probabilidades directas. Es útil cuando hay **conteos** y nos interesa saber **cómo cambia la media** del número de eventos esperados según ciertas variables.

***

## Ejemplo aplicado

Supongamos que analizamos un gráfico horario y contamos, para cada día, cuántas veces se activa un patrón de reversión en el orderbook.

Registramos para cada día:

* **Volumen total del día**
* **Volatilidad intradía**
* **¿Cuántas veces se activó el patrón de reversión?**

Tendremos una tabla como la siguiente:

| Día | Volumen | Volatilidad | Patrones activados |
|-----|---------|-------------|---------------------|
| 1   |  15k    |  1.3        | 3                   |
| 2   |  8k     |  2.2        | 0                   |
| 3   |  12k    |  1.9        | 1                   |
| ... |  ...    |  ...        | ...                 |

Queremos entender:  
**¿Qué variables influyen en la frecuencia esperada de activaciones del patrón?**

***

## ¿Cómo se construye el modelo?

1. Primero construimos una **combinación lineal**:
```
ηᵢ = β₀ + β₁·x₁ᵢ + β₂·x₂ᵢ + ...
```

2. Luego aplicamos la **función exponencial**:
```
μᵢ = exp(ηᵢ)
```

Este `μᵢ` representa la **media esperada de eventos** (por ejemplo, activaciones del patrón) para la observación `i`.

***

## Interpretación de los coeficientes

Cada `βⱼ` representa el cambio proporcional en la media `μ` por cada unidad de cambio en `xⱼ`:

* Si `β₁ = 0.05` → `exp(0.05) ≈ 1.05`  
  ➞ Aumento del 5% en la frecuencia por unidad adicional en `x₁`

> **Regla de oro**:  
> El coeficiente `βⱼ` se interpreta como el **cambio porcentual** en la media del conteo por unidad de cambio en la variable `xⱼ`.

***

## El modelo completo: estructura conceptual

| Etapa             | Fórmula                                               | Qué representa                        |
|------------------|--------------------------------------------------------|----------------------------------------|
| Regresores        | `xᵢ`                                                  | Variables predictoras                  |
| Offset (opcional) | `log(eᵢ)`                                            | Ajuste por exposición (si hay)         |
| Predictor lineal  | `ηᵢ = β₀ + β₁·x₁ᵢ + ... + log(eᵢ)`                     | Combinación lineal + offset            |
| Valor esperado    | `μᵢ = exp(ηᵢ)`                                        | Predicción del modelo (media esperada) |
| Observación real  | `yᵢ`                                                  | Conteo observado                       |
| Residuo           | `(yᵢ - μᵢ) / sqrt(μᵢ)`                                | Diferencia (ajustada) entre `y` y `μ`  |

***

## ¿Qué es un offset?

Cuando los eventos se observan sobre distintas **exposiciones** (ej: cantidad de operaciones, duración, volumen), usamos un **offset** para modelar **tasas** en vez de conteos absolutos.

Ejemplo:
```
log(μᵢ) = β₀ + β₁·x₁ + log(eᵢ)
```

Donde `eᵢ` es la exposición. El offset se **suma** en el log, con coeficiente **fijo = 1**.

***

## Supuestos del modelo de Poisson

1. La variable dependiente es un conteo entero no negativo.  
2. Las observaciones son independientes.  
3. La **media es igual a la varianza**: `E(Yᵢ) = V(Yᵢ) = μᵢ`.  
4. La relación entre `X` y `μ` es **exponencial**.

***

## Control de residuos y sobredispersión

El modelo asume `E(Yᵢ) = V(Yᵢ)`, pero si la varianza es mayor (común en trading), hay **sobredispersión**.

Entonces:

* Calculamos residuos estandarizados:
```
rᵢ = (yᵢ - μᵢ) / sqrt(μᵢ)
```

* Si muchos residuos están fuera de [-2, 2] → el modelo podría estar mal especificado

Soluciones:

- Usar **regresión binomial negativa**
- Aplicar **corrección robusta de varianza**

***

## Comparación de modelos

Para evaluar el modelo, usamos:

- **Deviance** (menor es mejor)
- **AIC** (menor es mejor, penaliza complejidad)
- **Pruebas de razón de verosimilitud** (comparar modelos anidados)

***

## Notas conceptuales

* La regresión de Poisson es un tipo de **modelo lineal generalizado (GLM)**.
* Usa como función de enlace el **logaritmo natural**:
```
log(μᵢ) = β₀ + β₁·x₁ + ... + βₚ·xₚ
```
* El modelo estima **medias esperadas de eventos**, no probabilidades.
* El análisis de residuos permite detectar datos atípicos o mal ajustados.
