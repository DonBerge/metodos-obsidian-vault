Es una combinación del método de la bisección y el método de la secante que se usa para encontrar el valor $\alpha$ tal que $f(\alpha)=0$

Se elijen $a_{0}$ y $b_{0}$ tal que $f(a_{0})f(b_{0})\leq 0$
1) Se calcula $c_{n}$ usando el método de la secante, $c_{n}=b_{n}-f(b_{n}) \frac{b_{n}-a_{n}}{f(b_{n})-f(a_{n})}$
2) 
	- Si $sgn(f(a_{n}))=sgn(f(c_{n}))$, $a_{n+1}=c_{n}$ y $b_{n+1}=b_{n}$
	- Si $f(sgn(b_{n}))=f(sgn(c_{n}))$, $a_{n+1}=a_{n}$ y $b_{n+1}=c_{n}$
	- Si $f(c_{n})=0$, $\alpha=c_{n}$
