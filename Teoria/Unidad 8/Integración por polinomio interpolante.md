Por interpolación de Lagrange se tiene que
$$f(x)=p(x)+\frac{{\Phi_{n}(x)}}{(n+1)!}f^{(n)}(\xi(x))$$
Donde
$$
\begin{matrix}
p(x)=\sum_{i=1}^n f(x_{i})L_{i}(x), &  
\Phi_{n}(x)=\prod_{i=1}^n(x-x_{i}), & 
L_{i}(x)=\prod_{j=1,j\neq i}^n \frac{x-x_{j}}{x_{i}-x_{j}}
\end{matrix}
$$
Integrando el lado derecho queda como:
$$
\int_{a}^b p(x) \, dx + \frac{1}{(n+1)!}\int_{a}^b \Phi_{n}(x)f^{(n)}(\xi(x)) \, dx 
$$
---
