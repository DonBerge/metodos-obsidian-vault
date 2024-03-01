Si $N \in \mathbb{R}^{n\times n}$ es no singular entonces
$Ax=b \implies Ax-b=0$
$Nx=Nx \implies Nx =Nx-0 \implies Nx=Nx-Ax+b$

El proceso iterativo es de la forma:
$$
N\mathbf{x}^{(n+1)}=(N-A)\mathbf{x}^{(n)}-b
$$
O bien:
$$
\mathbf{x}^{(n+1)}=(I-N^{-1}A)\mathbf{x}^{(n)}+N^{-1}b
$$
## Condiciones de convergencia
Si $\lVert I-N^{-1}A\rVert < 1$, el metodo iterativo converge para cualquier vector inicial

<u>Demostración:</u>
	Sea $\mathbf{x}$ tal que $A\mathbf{x}=b$
	$(I-N^{-1}A)\mathbf{x}+N^{-1}b=\mathbf{x}-N^{-1}b+N^{-1}\mathbf{x}=\mathbf{x}$
	\ 
	Sea el error $\mathbf{e}^{(k)}=\mathbf{x}-\mathbf{x^{(k)}}$
	$\mathbf{e}^{(k+1)}=\mathbf{x}-\mathbf{x^{(k+1)}}=(I-N^{-1}A)\mathbf{x}+N^{-1}b-(I-N^{-1}A)\mathbf{x}^{(n)}-N^{-1}b$
	$\mathbf{e}^{(k+1)}=(I-N^{-1}A)e^{(k)}$
	\ 
	Luego se tiene que $e^{(k+1)}=(I-N^{-1}A)e^{(0)}$
	$\lim_{ n \to \infty }\mid\mid\mathbf{e}^{(n)}\mid\mid=\mid\mid (I-N^{-1}A)^ne^{(0)}\mid\mid \leq \mid\mid (I-N^{-1}A)^n\mid\mid \cdot\mid\mid e^{(0)}\mid\mid=0$
	