![[Pasted image 20240224190543.png]]
1)
a)
Sea un sucesión $x^{(n+1)}=f(x^{(n)})$ que converge a un valor $\alpha$, se define como orden de convergencia al mínimo numero $p\geq1$ tal que:
$$
\lim_{ n \to \infty } \frac{|a-x^{(n)}|}{|a-x^{(n-1)}|^p}=\beta<\infty
$$
Se dice que el orden de convergencia es superlineal si $p>1$  o si $p=1$ y $\beta=0$
b)
El polinomio de Taylor de orden 1 centrado en $x_{0}$ es
$$
f(x)\approx f(x_{0})+(x-x_{0})f'(x_{0})
$$
Si quiero encontrar el punto $\alpha$ tal que $f(\alpha)=0$ entonces
$f(\alpha)=0\approx f(x_{0})+(\alpha-x_{0})f'(x_{0})$
Donde
$x_{0}-\frac{f(x_{0})}{f'(x_{0})}= \approx \alpha$

La aproximación de la izquierda puede usarse nuevamente para aproximar el valor de $\alpha$

El metodo de newton se define en base a la iteración:
$x_{n}-\frac{f(x_{n})}{f'(x_{n})}=x_{n+1}$

Para la orden de convergencia, el error del polinomio de Taylor en una iteración $n$ es:
$$
\frac{1}{2}(\alpha-x_{n})^{2}f''(c_{n})
$$
Donde $c$ esta entre $x_{n}$ y $\alpha$
Se tiene entonces que
$f(\alpha)=0=f(x_{n})+(\alpha-x_{n})f'(x_{n})+\frac{1}{2}(\alpha-x_{n})^{2}f''(c_{n})$
En particular, dvidiendo por $f'(x_{n})\neq 0$
$0=\frac{f(x_{n})}{f'(x_{n})}+(\alpha-x_{n})+\frac{1}{2}(a-x_{n})^{2} \frac{f''(c_{n})}{f'(x_{n})}$
$x_{n}-x_{n+1}=\frac{f(x_{n})}{f'(x_{n})}$(se deriva de la iteración del metodo). 
Por lo tanto:
$0=x_{n}-x_{n+1}+\alpha-x_{n}+\frac{1}{2}(\alpha-x_{n})^{2} \frac{f''(c_{n})}{f'(x_{n})}$
Y resulta:
$\alpha-x_{n+1}=-\frac{1}{2}(\alpha-x_{n})^{2} \frac{f''(c_{n})}{f'(x_{n})}$

$\lim_{ n \to \infty } \frac{|a-x_{n}|}{(a-x_{n})^{2}}  = \lim_{ n \to \infty } \frac{{\frac{1}{2}(\alpha -x_{n})^{2}f''(c_{n})}}{(\alpha-x_{n})^{2}f'(x_{n})}=\lim_{ n \to \infty } \frac{f''(c_{n})}{2f'(x_{n})}$
$\lim_{ n \to \infty } x_{n}=\alpha$
$\lim_{ n \to \infty } c_{n} = \alpha$($c_{n} \in (x_{n};\alpha)$)
Por lo tanto el limite anterior tiende a $\left|\frac{f''(\alpha)}{2f'(\alpha)}\right|$ y resulta $p\geq 2$

Si resulta $p>2$ entonces
$$\lim_{ n \to \infty } \frac{{|\alpha-x_{n}|}}{|\alpha-x_{n}|^p} = \lim_{ n \to \infty } \frac{f''(c_{n})}{2|\alpha-x_{n}|^{p-2}f'(x_{n})}$$
Como $\lim_{ n \to \infty } |\alpha-x_{n}|=0$, $\lim_{ n \to \infty } |a-x_{n}|^p-2=0$. Queda un limite de la forma $\frac{c}{0}$ con $c \in \mathbb{R}$ y el limite es $+\infty$. Por lo tanto la convergencia del método es cuadrática.



---
2) 
Dado el sistema de ecuaciones lineales en forma matricial $Ax=b$ con solución única, existen varios para resolver el sistema:
- Sustitución progresiva: Si $A$ es una matriz triangular inferior, se pueden resolver primero la primera ecuación del sistema y luego usar dichos resultados para resolver el resto de ecuaciones:
    Mas formalmente el primer sistema es de la forma:
    $a_{11}x_{1}=b_{1}$, cuya solución es $x_{1}=\frac{b_{1}}{a_{1}}$
    La segunda ecuación tiene la forma
    $a_{21}x_{1}+a_{22}x_{2}=b_{2}$, cuya solución es $x_{2}=\frac{1}{a_{22}}\left( b_{2}-a_{21}x_{1} \right)$
    Luego la $i$-esima ecuación tiene la forma
    $\sum_{j=1}^ia_{ij}x_{j}=b_{i}$
    Se conoce el valor de $x_{j}$ para $j=1,\dots,i-1$ ya que se obtuvo resolviendo las ecuaciones anteriores luego la solución de la $i$-esima ecuación es:
    $x_{i}=\frac{1}{a_{ii}}\left( b_{i}-\sum_{j=1}^{i-1}a_{ij}x_{j} \right)$
- Sustitución regresiva: Similar a la sustitución progresiva pero para una matriz triangular superior, aquí las ecuaciones se resuelven desde abajo hacia arriba.  
    Es decir, se resuelve primero la ultima ecuación de la forma $x_{n}=\frac{b_{n}}{a_{nn}}$ y luego dicho resultado se usa para resolver el resto de ecuaciones
- Metodo de Gauss: Este método busca convertir el sistema $Ax=b$ en un sistema $A'x=b'$ donde $A'$ es una matriz triangular superior. Luego el sistema se resuelve por sustitución regresiva.
- Método de Gauss-Jordan: Similar al método de Gauss, pero este busca conseguir 0s por arriba y por abajo de la diagonal, luego el sistema por sustitución regresiva o progresiva.
- Método de Gauss con pivoteo parcial: En el caso de que la matriz contenga un cero en la diagonal en algún paso del método de gauss, se pueden intercambiar hacer intercambios de filas para conseguir un nuevo valor $\neq 0$ en la diagonal. Para evitar errores de redondeo se suele intercambiar la fila con aquella que tenga el mayor valor absoluto
- Método de Gauss con pivoteo completo: Similar al pivoteo parcial, pero se intercambian tanto columnas como filas para conseguir un elemento $\neq 0$.
- Factorización LU: Esta factorización es útil si se requiere resolver muchos sistemas de ecuaciones donde aparece la matriz $A$. Para ello se factoriza la matriz $A$ en dos matrices $L$ y $U$ con $L$ una matriz triangular inferior y $U$ una matriz triangular superior. Luego $Ax=b$ es equivalente a $L(Ux)=b$. Dicho sistema se puede resolver primero resolviendo el sistema $Ux=y$  y luego resolver el sistema $Ly=b$.
- Factorización QR: Si $A$ es una matriz con columnas linealmente independientes entonces puede factorizarse con $A=QR$ con $Q$ una matriz triangular y $R$ una matriz triangular superior con elementos diagonales positivos. Luego el sistema $Ax=b$ es equivalente a $Q(Rx)=b$ o bien $Rx=Q^tb$ que puede resolverse con sustitución regresiva.
- Factorización de Cholesky: Si $A$ es una matriz definida positiva se puede factorizar como $A=R^tR$ con $R$ una matriz triangular superior con elementos diagonales positivos, el sistema $Ax=b$ es equivalente a $R^t(Rx)=b$. Luego se puede resolver el sistema $Rx=y$ por sustitución regresiva y el sistema $R^ty=b$ con sustitución progresiva.

---
3)
El método de integración numérica basado en polinomios interpolantes consiste en tres partes:
Suponiendo que se quiere integrar una función $f$ en un intervalo $[a;b]$
1) Se divide el intervalo en partes equidistantes, $x_{0}=a$, $x_i=a+h \cdot i$, $x_{n}=b$, $h=\frac{b-a}{n}$
2) Calcular el polinomio interpolante de grado $n$, esto puede, por ejemplo, calculando el polinomio interpolante de Lagrange:
     $L_{0}(x)=\prod_{j=2}^n \frac{{x-x_{j}}}{x_{0}-x_{j}}$, $L_{1}(x)=\prod_{j=1,j\neq 2}^n \frac{x-x_{j}}{x_{2}-x_{j}}$, $L_{i}(x)=\prod_{j=1,j\neq i} \frac{x-x_{j}}{x_{i}-x_{j}}$
     $p(x)=\sum_{i=1}^nf(x_{i})L(x)$
     $e(x)=\frac{1}{(n+1)!}\prod_{i=1}^n(x-x_{i})f^{(n+1)}(\xi(x))$
     Con $\xi(x) \in (a,b)$
3) Calcular la antiderivada del polinomio interpolante:
    $P(x)=\int _{a}^b p(x) \, dx$
4) Por la regla de Barrow, la integral numérica viene dada por $P(b)-P(a)$ y el error viene dado por $\int _{a}^be(x) \, dx$.

b)
Para el caso de un polinomio de primer grado, se tiene que $x_{0}=a$, $x_{1}=b$, $h=b-a$
$L_{0}(x)= \frac{x-x_{1}}{x_{0}-x_{1}}= \frac{x-b}{-h}$
$L_{1}(x)=\frac{x-x_{0}}{x_{1}-x_{0}}=\frac{x-a}{h}$
El polinomio interpolante viene dado por
$p(x)=f(a)\frac{x-b}{-h}+f(b)\frac{x-a}{h}$
Y el error es
$e(x)=\frac{1}{2}(x-a)(x-b)f''(\xi(x))$

