# Estrategia de baja precision

## Introducción

Te encontrás con esta estrategia:

- Acierta solo 3 de cada 10 veces.
- Pero cuando gana, gana $100.
- Cuando pierde, pierde $30.

Tu primera reacción es pensar:  
**“¡Tiene una tasa de acierto bajísima! ¿Cómo puede ser buena?”**

Pero lo es.  
Y para entender por qué, necesitamos mirar **algo más que la frecuencia de aciertos**.  
Necesitamos mirar la **expectativa**.

## ¿Qué es la expectativa?

La expectativa matemática (o esperanza de ganancia)  
es lo que esperás ganar (o perder), **en promedio**, cada vez que aplicás la estrategia.

Se calcula como:

Expectativa = (Probabilidad de acierto × Ganancia) + (Probabilidad de fallo × Pérdida)

En nuestro ejemplo:

E = (0.3 × 100) + (0.7 × –30) = 30 – 21 = +9


Eso significa que, en promedio, **ganás $9 por trade**.
Aunque pierdas más veces de las que ganás.

## ¿Qué rol juega la tasa de acierto?

La tasa de acierto **no es buena ni mala por sí sola**.  
Es solo uno de los ingredientes.

Una estrategia puede tener:

- Alta tasa de acierto pero perder más de lo que gana (mal payoff).
- Baja tasa de acierto pero ganar más de lo que pierde (buen payoff).

Lo que importa es **cómo se equilibran ambas cosas**.

## ¿Y qué es el payoff?

El payoff es la relación entre la ganancia media y la pérdida media:

En nuestro ejemplo:

Payoff = 100 / 30 ≈ 3.33

Eso significa que **una sola operación ganadora cubre más de tres perdedoras**.

Con ese payoff, **no necesitás una tasa de acierto alta** para ser rentable.

---

## ¿Cómo se combinan?

Existe una fórmula simple para conocer la tasa mínima de acierto que necesitás:

Tasa mínima = 1 / (1 + Payoff)

Con un payoff de 3.33:

Eso quiere decir que **con acertar apenas el 23% de las veces, la estrategia ya no pierde dinero**.

Si acertás más que eso, **tenés expectativa positiva**.

---

## ¿Por qué esto es importante en inferencia?

Porque muchas veces, cuando analizamos una estrategia,  
lo primero que miramos es **la tasa de acierto**.  
Y si no supera el 50%, pensamos que no sirve.

Pero eso es un error.

Lo que deberías preguntarte es:

**¿La tasa de acierto observada supera el mínimo necesario para ser rentable?**

Y eso **sí** es algo que podés evaluar con inferencia.

---

## Ejemplo aplicado

Probás una estrategia que acierta el 34% de las veces,  
con un payoff estimado de 2.8.

Calculás la tasa mínima necesaria:

1 / (1 + 2.8) ≈ 0.26

yaml
Copy
Edit

Tu estrategia está por encima.  
Entonces el siguiente paso es evaluar si esa diferencia es **estadísticamente significativa**.  
Ahí entra el test de hipótesis para una proporción, que ya vimos.

---

## Cierre

La tasa de acierto no es el juez de tu estrategia.  
Es solo un número.

Lo que importa es **la relación entre cuánto ganás cuando ganás y cuánto perdés cuando perdés**.  
Eso es lo que determina si la expectativa es positiva.

Y una estrategia con baja tasa de acierto,  
pero con buena expectativa,  
es como un cazador paciente:

No acierta siempre…  
pero cuando lo hace, **vale la pena**.