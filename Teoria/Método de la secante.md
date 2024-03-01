El método de newton utiliza la interacción de punto fijo:
$$x_{n+1}=x_{n}-\frac{f(x_{n})}{f'(x_{n})}$$
Donde $x_{0}$ es una aproximación inicial.
La derivada $f'(x_{0})$ se define como
$$f'(x_{0})=\lim_{ x \to a } \frac{{f(x)-f(x_{0})}}{x-x_{0}}$$
Tomando $a=x_{1}$ otra aproximación inicial se tiene la siguiente aproximación
$$f'(x_{0}) = \frac{{f(x_{1})-f(x_{0})}}{x_{1}-x_{0}}$$
Y se puede reemplazar la iteración del método de newton con
$$x_{2}=x_{1}-f(x_{1}) \frac{{x_{1}-x_{0}}}{f(x_{1})-f(x_{0})}$$
Y en forma general:
$$x_{n+1}=x_{n}-f(x_{n}) \frac{{x_{n}-x_{n-1}}}{f(x_{n})-f(x_{n-1})}$$
