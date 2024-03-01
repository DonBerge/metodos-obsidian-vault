Se demuestra por inducción en $n$:

CB) $n=2$
En este caso se tiene que
$|a_{11}| > |a_{12}|$ y $|a_{22}| > |a_{21}|$
Por lo tanto $a_{11} \neq 0$ y $a_{22} \neq 0$(sino se tiene que $0 > |a_{12}|$ con $|a_{12}|$ un numero positivo).

No es necesario un pivoteo para la primera fila, al aplicar la eliminación de gauss se tiene que
$a_{22}^{(2)} = a_{(22)}^{(1)} - a_{12}^{(1)} \cdot \frac{a_{21}^{(1)}}{a_{11}^{(1)}} = \frac{\det(A)}{a_{11}^{(1)}} \neq 0$

Por lo tanto no es necesario un pivoteo.

HI) Para toda matriz $A \in \mathbb{R}^{n \times n}$ estrictamente diagonal dominante, no es necesario un pivoteo.

PI)
Para la matriz $n+1 \times n+1$ definida como
$$
\begin{pmatrix}
a_{11} & a_{12} & \dots & a_{1,n+1} & b_{1} \\
a_{21} & a_{22} & \dots & a_{2,n+1} & b_{2} \\
\vdots & \vdots & \ddots & \vdots & \vdots \\
a_{n+1.1} & a_{n+1,2} & \dots  & a_{n+1,n+1} & b_{n+1} \\
\end{pmatrix}
$$
Tras aplicar una vez la eliminación gaussiana se tiene que:
$$
\begin{pmatrix}
a_{11} & a_{12} & \dots & a_{1,n+1} & b_{1} \\
0 & a_{22} - a_{12} \cdot \frac{a_{21}}{a_{11}}  & \dots & a_{2,n+1} - a_{1,n+1} \cdot \frac{a_{21}}{a_{11}} & b_{2} - b_{1} \cdot \cdot \frac{a_{21}}{a_{11}} \\
\vdots & \vdots & \ddots & \vdots & \vdots \\
0 & a_{n+1,2} - a_{12} \cdot \frac{a_{n+1,1}}{a_{11}} & \dots  & a_{n+1,n+1} - a_{1,n+1} \cdot \frac{a_{n+1,1}}{a_{11}} & b_{n+1} - b_{1} \cdot \frac{a_{n+1,1}}{a_{11}} \\
\end{pmatrix}
$$

En particular para $i \geq 2$:
$a_{ij}^{(2)} = a_{ij} - a_{1,j} \cdot \frac{a_{i1}}{a_{11}}$

A partir de acá, probar que la submatriz $A(1|1)$ en la segunda interacción es estrictamente DD y en consecuencia no hace falta aplicar pivoteo parcial.