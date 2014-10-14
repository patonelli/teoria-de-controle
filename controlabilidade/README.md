# Controlabilidade de Sistemas Lineares

Consideremos duas matrizes $$A \in \mathbb{M}_{n\times n}$$ e $$ B \in \mathbb{M}_{n\times m}$$, que define um sistema de controle linear dado pela dinâmica
$$ \dot{x}(t) = Ax(t) + Bu(t) $$
com $$u(\cdot)$$ no espaço vetorial de funções $$\mathcal{U} =\{ u:\mathbb{R} \to \mathbb{R}^m \}$$ localmente integráveis.
A solução desse sistema que no instante $$t_0$$ passa por $$x_0$$ é:
$$\varphi(t,t_0,x_0,u(\cdot))= \text{e}^{(t-t_0)A}x_0 + \int_{t_0}^t\text{e}^{(t-s)A}Bu(s)ds$$

O conjunto
$$ \mathcal{A}(t,t_0,x_0) = \{x\in \mathbb{R}^n: (\exists u(\cdot) \in \mathcal{U}) \wedge (x = \varphi(t,t_0,x_0,u(\cdot)))\} $$
Este conjunto chamaremos de *conjunto de controlabilidade*. Queremos condições sobre o par de matrizes $$(A,B)$$ para que este conjunto seja todo espaço de estados $$\mathbb{R}^n$$, e neste caso diremos que o par $$(A,B)$$, ou o sistema seja controlável.

### Primeiras observações sobre $$\mathcal{A}(t,t_0,x_0)$$

* $$\mathcal{A}(t,t_0,x_0) = \text{e}^{(t-t_0)A}x_0 + \{ \int_{t_0}^t\text{e}^{(t-s)A}Bu(s)ds : u(\cdot) \in \mathcal{U}\} = \text{e}^{(t-t_0)A}x_0 +\mathcal{A}(t,t_0,0).$$

* $$\mathcal{A}(t,t_0,0)= \text{Im}\mathcal{L}.$$
* onde $$\mathcal{L}$$ é o operador linear
$$ \begin{gather}\mathcal{L}:\mathcal{U} \to \mathbb{R}^n \\
\mathcal{L}(u(\cdot))=\int_{t_0}^t\text{e}^{(t-s)A}Bu(s)ds
\end{gather}$$

* Assim o par $$(A,B)$$ é controlável se, e somente se, $$\text{Im}\mathcal{L}=\mathbb{R}^n$$

### Exemplo:
Podemos reescrever a equação $$\ddot{x}(t) = u(t)$$ como:
$$\begin{pmatrix}\dot{x} \\ \dot{y} \end{pmatrix}=\begin{pmatrix}0 & 1 \\ 0 & 0 \end{pmatrix}\begin{pmatrix} x \\ y \end{pmatrix} + \begin{pmatrix} 0 \\ 1 \end{pmatrix} u(t) $$
Pode-se verificar facilmente que
$$ \text{e}^{(t-t_0)A} = \begin{pmatrix} 1 & t-t_0 \\ 0 & 1\end{pmatrix} \text{ e } \mathcal{L}(u) = \begin{pmatrix} \int_{t_0}^t(t-s)u(s) ds \\ \int_{t_0}^t u(s) ds \end{pmatrix}$$

Dado um ponto $$(x_0,y_0)$$ qualquer de $$\mathbb{R}^n$$ e tomando um controle da forma $u(t) =at + b$, então podemos resolver o sistema:
$$ \begin{eqnarray}
a \int_{t_0}^t (t-s)sds + b \int_{t_0}^t(t-s)ds & = & x_0 \\
a \int_{t_0}^ts ds  + b \int_{t_0}^t ds&=& y_0
\end{eqnarray}$$
para mostrar que este par de matrizes é controlável.

#### Exercício:
verifique que o par de matrizes $$(A,B)$$ com:
$$ A = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix} \text{ e } B= \begin{pmatrix} 1 \\ 0 \end{pmatrix}$$
não é controlável.

