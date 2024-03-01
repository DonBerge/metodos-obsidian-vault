El metodo de la secante es un metodo de dos puntos, se tiene que la iteración del metodo de newton es:
$$
x_{n+1}=x_{n}-\frac{f(x_{n})}{f'(x_{n})}
$$
Teniendo en cuenta que $f'(x_{n})=\lim_{ a \to x_{n} } \frac{f(x_{n})-f(a)}{x_{n}-a}$, se puede tomar $a=x_{n-1}$ como aproximación de $f'(x_{n})$ para tener la siguiente iteración:
$$
x_{n+1}=x_{n}-f(x_{n}) \frac{x_{n}-x_{n-1}}{f(x_{n})-f(x_{n-1})}
$$
## Análisis del error
Se pude demostrar que
$\lVert \alpha-x_{n+1} \rVert=\frac{1}{2}(\alpha-x_{n})(\alpha-x_{n-1}) \frac{f''(\xi_{n})}{f'(c_{n})}$

Luego si $x_{n}$ converge a $\alpha$ se tiene que
$\lim_{ n \to \infty } \frac{{\lVert \alpha-x_{n+1} \rVert}}{\lVert \alpha-x_{n} \rVert^p}= \left| \frac{f''(\alpha)}{2f'(\alpha)} \right|^{p-1}$
con $p=\phi=\frac{\sqrt{ 5 }+1}{2}$
