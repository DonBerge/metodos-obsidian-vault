El orden de convergencia de un método $x_{n} \to \overline x$ es el numero $p$ tal que:
$$\lim_{ n \to \infty } \frac{{||{x_{n+1}-\overline x}||}}{||x_{n}-\overline x||^p} = \beta < \infty$$
## Método de la bisección
El error del método esta acotado por
$|x_{n}-\alpha| \leq \left(\frac{1}{2}\right)^n(b-a)$

Luego
$$\lim_{ n \to \infty } \frac{{||{x_{n+1}-\overline x}||}}{||x_{n}-\overline x||^p} = \lim_{ n \to \infty } \frac{||{(\frac{1}{2})}^{n+1}(b-a)||}{||{{(\frac{1}{2})}^{n}(b-a)||}^p}$$
$$=\lim_{ n \to \infty } {\frac{2^{(p-1)n-1}}{(b-a)^{p-1}}} $$
Si $p> 1$, $\lim_{ n \to \infty } {2}^{(p-1)n-1} = +\infty$ y el limite anterior tiende a infinito
Si $p=1$, el limite queda como
$$\lim_{ n \to \infty } \left\lVert\frac{\left( \frac{1}{2} \right)^{n+1}}{\left( \frac{1}{2} \right)^{n}}\right\rVert = \lim_{ n \to \infty } \frac{1}{2} = \frac{1}{2}$$
La convergencia es lineal con tasa de convergencia $\frac{1}{2}$

## Método de newton
El método de newton es un método de punto fijo donde:
$$x_{n+1}=x_{n}-\frac{f(x_{n})}{f'(x_{n})}$$
Suponiendo que el método de newton converge a $\alpha$
El polinomio de Taylor de $f$ de grado $2$ con error alrededor de $x_{n}$ y evaluándolo en $\alpha$ se tiene que:
$$0=f(\alpha)=f(x_{n})+(\alpha-x_{n})f'(x_{n})+\frac{1}{2}(\alpha-x_{n})^2f''(c_{n})$$
Con $c_{n}$ entre $\alpha$ y $x_{n}$

$f'(x_{n})\neq 0$, dividiendo todo por $f'(x_{n})$ se consigue
$$0 = \frac{f(x_{n})}{f'(x_{n})}+(\alpha-x_{n})+\frac{1}{2}(\alpha-x_{n})^2 \frac{f''(c_{n})}{f'(x_{n})}$$
O reescribiéndolo a partir de la iteración del método:
$$0=x_{n}-x_{n+1}+\alpha-x_{n}+\frac{1}{2}(\alpha-x_{n})^2 \frac{f''(c_{n})}{f'(x_{n})}$$
Y queda al final
$$\alpha-x_{n}=-\frac{f''(c_{n})}{2f'(x_{n})}(a-x_{n})^2$$
Y entonces
$$\lim_{ n \to \infty } \frac{{|a-x_{n+1}|}}{(a-x_{n})^2} = \lim_{ n \to \infty }\left|-\frac{f''(c_{n})}{2f'(x_{n})}\right| = \left|\frac{f''(\alpha)}{2f'(\alpha)}\right|$$
El método tiene convergencia cuadrática.

## Método de la secante
Suponiendo que el método converge a $\alpha$
Dada la iteración del método de la secante
$$x_{n+1}=x_{n}-f(x_{n}) \frac{{x_{n}-x_{n-1}}}{f(x_{n})-f(x_{n-1})}$$

Defino para mayor simplicidad: $\epsilon_{n}=\alpha-x_{n}$
Se tiene que $x_{n+1}-x_{n} = (\alpha-x_{n})-(\alpha-x_{n+1}) = \epsilon_{n}-\epsilon_{n+1}$

El polinomio de Taylor de $f$ alrededor de $\alpha$ 
$f(x)=f(\alpha)+(x-\alpha)f'(\alpha)+\frac{1}{2}(x-\alpha)^{2}f''(c_{n}) =(x-\alpha)f'(\alpha)+\frac{1}{2}(x-\alpha)^2f''(c_{n})$
Evaluado en $x_{n}$
$f(x_{n})=(x_{n}-\alpha)f'(\alpha)+\frac{1}{2}(x-\alpha)^2f''(c_{n})$
$=-\epsilon_{n}f'(\alpha)+\frac{1}{2}{\epsilon_{n}}^2f''(c_{n})$
$=\epsilon_{n}\left(f'(\alpha)+\frac{1}{2}\epsilon_{n}f''(c_{n})\right)$

(acá hay un error, no considero los distintos $c_{n}$)
Por lo tanto:
$f(x_{n})-f(x_{n-1})=(\epsilon_{n-1}-\epsilon_{n})f'(\alpha)+\frac{1}{2}({\epsilon_{n}}^2-{\epsilon_{n-1}}^2)f''(c_{n})$
$=(\epsilon_{n-1}-\epsilon_{n})\left(f'(\alpha)+\frac{1}{2}(\epsilon_{n}+\epsilon_{n-1})f''(c_{n})\right)$

Entonces puedo restarle a $\alpha$ ambos lados de la formula de iteración para obtener lo siguiente
$$\alpha-x_{n+1}=\alpha-x_{n}+f(x_{n}) \frac{{x_{n}-x_{n-1}}}{f(x_{n})-f(x_{n-1})}$$
Simplificando
$$\epsilon_{n+1}=\epsilon_{n}+\epsilon_{n}\left(f'(\alpha)+\frac{1}{2}\epsilon_{n}f''(c_{n})\right) \frac{{\epsilon_{n-1}-\epsilon_{n}}}{(\epsilon_{n-1}-\epsilon_{n})\left(f'(\alpha)+\frac{1}{2}(\epsilon_{n}+\epsilon_{n-1})f''(c_{n})\right)}$$

$$e_{n+1}=\epsilon_{n}+\epsilon_{n} \frac{{f'(\alpha)+\frac{1}{2}\epsilon_{n}f''(c_{n})}}{f'(\alpha)+\frac{1}{2}(\epsilon_{n-1}+\epsilon_{n})f''(c_{n})}$$
