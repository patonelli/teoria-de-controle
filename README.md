# Métodos Matemáticos em controle

Em praticamente todos os sistemas da natureza há a possibilidade de intervenção que permite exercer algum controle sobre o sistema. Aspectos tecnológicos nos fazem procurar uma forma de exercer este controle automaticamente. É o que chamaremos de retroalimentação do sistema.

Basicamente a origem da teoria de controle são os sistemas de regulagem, isto é, procura-se desenvolver um processo automático para que um sistema fique numa situação de equilíbrio. Assim um sensor detecta se o sistema está se desregulando e um controlador atuaria automaticamente para restabelecer o equilibrio. Claro que muitos mecanismos engenhosos foram desenvolvidos durante milênios para resolver este problema, porém um caso interessante era o de controle de velocidade de moinhos de vento. Huygens inventou um instrumento conhecido como *flyball* que na pratica resolvia o problema.
Esta mesma idéia do [flyball](http://en.wikipedia.org/wiki/Centrifugal_governor) foi usada depois por Watt em máquinas  para o controle de fluxo de vapor.
Este modelo que funcionava na prática tinha um problema de excesso de vibração para velocidades muito altas. Foi Maxwell quem
elaborou um modelo matemático para o flyball e colocou o problema de eliminação das vibrações como um problema de estabilização. Este foi, pode-se dizer, o primeiro problema matemático da teoria de controle.

No começo do século XX, o desenvolvimento das redes de comunicações telefônicas, propiciou o aparecimento de novos modelos e a utilização de métodos da teoria de funções a variáveis complexas para eliminação de ruídos e filtragens de sinais. Os trabalhos pioneiros nesta linha deveu-se a [Stephen Black](http://en.wikipedia.org/wiki/Harold_Stephen_Black), [Hendrik Bode](http://en.wikipedia.org/wiki/Hendrik_Wade_Bode) e [Harry Nyquist](http://en.wikipedia.org/wiki/Harry_Nyquist) do grupo do laboratório Bell. O conjunto de métodos desenvolvidos por eles influenciou bastante a engenharia e é chamado de teoria de controle clássica.
Isso foi mais ou menos em 1930. Depois da segunda guerra mundial os métodos de otimização ganharam importância e é um mérito da teoria de [Lev Pontriaguin](http://en.wikipedia.org/wiki/Lev_Pontryagin)  o estudo da teoria de controle ótimo. O desenvolvimento da teoria de sistemas dinâmicos propiciou uma nova abordagem para os sistemas de controles lineares. Assim nas décadas de 1960 e 1970 desenvolveu-se bastante uma teoria estrutural dos sistemas de controle. E nesta abordagem "moderna" baseada no espaço de estados dos sistemas são importantes os conceitos de controlabilidade e observabilidade introduzidos por Kalman. No final do século passado desenvolveram-se os métodos geométricos para o estudo de sistema de controle não linear. Em todos estes tópicos há ainda pesquisa bastante ativa.

### Exemplos
#### Um satélite simples num campo newtoniano
![satelite](http://wiki.stoa.usp.br/images/d/d1/Satelite.png "satélite em campo newtoniano")

Uma partícula de massa $$m$$ está sob ação de um campo de acelerações central newtoniano. Além disso podemos colocar dois controles independentes, um na direção radial e outro na direção tangencial $$u_{r}$$
e $$u_{\theta}$$ respectivamente. A equação dinâmica deste sistema é dada pela segunda lei de Newton:
$$m\ddot{\mathbf{r} }=(-\frac{k}{r^2}+u_r)\mathbf{e}_r + u_{\theta} \mathbf{e}_{\theta}$$
fazendo a massa $$m=1$$ para que eu não tenha que ficar digitando coisas a mais. Podemos reecrever as equações em coordenadas polares como:

$$\ddot{r} = r\dot{\theta}^2-\frac{k}{r^2}+u_r$$

$$r\ddot{\theta}= -2\dot{r}\dot{\theta} + u_{\theta}$$

Estas duas equações nos dão um sistema de controle não linear com duas entradas de controle. Voltaremos a este exemplo quando falarmos de linearização.
#### Pêndulo invertido
![Pêndulo Invertido](http://wiki.stoa.usp.br/images/b/b6/Cart-pendulum.png)


O [Pêndulo invertido](http://en.wikipedia.org/wiki/Inverted_pendulum) é um problema clássico em teoria de controle, as equações do movimento são:
$$
\left ( M + m \right ) \ddot x - m l \ddot \theta \cos \theta + m l \dot \theta^2 \sin \theta = F $$

$$m l (-g \sin \theta - \ddot x \cos \theta + l \ddot \theta) = 0 $$
A variável de controle aqui é a força $$F$$
