Los sistemas de ecuaciones lineales consisten en ecuaciones de la forma:
$$
a_{i1}x_{1}+a_{i2}x_{1}+\dots.+a_{in}x_{n}=b_{i}
$$
En formar simplificada:
$$
\sum_{j=1}^n a_{ij}x_{j} = b_{i}
$$
Se puede reordenar como
$\sum_{j=1}^na_{ij}x_{j}=\sum_{j=1,j\neq i}^n a_{ij}x_{j} +a_{ii}x_{i}=b_{i}$
$a_{ii}x_{i}=b_{i}-\sum_{j=1,j\neq i}^n a_{ij}x_{i}$
$x_{i}=\frac{1}{a_{ii}}\left( b_{i}-\sum_{j=1,j\neq i}^na_{ij}x_{j} \right)$

Partiendo de una suposición inicial $\mathbf{x}^{(0)}=\left[ x_{0}^{(0)},x_{1}^{(0)},\dots,x_{n}^{(0)} \right]$ el método de Jacobi propone como iteración:
$$
x_{i}^{(n+1)}=\frac{1}{a_{ii}}\left( b_{i} -\sum_{j=1,j\neq i}^na_{ij}x_{j}^{(n)} \right) 
$$

En forma matricial, sea $D$ la matriz diagonal de $A$:
$$
\mathbf{x}^{(n+1)}=D^{-1}\left[ \mathbf{b} + \left( D-A  \right)\mathbf{x}^{(n)}\right]
$$
