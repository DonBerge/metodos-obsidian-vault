Sea $A$ una matriz real con autovalores $\lambda_{1},\dots \lambda_{n}$, si existe un único autovalor de modulo máximo, es decir:
$$|\lambda_{1}| > |\lambda_{2}| \geq |\lambda_{3}| \geq \dots$$
Partiendo de una estimación inicial $z_{0}$ del autovector de $\lambda_{1}$ defino la iteración:
$$z_{n+1} = \frac{{Az_{n}}}{\lVert Az_{n} \rVert_{\infty}}$$
Resulta entonces que:
$\lim_{ n \to \infty } z_{n} = v_{1}$ con $v_{1}$ el autovector correspondiente a $\lambda_{1}$
Y dada una componente no nula de índice $k$ de $Az_{n}$
$\lim_{ n \to \infty } \lambda_{n} = \frac{Az_{n}(k) }{z_{n}(k)} = \lambda_{1}$

## Cuando no funciona?
Si la estimación inicial es ortogonal a $v_{1}$, el método no convergerá

Suponiendo que $z_{0} \perp v_{1}$:
$A$ es diagonalizable y por ende existe una base de autovectores $\{ v_{1},\dots v_{n} \}$ de $\mathbb{R}^n$
$z_{0} = \sum_{i=1}^n c_{i}v_{i}$
$Az_{0} = \sum_{i=1}^n \lambda_{i}c_{i}v_{i}$