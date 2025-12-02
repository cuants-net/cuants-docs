# Codificación de variables para regresión logística

Cuando trabajamos con regresión logística en el contexto del trading cuantitativo, uno de los primeros pasos fundamentales es **preparar los datos**. Esto incluye transformar las variables para que el modelo pueda interpretarlas correctamente.

Aunque el modelo matemático se basa en números, muchas veces nuestros datos contienen **estados, tipos de apertura o condiciones del mercado**. Vamos a ver paso a paso cómo convertir esas situaciones en variables numéricas sin perder su significado operativo.

---

## Punto de partida: ¿cuándo usar codificación?

Supongamos que queremos predecir si un día de mercado dará una **señal de entrada larga**. Para eso tenemos tres datos:

* **Variación previa** (diferencia entre el cierre y apertura del día anterior)
* **Tipo de apertura** (alcista, bajista o neutra)
* **Volumen relativo** (¿el volumen fue mayor al promedio?)

Queremos saber: “¿Podemos predecir la entrada a partir de estos datos?”

Pero antes de entrenar el modelo, necesitamos convertir todo a números.

---

## Variables numéricas: se usan directo

La variable **variación previa** es numérica (por ejemplo: +1.3, –0.8) y puede entrar al modelo tal como está.

---

## Variables dicotómicas: sí/no

**Volumen relativo** es una variable dicotómica. Tiene dos estados posibles: mayor o no mayor al promedio. Se codifica como:

* Volumen mayor al promedio: 1
* Volumen igual o menor al promedio: 0

El modelo interpretará: “¿Cómo influye operar con volumen alto en la probabilidad de entrada?”

---

## Variables categóricas con más de dos niveles: usar variables dummy

**Tipo de apertura** puede tener tres estados:

* Alcista
* Bajista
* Neutra

No podemos codificar como 1, 2, 3. El modelo pensaría que “bajista > alcista”, lo cual no tiene sentido.

Lo que hacemos es crear **una columna para cada categoría**, que vale 1 si el día tiene ese tipo de apertura y 0 si no.

| Apertura\_Alcista | Apertura\_Bajista | Apertura\_Neutra |
| ----------------- | ----------------- | ---------------- |
| 1                 | 0                 | 0                |
| 0                 | 1                 | 0                |
| 0                 | 0                 | 1                |

Para evitar redundancia, eliminamos una de las columnas (por ejemplo, la neutra), y el modelo compara las otras respecto a esa referencia.

---

## Resumen de codificación

| Tipo de variable        | Ejemplo                             | Codificación sugerida       |
| ----------------------- | ----------------------------------- | --------------------------- |
| Numérica continua       | Variación previa, Rango de apertura | Sin cambios                 |
| Dicotómica (2 niveles)  | Volumen alto (sí/no)                | 1/0                         |
| Categórica (3+ niveles) | Tipo de apertura                    | Variables dummy (una menos) |

---

## Consejos prácticos

* No uses números como etiquetas si no hay orden real.
* Usá variables dummy para categorías no jerárquicas.
* Elegí conscientemente qué categoría dejar como referencia.
* A veces se puede agrupar categorías poco frecuentes en "Otro" (ej: “apertura atípica”).

---

## Notas conceptuales

* A la transformación de variables cualitativas a números se la llama **codificación**.
* Las variables que toman solo 0 o 1 se llaman **dummy** o **indicadoras**.
* El proceso es necesario porque el modelo logístico **solo trabaja con números**.
* En algunos softwares esto se hace automáticamente, pero entenderlo permite evitar errores y mejorar la interpretación de los resultados.

---
