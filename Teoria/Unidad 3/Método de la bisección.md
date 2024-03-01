El método de la bisección es un método de dos puntos, suponiendo que se quiere encontrar $\alpha$ tal que $f(\alpha)=0$ para una cierta función $f$. Sean $a_{0}$ y $b_{0}$ dos puntos tal que $f(a_{0})f(b_{0})\leq 0$(tienen distinto signo).

Cada iteración se define como sigue:
1) Se calcula $c_{n}=\frac{a+b}{2}$
2) 
  - Si $sgn(f(a_{n}))=sgn(f(c_{n}))$ entonces $a_{n+1}=c_{n}$ y $b_{n+1}=b_{n}$
  - Si $sgn(f(b_{n}))=sgn(f(c_{n}))$ entonces $a_{n+1}=a_{n}$ y $b_{n+1}=c_{n}$
  - Si $f(c_{n})=0$ entonces $\alpha=c_{n}$

##  Calculo del error
Suponiendo sin perdida de generalidad que $b_{n+1}>a_{n+1}$
Si $b_{n+1}=c_{n}$ entonces $b_{n+1}-a_{n+1}=c_{n}-a_{n}=\frac{{b_{n}-a_{n}}}{2}$
Si $a_{n+1}=c_{n}$ entonces $b_{n+1}-a_{n+1}=b_{n+1}-c_{n}=\frac{{b_{n}-a_{n}}}{2}$

Por lo tanto para cada iteración: $b_{n+1}-a_{n+1}=\frac{1}{2}(b_{n}-a_{n})$
Luego por inducción se puede probar que $b_{n+1}-a_{n+1}=\left( \frac{1}{2} \right)^n(b_{0}-a_{0})$
CB) $n=1$
Es el caso anterior
PI)
$b_{n+2}-a_{n+2}=\frac{1}{2}(b_{n+1}-a_{n+1})=\frac{1}{2}\cdot \left( \frac{1}{2} \right)^n(b_{0}-a_{0})=\left( \frac{1}{2} \right)^{n+1}(b_{0}-a_{0})$

El error en una  iteración $n$ esta dado por
$\left| \alpha-c_{n} \right|\leq \left| b_{n}-c_{n} \right|=\frac{1}{2}\left( b_{n}-a_{n} \right)=\left( \frac{1}{2} \right)^n\left( b_{0}-a_{0} \right)$

Se tiene entonces que
$\lim_{ n \to \infty } |a-c_{n}| \leq \lim_{ n \to \infty } \left( \frac{1}{2} \right)^n(b_{0}-a_{0})=0$
Por lo tanto el método siempre converge.

## Orden de convergencia
El orden de convergencia esta definido por el mínimo numero $p\geq1$ tal que:
$$
\lim_{ n \to \infty } \frac{\lVert \alpha-x_{n+1} \rVert }{\lVert \alpha-x_{n} \rVert^p}=\beta <\infty
$$
Usando la formula anterior del error se tiene que:
$\lim_{ n \to \infty }\frac{\lVert \alpha-x_{n+1} \rVert}{\lVert \alpha-x_{n} \rVert}=\lim_{ n \to \infty } \frac{\left\lVert \left( \frac{1}{2} \right)^{n+1}(b_{0}-a_{0}) \right\rVert}{\left\lVert \left( \frac{1}{2} \right)^n(b_{0}-a_{0}) \right\rVert^p}$
$=\frac{1}{(b_{0}-a_{0})^{1-p}} \lim_{ n \to \infty } 2^{(p-1)n-1}$
$=0$ $\iff$ $p=1$

Por lo tanto, la convergencia del método es lineal con tasa de convergencia $\frac{1}{2}$