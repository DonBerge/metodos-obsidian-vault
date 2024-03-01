Se define el polinomio de Chebyshev de grado $n$ como
$$T_{n}(x) = \cos(n \times acos(x))$$
## Demostración de que Tn es un polinomio 
Por inducción en $n$
CB) $n=0$
$T_{0}(x)=\cos(0\times acos(x))=\cos(0)=1$, un polinomio de grado $1$
PI)
$T_{n+1}(x)=\cos((n+1)\times acos(x))=\cos(n\times acos(x)+acos(x))$
$=\cos(n\times acos(x))\cos(acos(x))-\sin(\cos(x) \times acos(x))\sin(acos(x))$
$T_{n-1}(x)=\cos((n-1)\times acos(x))=\cos(n\times acos(x)-acos(x))$
$=\cos(n\times acos(x))\cos(acos(x))+\sin(\cos(x)\times acos(x))\sin(acos(x))$

Sumando ambas expresiones queda:
$T_{n+1}(x)+T_{n-1}(x)=2\cos(n\times acos(x))\cos(acos(x)) = 2x \cdot T_{n}(x)$

Y queda la siguiente relación de recurrencia:
$T_{n+1}(x)=2xT_{n}(x)-T_{n-1}(x)$

Y por inducción, $T_{n+1}(x)$ es un polinomio de grado $n$

## Propiedades de los polinomios de Chebyshev
1) $|T_{n}(x)| \leq 1$, $-1\leq x\leq 1$:
	 Por inducción en $n$:
	 CB) $n=1$
	  $T_{0}(x)=1$ 
	 PI)
	  $|T_{n+1}(x)| = |2xT_{n}(x)|+|T_{n-1}(x)|$
2) $T_{n}(x)=2^{n-1}x^n+\dots$
	 Por inducción en $n$:
	 CB) $n=1$
	  $T_{1}(x)=x=2^0x^{1}$
	 PI)
	  En la formula de recurrencia, el termino de mayor grado esta determinado por el primer termino  de la recurrencia, al multiplicarse ese termino por $2x$, se consigue la formula que se quiere demostrar
3) Raíces de los polinomios de Chebyshev:
	 $T_{n}(x)=0 \iff \cos(n\times acos(x))=0 \iff \frac{(2k+1)\pi}{2n}=acos(x) \iff x=\cos\left( \frac{(2k+1)\pi}{2n} \right)$ para $0\leq k\leq n-1$

## Error de interpolación por Chebyshev
Lo ideal al tratar de aproximar la función $f$ en un intervalo $[a;b]$ por un polinomio $p$ es minimizar el error de interpolación en el intervalo
$$E(p)=\min_{x \in [a;b]}|f(x)-p(x)|$$

