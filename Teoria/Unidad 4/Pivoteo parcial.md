En cada paso del algoritmo de gauss se supone que $a^{(k)}_{kk} \neq 0$, si $a^{(k)}_{kk}=0$ se puede intercambiar la $k$-esima fila por alguna fila por debajo de de esta donde $a^{(k)}_{ik} \neq 0$ y continuar con el algoritmo normalmente.

Si el sistema tiene solución, entonces esto siempre es posible
<u>Demostración:</u>
	Sea $A^{(k)}$ la matriz de coeficientes en el $k$-esimo paso, las operaciones de filas del metodo de gauss con pivoteo parcial no anulan el determinante. Como el sistema tiene solución $\det(A^{(1)})\neq 0$ y por ende $\det(A^{(k)})\neq 0$.
	Suponiendo que en el paso $k$ se tiene que $a^{(k)}_{kk}=0$, entonces la matriz $A^{(k)}$ se puede dividir por bloques:
	$A^{(k)}=\begin{pmatrix}A^{(k)}_{11} & A^{(k)}_{12} \\ 0 & A_{22}^{(k)}\end{pmatrix}$
	Donde $A^{(k)}_{11}$ es una matriz $k\times k$ y $A^{(k)}_{22}$ es una matriz $(n-k)\times(n-k)$
	Y por lo tanto $\det(A^{(k)})=\det(A^{(k)}_{11})\det(A^{(k)}_{22})$. De aquí se desprende que $\det(A_{22}^{(k)})\neq 0$ y por ende la primera columna no puede ser nula. Por ende, el pivoteo parcial es posible.

---
## Casos especiales
### Matrices simétricas y definidas positivas
Las matrices simétricas definidas positivas pueden escalonarse por el método de gauss sin necesidad de pivoteo, además, todos los elementos pívots son positivos:
