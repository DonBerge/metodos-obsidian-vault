El metodo de Gauss-Seidel se puede modificar como sigue:
$$
x_{i}^{(n+1)}=(1-\omega)x_{i}^{(n)}+\frac{\omega}{a_{ii}}\left[ b_{i}-\sum_{1\leq j<i}a_{ij}x_{j}^{(n+1)}-\sum_{i<j\leq n}a_{ij}x_{j}^{(n)} \right] 
$$
Que se puede reordenar como:
$$
a_{ii}x_{i}^{(n+1)}+\omega\sum_{1\leq j<i}a_{ij}x_{j}^{(n+1)}=(1-\omega)a_{ii} \cdot x_{i}^{(n)}+\omega b_{i}-\omega \sum_{i< j\leq n}a_{ij}x_{j}^{(n)}
$$
Que se puede reescribir de forma matricial como:
$$
D\mathbf{x}^{(n+1)}+\omega L \cdot\mathbf{x}^{(n+1)}=(1-\omega)D\mathbf{x}^{(n)}+\omega b-\omega U \mathbf{x}^{(n)} 
$$
Que es igual a
$$
(D+\omega L)\mathbf{x}^{(n+1)}=\left[ (1-\omega)D-\omega U \right]\mathbf{x}^{(n)}+\omega b 
$$