Dados los puntos de interpolación $(x_{i},y_{i})$, se definen las funciones
$$L_{k}(x)=\prod_{i=0,i\neq k}^n \frac{{x-x_{i}}}{x_{k}-x_{i}}$$
Se define el polinomio $p(x)$
$$p(x)=\sum_{k=0}^nL_{k}(x)y_{k}$$
Se tiene que si para un cierto $i$ y un cierto $k$:
$$\begin{matrix}
L_{k}(x_{i})=0, & i\neq k \\
L_{k}(x_{i})=1, & i =k 
\end{matrix}$$
Y por lo tanto $p(x_{i})=y_{i}$
Como cada uno de los polinomios $L_{k}(x)$ tienen grado menor o igual $n$, el polinomio interpolante tiene grado $n$ y por lo tanto es único.