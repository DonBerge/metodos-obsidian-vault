Sea el conjunto de puntos $\{ (x_{i},y_{i}) : y_{i}=f(x_{i}), i=0,1,\dots ,n \}$

Se quiere encontrar un polinomio $p(x)$ tal que $p(x_{i})=y_{i} \forall i$

Suponiendo que el grado de $p$ es $n$, se quiere resolver el siguiente sistema de ecuaciones
$$
\begin{matrix}
p(x_{0})=a_{0}+a_{1}x_{0}+\dots+a_{m}x_{0}^n=y_{0} \\
p(x_{1})=a_{0}+a_{1}x_{1}+\dots+a_{m}x_{1}^n=y_{1} \\
\vdots \\
p(x_{n})=a_{0}+a_{1}x_{n}+\dots+a_{m}x_{n}^n=y_{n} \\
\end{matrix}
$$
En forma matricial
$$Xa=y$$
Donde:
$$
\begin{matrix}
X =\begin{pmatrix}
1 & x_{0} & \dots & x_{0}^n \\
1 & x_{1} & \dots & x_{1}^n \\
\vdots & \vdots & \ddots & \vdots\\
1 & x_{n} & \dots & x_{n}^n \\
\end{pmatrix} & a= \begin{pmatrix}
a_{0} \\
a_{1} \\
\vdots \\
a_{m}
\end{pmatrix} &&  
y=\begin{pmatrix}
y_{0} \\
y_{1} \\
\vdots \\
y_{m}
\end{pmatrix}
\end{matrix}
$$
Donde $X$ es la matriz de Vandermonde
## Determinante de la matriz de Vandermonde
Se puede probar por inducción que:
$$\\det(X) = \prod_{0\leq j<i\leq n} (x_{i}-x_{j})$$
CB) $n=1$
La matriz es $\begin{pmatrix}1 & x_{0} \\ 1 & x_{1}\end{pmatrix}$ y su determinante es $x_{1}-x_{0}$, lo cual se corresponde con la propiedad.
PI)
A la $i$-esima columna le resto la columna anterior multiplicada por $x_{0}$(la primera columna queda como esta).
La entrada $ij$ con $j=0,1,\dots,n$ queda como:
$x_{j}^i - x_{j}^{i-1} \cdot x_{0} = x_{j}^{i-1}(x_{j}-x_{0})$
Cuando $j=0$, se tiene que la entrada $i_{0}$ es igual a $0$
Por lo tanto la matriz queda como:
$$
\begin{vmatrix}
1 & 0 & \dots & 0 \\
1 & x_{1}-x_{0} & \dots & x_{1}^{n-1}(x_{1}-x_{0}) \\
\vdots & \vdots & \ddots & \vdots\\
1 & x_{n}-x_{0} & \dots & x_{n}^{n-1}(x_{n}-x_{0}) \\
\end{vmatrix}
$$
Se puede expandir el determinante por la primera fila para que quede como sigue:
$$
\begin{vmatrix}
x_{1}-x_{0} & \dots & x_{1}^{n-1}(x_{1}-x_{0}) \\
\vdots & \ddots & \vdots\\
x_{n}-x_{0} & \dots & x_{n}^{n-1}(x_{n}-x_{0}) \\
\end{vmatrix}
$$
Extraigo los factores comunes de cada columna:
$$
\prod_{1\leq i\leq n}(x_{i}-x_{0}) \begin{vmatrix}
1 & \dots & x_{1}^{n-1} \\
\vdots & \ddots & \vdots\\
1 & \dots & x_{n}^{n-1} \\
\end{vmatrix}
$$
Donde la matriz de la izquierda es la matriz de Vandermonde con un nodo de interpolación, aplicando la HI se puede simplificar el determinante como queda
$$
\prod_{1\leq i\leq n}(x_{i}-x_{0}) \prod_{1\leq j<i<n}(x_{i}-x_{j})=\prod_{0\leq j<i\leq n}(x_{i}-x_{0})
$$

## Existencia y unicidad del polinomio interpolante
Como todos los nodos de interpolación son distintos $\det(X) \neq 0$ y por lo tanto el sistema $Xa=y$ tiene solución única.
## Limitaciones computacionales
La matriz de Vandermonde es no singular pero esta mal condicionada

Por ejemplo, si se tienen $n$ nodos equiespaciados en el intervalo $[0,1]$
$x_{i}=\frac{i}{n-1}$
$x_{i}-x_{j} = \frac{{i-j}}{n-1}$
$\lim_{ n \to \infty }{\det(X)}=\lim_{ n \to \infty } \prod_{0\leq j<i\leq n}(x_{i}-x_{0})$
$=\lim_{ n \to \infty } \prod_{0\leq j<i\leq n}\frac{i-j}{n-1}$
(el punto es que tiende a $0$)
