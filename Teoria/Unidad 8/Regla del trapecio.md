La regla del trapecio integra el intervalo $[a,b]$ usando el polinomio interpolante de grado $1$
$$x_{0}=a,x_{1}=b,h=b-a$$
El polinomio interpolante es:
$$p(x)=f(x_{0})L_{0}(x)+f(x_{1})+L_{1}(x)=f(x_{0}) \frac{{x-x_{1}}}{x_{0}-x_{1}}+f(x_{1}) \frac{{x-x_{0}}}{x_{1}-x_{0}} = \frac{{f(x_{0})-f(x_{1})}}{x_{0}-x_{1}}x$$Luego
$$
\int _{a}^b f(x) \, dx = \int _{a} ^ b p(x)\, dx +\frac{1}{2} \int _{a} ^b f''(\xi(x))(x-x_{0})(x-x_{1}) \, dx   \tag{1}
$$
---
## Integración del polinomio interpolante
$\int_{a}^b f(a) \frac{x-b}{a-b} \, dx = \int _{a}^b \frac{f(a)}{-h}(x-b) \, dx\overset{\text{Sustitucion u=x-b}}{=}\int _{a-b}^{0}-\frac{f(a)}{h}u \, du$
$\int _{-h}^{0}-\frac{f(a)}{h}u \, du=\left. -\frac{f(a)}{2h}u^{2} \right|_{-h}^{0}=\frac{f(a)}{2}h$

$\int _{a}^b f(b) \frac{x-a}{b-a} \, dx=\int _{a}^{b} \frac{f(b)}{h}(x-a) \, dx\overset{Sustitucion u=x-a}{=}\int _{0}^{b-a} \frac{f(b)}{h}u \, du=\int _{0}^h \frac{f(b)}{h} u \, dh$
$=\left. \frac{f(b)}{2h}u^{2} \right|^h_{0}=\frac{f(b)}{2}h$

Por lo tanto la integral definida del polinomio interpolante es $\frac{h}{2}\left[ f(a)+f(b) \right]$

---
## Integración del error
Se tiene el siguiente teorema:
<u>Teorema del valor medio para integrales:</u> Sea $g(x)$ una función que no cambia de signo e integrable en el intervalo $[a;b]$ y $f(x)$ una función continua de $[a,b]$ entonces existe $c \in[a,b]$ tal que:
$$
\int _{a} ^b g(x)f(x)\, dx =f(c)\int_{a}^b g(x) \, dx  
$$
$f''(\xi(x))$ es una función continua y derivable(esto se sabe porque cumple las hipótesis del teorema de error de interpolación polinómica). Como $a\leq x \leq b$, $(x-a)(x-b)$ es siempre no positiva y por lo tanto se puede aplicar el teorema para (1)

$$
\int _{a} ^b f''(\xi(x))(x-x_{0})(x-x_{1}) \, dx = f''(c)\int_{a}^b (x-a)(x-b) \, dx
$$
$$\int _{a}^bx^{2}-(a+b)x+ab \, dx=\left.\frac{1}{3}x^{3}-\frac{{a+b}}{2}x^{2}+ab \cdot x\right|_{a}^b =\frac{b^{3}-a^{3}}{3}-\frac{{a+b}}{2}\left( b^{2}-a^{2} \right)+ab(b-a) 
$$
$$
=\frac{b^{3}}{3}-\frac{{b^{2}a}}{2}+\frac{{ba^{2}}}{2}-\frac{a^{3}}{3}-\frac{b^{3}}{2}+\frac{a^{3}}{2}+b^{2}a-ba^{2}
$$
$$
=-\frac{b^{3}}{6}+\frac{{b^{2}a}}{2}-\frac{ba^{2}}{2}+\frac{a^{3}}{6}=-\frac{1}{6}\left( b^{3}-3b^{2}a+3ba^{2}-a^{3} \right) = -\frac{(b-a)^3}{6}=-\frac{h^{3}}{6} 
$$
Por lo tanto la integral anterior queda como $-f''(c) \frac{h^{3}}{6}$

---
### Integral final
Sustituyendo en (1) las integrales anteriores la regla queda como:
$$
\int _{a}^b f(x)\, dx=\frac{h}{2}\left[ f(a)+f(b) \right] - \frac{h^{3}}{12} f''(c)  
$$
Con $c \in[a;b]$