$\int _{a}^b p(x)\, dx=\frac{f(a)}{-h}\int_{a}^b x-b \, dx+\frac{f(b)}{h}\int _{a}^bx-a \, dx$
$\int _{a}^b x-b \, dx=\int _{a-b}^0u \, du=\left. \frac{1}{2}u^{2} \right|^0_{-h}=-\frac{1}{2}h^{2}$
$\int _{a}^b x-a \, dx=\int _{0}^{b-a}u \, du=\left.\frac{1}{2}u^{2}\right|_{0}^h=\frac{1}{2}h^{2}$
Por lo tanto la integral del polinomio interpolante queda como: $\frac{h}{2}\left( f(a)+f(b) \right)$

$\int_{a}^b e(x) \, dx=\frac{1}{2}\int _{a}^b(x-a)(x-b)f''(\xi(x)) \, dx$
Por el teorema del valor medio de las integrales:
$\frac{1}{2}f''(c)\int _{a}^b(x-a)(x-b) \, dx=\frac{1}{2}f''(c)\int_{0}^{b-a}u(u-h)  \, dx$
$\frac{1}{2}f''(c)\int _{0}^h \left( u^{2}-hu \right) \, dx=\frac{1}{2}f''(c)\left.  \frac{1}{3}u^{3}-\frac{1}{2}hu^{2} \right|_{0}^h=-\frac{1}{2}f''(c)\frac{1}{6}h^{3}$
$=-\frac{1}{12}f''(c)h^{3}$
