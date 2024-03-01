El metodo de Jacobi propone como iteración:
$$
x_{i}^{(n+1)}=\frac{1}{a_{ii}}\left( b_{i} -\sum_{j=1,j\neq i}^na_{ij}x_{j}^{(n)} \right) 
$$
El método de Gauss-Seidel propone como iteración utilizar los valores de la iteración actual al calcular los valores de $x^{(n+1)}$ es decir, propone como iteración:
$$
x_{i}^{(n+1)}=\frac{1}{a_{ii}}\left( b_{i} -\sum_{1\leq j<i}a_{ij}x_{j}^{(n+1)} -\sum_{i< j\leq n} a_{ij}x_{j}^{(n)} \right) 
$$
Se puede juntar el termino izquierdo $x_{i}^{(n+1)}$ con los terminos semejantes del lado derecho, asi, la iteración puede reescribirse como:
$$
\sum_{1\leq j\leq i}a_{ij}x_{j}^{(n+1)}=b_{i}-\sum_{i<j\leq n}a_{ij}x_{j}^{(n)}
$$
En forma matricial:
$$
\begin{pmatrix}
a_{11} & 0 & \dots & 0 & 0 \\
a_{21} & a_{22} & \dots & 0 & 0\\
\vdots & \vdots & \ddots & \vdots & \vdots \\ 
a_{(n-1)1} & a_{(n-1)2} & \dots & a_{(n-1)(n-1)} & 0 \\
a_{n1} & a_{n2} & \dots & a_{n(n-1)} & a_{nn}
\end{pmatrix}\mathbf{x^{(n+1)}}=\mathbf{b}-\begin{pmatrix}
a_{11} & a_{12} & \dots & a_{1(n-1)} & a_{1n} \\
0 & a_{22} & \dots & a_{2(n-1)} & a_{2n}\\
\vdots & \vdots & \ddots & \vdots & \vdots \\ 
0 & 0 & \dots & a_{(n-1)(n-1)} & a_{(n-1)n} \\
0 & 0 & \dots & 0 & a_{nn}
\end{pmatrix}\mathbf{x^{(n)}}
$$
Introduciendo la descomposición $A=L+D+U$ queda como:
$(L+D)\mathbf{x}^{(n+1)}=\mathbf{b}-U\mathbf{x}^{(n)}$
Si $L+D$ es invertible se consigue
$$
\mathbf{x}^{(n+1)}=(L+D)^{-1}\mathbf{b}+[I-(L+D)^{-1}A]\mathbf{x}^{(n)}
$$
