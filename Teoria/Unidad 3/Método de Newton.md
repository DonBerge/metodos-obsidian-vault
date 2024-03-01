Suponiendo que se quiere encontrar la raíz $\alpha$ de una cierta función $f$.
Sea $x_{0}$ una aproximación inicial de $\alpha$, el polinomio de Taylor de $f$ centrado en $x_{0}$ es:
$$
f(x) \approx f(x_{0})+f'(x_{0})(x-x_{0})
$$
Evaluando en $\alpha$, se tiene que $f(\alpha)=0$
$0=f(\alpha) \approx f(x_{0})+f'(x_{0})(\alpha-x_{0})$
Despejando $\alpha$ se tiene la siguiente aproximación de la raíz
$x_{0}-\frac{f(x_{0})}{f'(x_{0})} \approx \alpha$
Esta aproximación de $\alpha$ puede usarse como una nueva aproximación inicial para hacer otra iteración.
Por eso, el método de newton define la iteración
$$
x_{n+1}=x_{n}-\frac{f(x_{n})}{f'(x_{n})}
$$
## Acotación del error
El polinomio de taylor de $f$ centrado en $x_{n}$ con error es:
$$
f(x)=f(x_{n})+f'(x_{n})(x-x_{n})+\frac{1}{2}(x-x_{n})^{2}f''(c_{n})
$$
Con $c_{n}$ un numero entre $x_{n}$ y $x$.
Evaluando en $\alpha$ se tiene que
$0=f(\alpha)=f(x_{n})+f'(x_{n})(\alpha-x_{n})+\frac{1}{2}(\alpha-x_{n})^{2}f''(c_{n})$
$-\frac{f(x_{n})}{f'(x_{n})}=\alpha-x_{n}+\frac{1}{2}(\alpha-x_{n})^{2} \frac{f''(c_{n})}{f'(x_{n})}$

$x_{n}-\frac{f(x_{n})}{f'(x_{n})}=\alpha+\frac{1}{2}(\alpha-x_{n})^{2} \frac{f''(c_{n})}{f'(x_{n})}$
$x_{n+1}=\alpha+\frac{1}{2}(\alpha-x_{n})^{2} \frac{f''(c_{n})}{f'(x_{n})}$
$\alpha-x_{n+1}=-\frac{1}{2}(\alpha-x_{n})^{2} \frac{f''(c_{n})}{f'(x_{n})}$

## Convergencia
El método de newton converge para $x_{0}$ lo suficientemente cercano a $\alpha$
Esto es debido a que para la función $g(x)=x-\frac{f(x)}{f'(x)}$ se cumple que
$g'(x)=1-\frac{f'(x)f'(x)-f(x)f''(x)}{f'(x)^{2}}=-\frac{f(x)f''(x)}{f'(x)^{2}}$
Evaluando en $\alpha$ $g'(x)$ se tiene que $g'(x)=0 \leq 1$. Por lo tanto el método de newton converge para $\alpha$ lo suficientemente cercano a $\alpha$
### Orden de convergencia
Se tiene que
$\alpha-x_{n+1}=-\frac{1}{2}(\alpha-x_{n})^{2} \frac{f''(c_{n})}{f'(x_{n})}$
Luego
$\lim_{ n \to \infty } \frac{\lVert a-x_{n+1} \rVert}{\left\lVert a-x_{n} \right\rVert^p}=\lim_{ n \to \infty } \frac{\lVert\alpha-x_{n}\rVert^{2}\lVert f''(c_{n})\rVert}{2\lVert \alpha-x_{n} \rVert^p \lVert f'(x_{n}) \rVert}$
$=\lim_{ n \to \infty } \left\lVert \frac{f''(c_{n})}{2f'(x_{n})} \right\rVert \frac{1}{\lVert \alpha-x_{n} \rVert^{p-2}}$

Suponiendo que el método de newton converge $\lim_{ n \to \infty } \lVert \alpha -x_{n}\rVert = 0$ y por lo tanto el limite no converge si $p>2$

Si en cambio $p=2$ se tiene que el limite anterior es igual a $\lim_{ n \to \infty } \left\lVert \frac{f''(c_{n})}{2f'(x_{n})} \right\rVert=\left\lVert \frac{f''(\alpha)}{2f'(\alpha)} \right\rVert$

Por lo tanto, la convergencia del método es cuadrática.