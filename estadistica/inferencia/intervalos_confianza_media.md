# Intervalos de confianza para la media

## El problema

Ya sabés que la media muestral es una estimación del valor real.  
Pero… ¿qué tan confiable es esa estimación?

No podés saber si tu promedio es exacto.  
Pero sí podés **acotar el rango donde probablemente esté la media verdadera**.  
Eso se llama: **intervalo de confianza**.

## ¿Qué es un intervalo de confianza?

Es un rango alrededor de la media muestral, dentro del cual **creemos que está la media real**, con cierto nivel de confianza.

“Con un 95% de confianza, la media real está entre 0.15% y 0.25%”

No garantiza que la media esté ahí.  
Pero si repitieras muchas veces el experimento, el 95% de los intervalos construidos de esta forma **incluirían el valor real**.

## ¿Cómo se calcula?

Cuando conocemos la desviación poblacional (caso ideal):

$$
IC = \bar{x} \pm z_{\alpha/2} \cdot \frac{\sigma}{\sqrt{n}}
$$
Donde:
- $\bar{x}$: media muestral
- $z_{\alpha/2}$: valor crítico de la normal estándar (por ejemplo, 1.96 para 95%)
- $\sigma$: desviación estándar poblacional
- $n$: tamaño de la muestra

## Pero en la práctica no conocemos $\sigma$

Entonces usamos la desviación **muestral** ($s$), y reemplazamos $z$ por un valor de la **distribución $t$ de Student**:

$$
IC = \bar{x} \pm t_{\alpha/2, n-1} \cdot \frac{s}{\sqrt{n}}
$$
La lógica es la misma:  
“Media muestral ± margen de error”

Solo que ahora usamos un modelo que **ajusta el error** al tamaño de muestra.

## Ejemplo

Una estrategia tuvo un retorno medio diario de **0.21%** en una muestra de 100 días.  
Desviación estándar muestral: 1.6%

Nivel de confianza: 95% → $t_{0.025, 99} \approx 2.00$

Error típico:

$$
\text{Error} = 2.00 \cdot \frac{1.6}{\sqrt{100}} = 2.00 \cdot 0.16 = 0.32
$$
Entonces el intervalo es:

$$
IC = 0.21 \pm 0.32 = (-0.11\%, 0.53\%)
$$
El retorno verdadero podría ser negativo. No hay evidencia suficiente para confiar todavía.

## ¿Qué factores afectan el intervalo?

- **Nivel de confianza**: mayor confianza → intervalo más amplio  
- **Variabilidad (s)**: más dispersión → mayor incertidumbre  
- **Tamaño de muestra**: mayor $n$ → intervalo más estrecho

## ¿Qué me dice el intervalo?

- Si **no contiene cero**, tenés evidencia de que la media es distinta de cero.
- Si el intervalo es **muy ancho**, tus datos no permiten afirmar nada sólido.
- Si es **muy estrecho pero contiene cero**, tu estimación es precisa, pero poco prometedora.

## Nota conceptual

El intervalo de confianza **no dice dónde está la media con certeza**, sino qué tan confiable es tu proceso de estimación.  
Es una forma estructurada de expresar incertidumbre.  
Y eso, en trading, **vale más que una predicción sin medida.**
