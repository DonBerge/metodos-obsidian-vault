Los métodos iterativos de punto fijo son aquellos donde, partiendo de una iteración $x_{0}$ cumplen la formula para todo $n$:

$$x_{n+1} = g(x_{n})$$
Donde $g$ es una función continua.

## Condición suficiente de convergencia
Sea $g$ una función continua y diferenciable en $[a,b]$ que satisface
1) $a \leq x \leq b \implies a \leq g(x) \leq b$
2) $\lambda := sup_{x \in [a,b]} |g'(x)| < 1$

Entonces se cumple lo siguiente
1) Existe una única solución $\alpha$ de la ecuación $x = g(x)$
2) Para cualquier valor inicial $x_{0} \in [a,b]$, la iteración $x_{n+1} = g(x_{n})$ converge a $\alpha$
3) $|a-x_{n}| \leq \frac{\lambda}{1-\lambda}|x_{0}-x_{1}|$, $n \geq 0$
4) $\lim_{ n \to \infty } \left|\frac{{\alpha-x_{n+1}}}{\alpha-x_{n}}\right| = g'(\alpha)$

Demostración de 1)
	La hipótesis 1) permite aplicar el teorema de existencia de puntos fijos y garantizar la existencia de al menos una solución. Suponiendo ahora que hay dos soluciones distintas $\alpha$ y $\beta$
	\ 
	 Suponiendo sin perdida de generalidad que $\alpha < \beta$, $g$ es continua en $[\alpha,\beta]$ y diferenciable en $(\alpha, \beta)$, por el teorema de Lagrange $\exists c \in (\alpha,\beta) : g'(c) = \frac{{g(\beta)-g(\alpha)}}{\beta-\alpha} = \frac{{\beta-a\alpha}}{\beta-\alpha} = 1$, y por lo tanto $\lambda \geq 1$, ABS!.
	 \ 
	 El absurdo proviene de suponer que existe mas de un punto fijo, por lo tanto la solución a la ecuación es única.

Demostración de 2)
	Se tiene que existe $\alpha$ tal que $\alpha = g(\alpha)$ y $x_{n+1} = g(x_{n})$, restando ambas ecuaciones se tiene que $a-x_{n+1} = g(\alpha)-g(x_{n})$
	\ 
	Por el teorema de Lagrange, $g(\alpha)-g(x_{n}) = g'(c)(\alpha-x_{n})$ para algún $c$ entre $\alpha$ y $x_{n}$
	Por lo tanto $|\alpha-x_{n+1}| = |g'(c)||\alpha-x_{n}| \leq \lambda|\alpha-x_{n}|$
	\ 
	Por inducción se puede probar que $|\alpha-x_{n+1}| \leq \lambda^{n}|\alpha-x_{0}|$
	CB) $n=0$
		Aplicando la ecuación obtenida antes para $n=1$ se tiene que $|\alpha-x_{2}|\leq \lambda|\alpha-x_{1}|$
	HI) $\forall n \in \mathbb{N} : |\alpha-x_{n+1}| \leq \lambda^{n}|\alpha-x_{0}|$
	PI)
		Aplico la ecuación del caso base para $x_{n+1}$:
		$|\alpha-x_{n+2}|\leq \lambda|a-x_{n+1}| \overset{HI}{\leq} \lambda \cdot \lambda^n|\alpha-x_{0}| = \lambda^{n+1}|\alpha-x_{0}|$
	\  
	$$\begin{rcases}
\lim_{ n \to \infty } \lambda^{n} = 0, \text{ ya que } \lambda < 1 \\
\lim_{ n \to \infty } |\alpha-x_{0}| = |\alpha-x_{0}|
\end{rcases}
	 \ \lim_{ n \to \infty } \lambda^n|\alpha-x_{0}| = 0 $$
	$0 \leq |a-x_{n+1}|\leq \lambda^{n}|a-x_{0}|$
	Por principio de intercalación, $\lim_{ n \to \infty } |\alpha-x_{n+1}| = 0$ y la interacción de punto fijo converge a $\alpha$
Demostración de 3)
	$|\alpha-x_{n}| = |\alpha-x_{1}+x_{1}-x_{0}| \leq |\alpha-x_{1}|+|x_{1}-x_{0}|$
	$|\alpha-x_{1}|+|\alpha-x_{0}| \leq \lambda|\alpha-x_{0}|+|x_{1}-x_{0}|$
	$(1-\lambda)|\alpha-x_{0}| \leq |x_{1}-x_{0}|$
	$|a-x_{0}|\leq \frac{1}{1-\lambda}|x_{1}-x_{0}|$
	\ 
	 Usando (2):
	 $|a-x_{n}| \leq \lambda^n|a-x_{0}| \leq \frac{\lambda^n}{1-\lambda}|x_{1}-x_{0}|$
Demostración de 4)
	Por Lagrange, $\frac{g(\alpha)-g(x_{n})}{\alpha-x_{n}}=\frac{{\alpha-x_{n+1}}}{\alpha-x_{n}} = g'(c)$ para $c \in [\alpha,x_{n}]$
	A medida que $n \to \infty$, $x_{n} \to \alpha$ y por lo tanto $c$ tiende a $\alpha$
	$\lim_{ n \to \infty } \frac{{\alpha-x_{n+1}}}{\alpha-x_{n}} = \lim_{ n \to \infty } g'(c) = g'(\alpha)$

### Corolarios
Suponiendo que $x=g(x)$ tiene una solución $\alpha$ y que $g(x)$ y $g'(x)$ son continuas en un entorno de $\alpha$
1) Si $|g'(\alpha)| < 1$, entonces el método converge para $x_{0}$ lo suficientemente cercano a $\alpha$.
2) Si $|g'(\alpha)|>1$ entonces el método no converge a $\alpha$.
3) Si $|g'(\alpha)| = 1$, no se pueden sacar conclusiones

Demostración de 1)
	