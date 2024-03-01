La regla de Simpson usa un polinomio interpolante de grado 2
$$
f(x)=f(x_{0})L_{0}(x)+f(x_{1})L_{1}(x)+f(x_{2})L_{2}(x)+\frac{\Phi_{2}(x)}{6}f'''(\xi(x))
$$
## Integración del polinomio interpolante
Por simplicidad tomo $b=a+2h$
$\int _{a}^b L_{0}(x) \, dx=\int_{a}^b \frac{x-a-h}{a-(a+h)} \frac{x-a-2h}{a-(a+2h)} \, dx=\int _{a}^b \frac{{x-a-h}}{-h} \frac{{x-a-2h}}{-2h} \, dx$
Sustitución: $u=\frac{x-a}{2}$, $dx=2du$
$x-a-h=2u-h$
$x-a-2h=2u-2h$
La integral anterior queda como:
$\int_{0}^h \frac{1}{h^{2}}(2u-h)(2u-2h) \, dx$
$=\frac{1}{h^2}\int _{0}^h4u^{2}-6hu+2h^{2} \, dx=\frac{1}{h^{2}} \left( \frac{4}{3}h^{3} -3h^{3}+2h^{3}\right)=\frac{1}{3}h$

$\int_{a}^b L_{1}(x) \, dx = \int _{a}^b \frac{{x-a}}{a+h-a} \frac{{x-a-2h}}{a+h-a-2h} \, dx=\int _{a}^b \frac{{x-a}}{h} \frac{{x-a-2h}}{-h} \, dx$
Sustitución: $u=\frac{{x-a}}{2}$
$dx=2du$
$x-a=2u$
$x-a-2h=2u-2h$
La integral anterior queda como:
$\frac{2}{-h^{2}}\int_{0}^h 2u(2u-2h)\, dx=-\frac{2}{h^{2}}\int _{0}^h 4u^{2}-4hu \, dx=-\frac{2}{h^{2}}\left( \frac{4}{3}h^{3}-2h^{3} \right)$
$=\frac{4}{3}h$

$\int _{a}^bL_{2}(x) \, dx=\int _{a}^b \frac{x-a}{a+2h-a} \frac{x-a-h}{a+2h-a-h} \, dx=\int _{a}^b \frac{x-a}{2h} \frac{x-a-h}{h} \, dx$
Sustitución: $u=\frac{x-a}{2}$
$dx=2du$
$x-a=2u$
$x-a-h=2u-h$
La integral anterior queda como:
$\frac{1}{h^{2}} \int _{0}^h 2u(2u-h) \, dx=\frac{1}{h^{2}} \int _{0}^h 4u^{2}-2hu \, dx = \frac{1}{h^{2}}\left( \frac{4}{3}h^{3}-h^{3} \right) = \frac{1}{3}h$

Juntando todas las integrales queda:
$\int _{a}^b p(x) \, dx =\frac{1}{3}h \cdot f(x_{0})+\frac{4}{3}h \cdot f(x_{1})+\frac{1}{3}h \cdot f(x_{2})$
$=\frac{h}{3}\left( f(x_{0})+4f(x_{1})+f(x_{2}) \right)$
