Paso 1:
Suponiendo $a^{(1)}_{11}\neq 0$, para cada fila por debajo, calcular los multiplicadores de fila
$$m_{i1}=\frac{{a^{(1)}_{i1}}}{a^{(1)}_{11}}$$
Y después ejecutar las operaciones de filas
$$
\begin{matrix}
a^{(2)}_{ij}=a^{(1)}_{ij}-m_{i1}a^{(1)}_{1j} \\
b^{(2)}_{ij}=b^{(1)}_{ij}-m_{i1}b^{(1)}_{1}
\end{matrix}
$$
Paso k:
Suponiendo $a^{(k)}_{kk} \neq 0$, para cada fila por debajo, calcular los multiplicadores de fila
$$
m_{ik}=\frac{{a^{(k)}_{ik}}}{a^{(1)}_{kk}}
$$
Y despues ejecutar las operaciones de filas
$$
\begin{matrix}
a^{(k+1)}_{ij} = a^{(k)}_{ij} - m_{ik}a^{(k)}_{kj} \\
b^{(k+1)}_{ij}=b^{(k)}_{ij} - m_{ik}b^{(k)}_{kj}
\end{matrix}
$$
Después de $n-1$ pasos, el sistema queda como un sistema triangular superior que se puede resolver por sustitución regresiva.

---
## Numero de operaciones del método de Gauss
En el paso $k$ se requieren:
- $n-k$ divisiones, para calcular los multiplicadores para las $n-k$ filas restantes.
- Para cada fila, se requieren $n-k$ sumas y multiplicaciones, y como se realizan estas operaciones en $n-k$ filas, se tienen en total $(n-k)^{2}$ operaciones por paso

Como la eliminación de gauss requiere $n-1$ pasos se tiene:
- Cantidad de sumas y multiplicaciones: $\sum_{k=1}^{n-1}(n-k)^2=\sum_{p=1}^{n-1}p^{2}=\frac{{n(n-1)(2n-1)}}{6}$
- Cantidad de divisiones: $\sum_{k=1}^{n-1} (n-k) = \frac{n(n-1)}{2}$

En total el orden de operaciones es $\frac{2}{3}n^{3}$
