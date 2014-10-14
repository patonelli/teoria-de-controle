# Gramiano de Controlabilidade

## A Matriz de Controlabilidade
Antes de mais nada vamos tratar de uma propriedade importante de nossos sistemas lineares: a invariância no tempo. Isto se reflete na seguinte propriedade da função de transição de estados:

$$ \varphi(t,t_0,x_0,u(\cdot)) = \varphi(t-t_0,0,x_0, v(\cdot))$$
onde $$v(t) = u(t+t_0)$$.
Para ver isto basta analisar a parte controlada do sistema. A parte controlada de $$\varphi(t,t_0,x_0,u(\cdot))$$ é
$$ \begin{gather} \int_{t_0}^t \text{e}^{(t-s)A}Bu(s)ds = \int_{0}^{t-t_0}\text{e}^{(t-t_0 -r)A}Bu(r+t_0)dr
\end{gather}$$
Desta forma para estudarmos a controlabilidade de nosso caso linear basta estudar o conjunto:
$$ \mathcal{A}(T) = \left\{ \int_0^T \text{e}^{(T-s)A}Bu(s)ds: u(\cdot) \in \mathcal{U}\right\} =\left\{ \int_0^T \text{e}^{sA}Bu(T-s)ds: u(\cdot) \in \mathcal{U}\right\}$$

## Gramiano de controlabilidade

Para um $$T>0$$, definimos o *Gramiano de controlabilidade* como a matriz simétrica:
$$Q_T = \int_0^T \text{e}^{sA}BB^\prime\text{e}^{sA^\prime}ds $$
Nesta fórmula $$A^\prime$$ é a transposta da matriz $$A$$.


## exercícios:
Calcular os gramianos de controlabilidade nos casos

* $$A=\begin{pmatrix}0&1 \\ 0 & 0\end{pmatrix}\text{ e } B=\begin{pmatrix} 0 \\ 1 \end{pmatrix}$$

* $$A=\begin{pmatrix}1&1 \\ 0 & 1\end{pmatrix}\text{  e }B=\begin{pmatrix} 1\\ 0 \end{pmatrix}$$

*Teorema:* O par $$(A,B)$$ é controlável se, e somente se, o gramiano $$Q_T$$ é inversível.

Primeiro suponha que $$Q_T$$ é inversível e seja $$x_1$$ um ponto qualquer do espaço de estados $$\mathbb{R}^n$$. Definimos o controle admissível:
$$ u(s) = B^\prime\text{e}^{(T-s)A^\prime}Q_Tx_1 $$
e verificamos que  $$\mathcal{L}(u(\cdot)) = x_1$$.

Agora suponha que $$Q_T$$ não seja inversível, e que $$x_2 \in \mathbb{R}^n$$ seja um elemento não nulo do núcleo $$\text{Ker}Q_T$$. Em particular vale:
$$ \begin{gather}\langle Q_Tx_2, x_2 \rangle = \int_0^T \langle \text{e}^{sA}BB^\prime\text{e}^{sA^\prime}x_2,x_2\rangle ds =0 \\
\int_0^T \| B^\prime\text{e}^{sA^\prime}x_2\|^2 ds=0 \implies B^\prime\text{e}^{sA^\prime}x_2 =0 \forall s \in [0,T]\end{gather}$$

Por outro lado, para todo $$u(\cdot) \in \mathcal{U}$$, tem-se que $$\langle \mathcal{L}(u(\cdot)), x_2 \rangle $$ pode ser
calculado:
$$ \begin{gather}
\langle \mathcal{L}(u(\cdot)), x_2 \rangle = \int_0^T\langle \text{e}^{(T-s)A}Bu(s),x_2\rangle ds = \int_0^T\langle u(s), B^\prime \text{e}^{(T-s)A^\prime}x_2\rangle ds =0
\end{gather}$$
O que significa que $$x_2$$ é ortogonal a $$\text{Im}\mathcal{L}$$ e o par $$(A,B)$$ não é controlável.


