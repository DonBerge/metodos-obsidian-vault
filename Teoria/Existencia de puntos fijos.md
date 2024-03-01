Un punto fijo de una función $g$ es un valor $x \in \mathbb{R}$ tal que
$$g(x)=x$$
## Condición suficiente de existencia de puntos fijos
Sea $g(x)$ una función continua en $[a,b]$ tal que
$$a \leq x \leq b \implies a \leq g(x) \leq b$$
Entonces la ecuación $x = g(x)$ tiene una solución $\alpha$ en el intervalo $[a,b]$
Si $g$ cumple esta condición, se dice que $g$ es contractiva.
### Demostración
Sea la función $f(x) = x-g(x)$
$f$ es continua ya que es una resta de funciones continuas
Notar que como $a \leq g(a)$ se tiene que $f(a) = a - g(a) \leq 0$
Y como $g(b) \leq b$ se tiene que $f(b) = b - g(b) \geq 0$

Luego por teorema de bolzano $\exists \alpha : f(\alpha) = 0$ y por lo tanto $\alpha - g(\alpha) = 0 \implies \alpha = g(\alpha)$.


