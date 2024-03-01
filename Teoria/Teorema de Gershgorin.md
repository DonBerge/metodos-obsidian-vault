Dada la matriz compleja $A$, se definen los circulos de gershgorin como

$$C_{i}=\{ z \in \mathbb{C} : |z-a_{ii}| \leq r_{i} \}$$
Donde
$$r_{i}=\sum_{j=1,j\neq i}^n |a_{i}|$$

Se puede demostrar lo siguiente, todo autovalor de $A$ pertenece a algún circulo de Gershgorin

## Demostración
Sea $\lambda$ un autovalor de $A$, se tiene que existe un autovector $v$, es decir:
$$Av=\lambda v \tag{1}$$

Sea $k \in \mathbb{N}$ tal que $|v_{k}|=\lVert v\rVert_{\infty}$(es decir, $k$ es el índice de la mayor componente)

Entonces para la $k$-esima componente de (1) se tiene que:
$$\sum_{j=1}^na_{kj}v_{j} = \lambda v_{k}$$
Y por lo tanto:
$$(\lambda-a_{kk})v_{k} = \sum_{j=1,j\neq k}^n a_{kj}v_{j}$$
Aplico valor absoluto a ambos lados
$$|(\lambda-a_{kk})|\lVert v\rVert_{\infty}=|(\lambda-a_{kk})| |v_{k}| \leq \sum_{j=1,j\neq k}^n |a_{kj}| |v_{j}| \leq r_{k}\lVert v\rVert_{\infty}$$
Y por ende $|\lambda-a_{kk}| \leq r_{k}$ y $\lambda \in C_{k}$
