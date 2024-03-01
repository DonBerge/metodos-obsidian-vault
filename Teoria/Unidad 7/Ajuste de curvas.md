Sea $y=g(x)$ una relación desconocida, se tiene el conjunto de puntos $\{(x_{i},y_{i})\}$ donde $y_{i}=g(x_{i})+v_{i}$ con $v_{i}$ un error de medición

Se quiere aproximar $g(x)$ por una función $f(x)$ de la forma:
$$f(x)=a_{1}\Phi_{1}(x)+a_{2}\Phi_{2}(x)+\dots+a_{p}\Phi_{p}(x)$$
Sea $|\epsilon_{i}|=|f(x_{i})-y_{i}|$ el error de aproximación

El problema de mínimos cuadrados consiste en hallar los coeficientes $a_{1},..a_{p}$ que minimizan la suma de los errores al cuadrado:
$$G(a_{1},\dots,a_{n})=\sum_{i=0}^n{\epsilon_{i}}^2=\sum_{i=0}^n\left(a_{1}\Phi_{1}(x_{i})+a_{2}\Phi_{2}(x_{i})+\dots+a_{p}\Phi_{p}(x_{i}) - y_{i}\right)^2$$
El problema de optimización consiste en encontrar el vector $x = [a_{1},a_{2},\dots,a_{p}]^T$ que minimiza $G$

Derivando en una variable $a_{k}$ y aplicando la regla de la cadena
$$\frac{ \partial G }{ \partial a_{k} } = \sum_{i=0}^n 2(a_{1}\Phi_{1}(x_{i})+\dots+a_{p}\Phi_{p}(x_{i})-y_{i})\Phi_{k}(x_{i}) \tag{1}$$
Derivando en otra variable(no necesariamente distinta) $a_{l}$:
$$\frac{ \partial^2 G }{ \partial a_{k} \partial a_{l} } = \sum_{i=0}^n 2{\Phi_{k}(x_{i})}\Phi_{l}(x_{i})$$
(no pude seguir, el punto es que la función es convexa porque la matriz hessiana es semidefinida positiva)

Como la función $G$ es convexa, todo mínimo local es un mínimo global, para encontrar el mínimo global de la función basta con encontrar un punto critico(dicho punto no puede ser un punto de inflexión, ya que sino la función no seria convexa).

Es decir, hay que buscar el punto $x$ tal que:
$\nabla G(x) = \left[\frac{ \partial G }{ \partial a_{1} },\dots,\frac{ \partial G }{ \partial a_{p} }\right] = 0$

Si (1) es $0$, entonces puede reestructurarse como sigue:
$$\frac{ \partial G }{ \partial a_{k} } = \left[\sum_{i=0}^n \Phi_{1}(x_{i})\Phi_{k}(x_{i}) \right]a_{1} + \dots + \left[\sum_{i=0}^n \Phi_{p}(x_{i})\Phi_{k}(x_{i}) \right]a_{p} = \sum_{i=0}^ny_{i}\Phi_{k}(x_{i}) \tag{2}$$
La solución por mininos cuadrados se consigue resolviendo el sistema de ecuaciones de arriba.
En forma matricial, dada las matrices:
$$
\begin{matrix}
\Phi = \begin{pmatrix}
\Phi_{1}(x_{0}) & \Phi_2(x_{0}) & \dots & \Phi_{p}(x_{0}) \\
\Phi_{1}(x_{1}) & \Phi_2(x_{1}) & \dots & \Phi_{p}(x_{1}) \\
\vdots & \vdots & \ddots & \vdots \\
\Phi_{1}(x_{n}) & \Phi_2(x_{n}) & \dots & \Phi_{p}(x_{n}) \\
\end{pmatrix}
&
b=
\begin{pmatrix}
y_{0} \\
\vdots \\
y_{n}
\end{pmatrix}
&
x=
\begin{pmatrix}
a_{0} \\
\vdots \\
a_{n}
\end{pmatrix}
\end{matrix}
$$
Se tiene que:
$\sum_{i=0}^n \Phi_{j}(x_{i})\Phi_{k}(x_{i}) = \sum_{i=0}^n \Phi_{i,j}\Phi_{i,k}=\sum_{i=0}^n {(\Phi^T)}_{j,i}\Phi_{i,k} = (\Phi^T\Phi)_{j,k}$

Por lo tanto el sistema (2) puede reescribirse como:
$$(\Phi^T\Phi)x = \Phi^Tb$$
(pista, ver que la matriz es semidefinida positiva viendo que define un producto interno)