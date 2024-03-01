Suponiendo que $x=g(x)$ tiene solución $\alpha$ y que $g(x)$ y $g'(x)$ son continuas en un entorno de $\alpha$, luego:
1) Si $\left| g'(\alpha) \right| <1$, la iteración $x_{n+1}=g(x_{n})$ converge para $x_{0}$ lo suficientemente cercano a $\alpha$
2) Si $\left| g'(\alpha) \right|>1$, la iteración $x_{n+1}=g(x_{n})$ no converge a $\alpha$
3) Si $|g'(\alpha)|=1$, no se pueden sacar conclusiones

## Demostración
1)
$g'(x)$ es continua en un entorno de $\alpha$ y $|g'(a)|\leq 1$, por lo tanto existe un entorno de $\alpha$ donde $|g'(x)|\leq 1$ 

Suponiendo que $x_{n}$ pertenece a dicho entorno, $g$ es continua y derivable en $[\alpha;x_{n}]$ por lo tanto por el teorema de Lagrange, $\exists c_{n} \in [\alpha;x_{n}] : g'(c_{n})= \frac{g(\alpha)-g(x_{n})}{\alpha-x_{n}}$, $g(\alpha)=\alpha$ y $g(x_{n})=x_{n+1}$ por lo tanto se tiene que $\alpha-x_{n+1}=g'(c_{n})(\alpha-x_{n})$

Por lo tanto $|\alpha-x_{n+1}|=|g'(c_{n})(\alpha-x_{n})|=|g'(c_{n})|\cdot|\alpha-x_{n}|\leq 1\cdot |\alpha-x_{n}|=|\alpha-x_{n}|$
Se tiene que $|\alpha-x_{n+1}|\leq|\alpha-x_{n}|$, esto es, $x_{n+1}$ esta mas cerca de $\alpha$ que de lo que esta $x_{n}$. Por lo tanto el método converge para $x_{0}$ lo suficientemente cercano a $\alpha$

2)
De la misma forma, si $g'(x)$ es continua en un entorno de $\alpha$ y $|g'(\alpha)|\geq 1$ existe un entorno de $\alpha$ donde $|g'(x)|\geq 1$
Luego se tiene que $|\alpha-x_{n+1}|=|g'(c_{n})||\alpha-x_{n}|\geq|\alpha-x_{n}|$, es decir, $x_{n+1}$ esta mas lejos de $\alpha$ que $x_{n}$ y por lo tanto el metodo no converge.
