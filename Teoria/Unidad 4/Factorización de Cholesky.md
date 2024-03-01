Una matriz $A$ es simétrica y definida positiva sii puede factorizarse como
$$
A=R^TR
$$
Donde $R$ es una matriz triangular superior con elementos diagonales positivos, dicha factorización es única y se denomina <b>Factorización de Cholesky</b>.
## Demostración
$\implies)$
Como $A$ es simétrica, existe una matriz ortogonal $P$ tal que $A=P^TDP$, con $D$ una matriz diagonal. Al ser $A$ definida positiva la diagonal de $D$ es positiva y por lo tanto existe $\sqrt{ D }$.

Luego $A=P^TDP=P^T\sqrt{ D }\sqrt{ D }P=(\sqrt{ D }P)^T(\sqrt{ D}P)$
$D$ es simétrica al ser una matriz diagonal. Entonces se puede definir $B=\sqrt{ D }P$ donde $B$ es no singular($\det(P)\neq 0$ porque es invertible y $\sqrt{D}$ no tiene elementos diagonales negativos).

Por lo tanto $B$ posee una factorización $QR$

$A=B^TB=R^TQ^TQR=R^TR$

$\impliedby)$
Es claro que $A$ es una matriz simétrica.
Sea $(\lambda,v)$ un par autovalor-autovector:
$Av=\lambda v$
$v^TAv=v^T\lambda v$
$\lambda=\frac{{v^TAv}}{v^Tv}=\frac{{v^TR^TR v}}{v^Tv}=\frac{{\lVert Rv\rVert^{2}}}{\lVert v \rVert^{2}} > 0$, ya que como $R$ es no singular, $Rv=0 \iff v=0$ cosa que no se cumple ya que $v \neq 0$ por ser un autovector.
Como todos los autovalores son positivos, $A$ es definida positiva