Una matriz $A \in \mathbb{R}^{n \times n}$ es diagonal dominante $\iff \forall i=1,\dots ,n$, $|a_{ii}| > \sum_{j=1, j\neq i}^n |a_{ij}|$

Toda matriz diagonal dominante es no singular, es decir, $\det(A) \neq 0$.

Por el contrario, si existiese una matriz diagonal dominante singular entonces existe un vector $v \neq 0$ tal que $Av = 0$

Y por lo tanto para $i = 1,\dots,n$ y $v_{i} \neq 0$:
$\sum_{j=1}^n a_{ij}v_{j} = 0$
$\sum_{j=1,j\neq i}^n a_{ij}v_{j} + a_{ii}v_{i} = 0$
$\sum_{j=1,j\neq i}^n a_{ij}v_{j} = -a_{ii}v_{i}$
$|a_{ii}v_{i}| = |\sum_{j=1,j\neq i}^n a_{ij}v_{j}| < \sum_{j=1,j\neq i}^n |a_{ij}v_{j}|$
$|a_{ii}| < \sum_{j=1,j\neq i}^n \left|\frac{v_{j}}{v_{i}}\right| |a_{ij}|$

En particular se puede tomar el valor de $i$ tal que $v_{i}$ sea máximo, el cual debe ser necesariamente distinto de 0, luego $\forall j, \left|\frac{v_{j}}{v_{i}}\right| \leq 1$ y entonces

$|a_{ii}| < \sum_{j=1,j\neq i}^n \left|\frac{v_{j}}{v_{i}}\right| |a_{ij}| < \sum_{j=1,j\neq i}^n |a_{ij}|$

Lo cual contradice la definición de matriz diagonal dominante, por lo tanto $\det(A) \neq 0$.
