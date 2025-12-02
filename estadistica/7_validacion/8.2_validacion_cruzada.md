# Validación cruzada

## Definición

La **validación cruzada** (cross-validation) es una técnica para **evaluar la capacidad de generalización de un modelo**. Consiste en dividir los datos en partes (folds), entrenar en algunas y validar en otras, repitiendo el proceso varias veces.

> Sirve para estimar cómo se comportará un modelo o estrategia **fuera de los datos con los que fue entrenado**.

***

## ¿Por qué es importante?

Porque una estrategia que funciona bien en su muestra de entrenamiento puede estar **sobreajustada**. Validar cruzadamente permite detectar si el rendimiento **se sostiene en datos no vistos**.

***

## Tipos comunes de validación cruzada

### k-Fold Cross Validation

* Divide los datos en _k_ partes.

* Se entrena _k_ veces, usando _k - 1_ partes como entrenamiento y la parte restante como prueba.

* Se promedian los resultados.

### Leave-One-Out (LOOCV)

* Caso extremo de k-Fold donde _k = n_, es decir, se deja fuera un solo dato por vez.

* Computacionalmente costoso, pero preciso.

### Walk-forward (rolling window)

* Especial para **series temporales**.

* Se avanza entrenando en una ventana fija y validando en la siguiente.

* Respeta el orden temporal (clave en trading).

***

## Aplicación al trading cuantitativo

* Validar una estrategia en datos fuera de muestra de forma repetida

* Evaluar la estabilidad de los resultados frente a diferentes particiones temporales

* Evitar conclusiones optimistas por ajuste a un único período de mercado

> 📌 _Ejemplo: una estrategia optimizada en 2018-2019 es evaluada en 2020, 2021 y 2022 por separado_

***

## Ejemplo básico en Python (k-Fold)

```python
from sklearn.model_selection import KFold
import numpy as np

X = np.arange(10)
kf = KFold(n_splits=5, shuffle=False)

for train_index, test_index in kf.split(X):
    print("Train:", X[train_index], "Test:", X[test_index])
```

### Ejemplo: validación tipo walk-forward (manual)

```python
data = np.random.normal(0, 1, 100)
window = 50

for start in range(0, len(data) - window):
    train = data[start:start+window]
    test = data[start+window]
    # Aquí podrías entrenar un modelo en 'train' y evaluar en 'test'
```
