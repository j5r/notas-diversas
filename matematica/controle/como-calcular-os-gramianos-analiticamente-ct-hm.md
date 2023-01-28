<script>MathJax = {tex: {inlineMath: [['$', '$']]}, svg: {fontCache: 'global'}};</script>
<script type="text/javascript" id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js"> </script>

# Resolvendo analiticamente os gramianos

Considere o seguinte sistema

$$
\left\{
\begin{aligned}
x(t)&=A_{\theta(t)}x(t)+B_{\theta(t)}u(t)+H_{\theta(t)}w(t)\\\\
y(t)&=C_{\theta(t)}x(t)+D_{\theta(t)}u(t)\\\\
u(t)&=F_{\eta(t)}x(t),\\\\
\theta(t)&\in\mathcal{N}=\\{1,...,N\\},\\\\
\eta(t)&\in\mathcal{M}=\\{1,...,M\\},\\\\
x(t)&\in\Re^n,\\;\\;t\ge0,
\end{aligned}
\right.
$$

com $C_i'D_i=0$ com $D_i'D_i>0$.

A cadeia de Markov $ \\{ \theta(t),t\ge0 \\} $ tem matriz de transição dada por $\Lambda=[\lambda_{ij}]$ e o processo observado é $\\{\eta(t),t\ge0 \\}$. O processo conjunto $Z(t)=(\theta(t),\eta(t))$ é tal que, para $h>0$ pequeno,

$$
Prob(Z(t+h)=(j,\ell)\mid Z(t)=(i,k)) =
\begin{cases}
\nu_{ik,j\ell} h + o(h), & (ik)\neq (j\ell),\\\\
1 + \nu_{ik,j\ell} h + o(h) & (ik) = (j\ell),
\end{cases}
$$

onde se tem as taxas $\nu_{ik,j\ell}$ para cada $(ik),(j\ell)\in\mathcal{N}\times \mathcal{M}$ dadas por

$$
\nu_{ik,\,j\ell}=
\begin{cases}
\alpha^k_{j\ell} \lambda_{ij}, & i\neq j,\\\\
q^i_{k\ell}, & i=j, \ell\neq k,\\\\
\lambda_{ii}+q_{kk}^i, & (ik)=(j\ell).
\end{cases}
$$

As matrizes de malha fechada são

$$\hat{A}\_{ik}=A\_i+B\_iF\_k\qquad\mbox{ e }\qquad\hat{C}\_{ik}=C\_i+D\_iF\_{ik},\quad \forall\\; (ik)\in\mathcal{N}\times\mathcal{M}$$

e definimos $\mathcal{O}\_{ik}=\hat{C}\_{ik}'\hat{C}\_{ik}$, para cada $(ik)\in\mathcal{N}\times\mathcal{M}$.

Denote por $I_{(m)}$ a matriz identidade de ordem $m$, $\otimes$ o produto de Kronecker, e $\text{vec}(X)$ o operador de vetorização (empilhamento das colunas de X).

## Gramiano de Observabilidade

Considere o operador $\mathcal{T}_{ik}(P)$, para cada $(ik)\in\mathcal{N}\times\mathcal{M}$, dado por

$$
\mathcal{T}\_{ik}(P) = \hat{A}\_{ik}'P\_{ik} + P\_{ik}\hat{A}\_{ik} +
\sum\_{j\in\mathcal{N}} \sum\_{\ell\in\mathcal{M}} \nu\_{ik,j\ell} P\_{j\ell}
$$

A solução $P=\\{P_{j\ell},j\in\mathcal{M},\ell\in\mathcal{M}\\}$ da equação

$$
\mathcal{T}\_{ik}(P) + \mathcal{O}\_{ik} = 0
$$

é o gramiano de observabilidade.

Para resolvê-lo analiticamente, escrevemos o seguinte sistema de equações lineares, nas variáveis $P_{j\ell}$.

$$
\scriptsize
\begin{split}
&\left\{
  \begin{bmatrix}
  I_{(n)}\otimes \hat{A}\_{11}'\\\\
  &...\\\\
  &&I_{(n)}\otimes \hat{A}\_{1M}'\\\\
  &&&I_{(n)}\otimes \hat{A}\_{21}'\\\\
  &&&&...\\\\
  &&&&&I_{(n)}\otimes \hat{A}\_{2M}'\\\\
  &&&&&&...\\\\
  &&&&&&&I_{(n)}\otimes \hat{A}\_{NM}'
  \end{bmatrix}
\right.\\\\[8pt]
&+\begin{bmatrix}
\hat{A}\_{11}\otimes I_{(n)}\\\\
  &...\\\\
  && \hat{A}\_{1M}\otimes I_{(n)}\\\\
  &&& \hat{A}\_{21}\otimes I_{(n)}\\\\
  &&&&...\\\\
  &&&&& \hat{A}\_{2M}\otimes I_{(n)}\\\\
  &&&&&&...\\\\
  &&&&&&& \hat{A}\_{NM}\otimes I_{(n)}
\end{bmatrix}\\\\[8pt]
&+\left.
  \begin{bmatrix}
\begin{bmatrix}
\nu\_{11,11},&\nu\_{11,12},&...,&\nu\_{11,1M},&\nu\_{11,21},&...,&\nu\_{11,2M},&...,&\nu\_{11,NM}\end{bmatrix}
\otimes I_{(n^2)}\\\\
\begin{bmatrix}\nu\_{12,11},&\nu\_{12,12},&...,&\nu\_{12,1M},&\nu\_{12,21},&...,&\nu\_{12,2M},&...,&\nu\_{12,NM}\end{bmatrix}
\otimes I_{(n^2)}\\\\
\vdots \\\\
\begin{bmatrix}\nu\_{1M,11},&\nu\_{1M,12},&...,&\nu\_{1M,1M},&\nu\_{1M,21},&...,&\nu\_{1M,2M},&...,&\nu\_{1M,NM}\end{bmatrix}
\otimes I_{(n^2)}\\\\
\begin{bmatrix}\nu\_{21,11},&\nu\_{21,12},&...,&\nu\_{21,1M},&\nu\_{21,21},&...,&\nu\_{21,2M},&...,&\nu\_{21,NM}\end{bmatrix}
\otimes I_{(n^2)}\\\\
\vdots \\\\
\begin{bmatrix}\nu\_{2M,11},&\nu\_{2M,12},&...,&\nu\_{2M,1M},&\nu\_{2M,21},&...,&\nu\_{2M,2M},&...,&\nu\_{2M,NM}\end{bmatrix}
\otimes I_{(n^2)}\\\\
\vdots \\\\
\begin{bmatrix}\nu\_{NM,11},&\nu\_{NM,12},&...,&\nu\_{NM,1M},&\nu\_{NM,21},&...,&\nu\_{NM,2M},&...,&\nu\_{NM,NM}\end{bmatrix}
\otimes I_{(n^2)}
\end{bmatrix}
\right\\}\\\\
&\times
\begin{bmatrix}
\text{vec}(P\_{11})\\\\
\vdots\\\\
\text{vec}(P\_{1M})\\\\
\text{vec}(P\_{21})\\\\
\vdots\\\\
\text{vec}(P\_{2M})\\\\
\vdots\\\\
\text{vec}(P\_{NM})
\end{bmatrix}=
\begin{bmatrix}
\text{vec}(\mathcal{O}\_{11})\\\\
\vdots\\\\
\text{vec}(\mathcal{O}\_{1M})\\\\
\text{vec}(\mathcal{O}\_{21})\\\\
\vdots\\\\
\text{vec}(\mathcal{O}\_{2M})\\\\
\vdots\\\\
\text{vec}(\mathcal{O}\_{NM})
\end{bmatrix}
\end{split}
$$

## Gramiano de Controlabilidade?[refazer as contas]

Considere a distribuição inicial de $Z(0)$ conforme $\pi\_{j\ell}=Prob(Z(0)=(j\ell))$ e também $\mathcal{Q}\_{j\ell}=\pi\_{j\ell}H\_jH\_j'$ para todo $(j\ell)\in\mathcal{N}\times\mathcal{M}$.

Considere o operador $\mathcal{L}_{j\ell}(P)$, para cada $(j\ell)\in\mathcal{N}\times\mathcal{M}$, dado por

$$
\mathcal{L}\_{j\ell}(Q) = \hat{A}\_{j\ell}Q\_{j\ell} + Q\_{j\ell}\hat{A}\_{j\ell}' +
\sum\_{i\in\mathcal{N}} \sum\_{k\in\mathcal{M}} \nu\_{ik,j\ell} Q\_{ik}
$$

A solução $Q=\\{Q_{j\ell},j\in\mathcal{M},\ell\in\mathcal{M}\\}$ da equação

$$
\mathcal{L}\_{j\ell}(Q) + \mathcal{Q}\_{j\ell} = 0
$$

é o gramiano de controlabilidade.

Para resolvê-lo analiticamente, escrevemos o seguinte sistema de equações lineares, nas variáveis $Q_{j\ell}$.

$$
\scriptsize
\begin{split}
  &\left\{
    \begin{bmatrix}
      I_{(n)}\otimes \hat{A}\_{11}\\\\
      &...\\\\
      &&I_{(n)}\otimes \hat{A}\_{1M}\\\\
      &&&I_{(n)}\otimes \hat{A}\_{21}\\\\
      &&&&...\\\\
      &&&&&I_{(n)}\otimes \hat{A}\_{2M}\\\\
      &&&&&&...\\\\
      &&&&&&&I_{(n)}\otimes \hat{A}\_{NM}
    \end{bmatrix}
  \right.\\\\[8pt]
  &+\begin{bmatrix}
    \hat{A}\_{11}'\otimes I_{(n)}\\\\
      &...\\\\
      && \hat{A}\_{1M}'\otimes I_{(n)}\\\\
      &&& \hat{A}\_{21}'\otimes I_{(n)}\\\\
      &&&&...\\\\
      &&&&& \hat{A}\_{2M}'\otimes I_{(n)}\\\\
      &&&&&&...\\\\
      &&&&&&& \hat{A}\_{NM}'\otimes I_{(n)}
  \end{bmatrix}\\\\[8pt]
  &+\left.\begin{bmatrix}
      \begin{bmatrix}
        \nu\_{11,11},&\nu\_{12,11},&...,&\nu\_{1M,11},&\nu\_{21,11},&...,&\nu\_{2M,11},&...,&\nu\_{NM,11}
      \end{bmatrix}
      \otimes I_{(n^2)}\\\\
      \begin{bmatrix}
        \nu\_{11,12},&\nu\_{12,12},&...,&\nu\_{1M,12},&\nu\_{21,12},&...,&\nu\_{2M,12},&...,&\nu\_{NM,12}
      \end{bmatrix}
      \otimes I_{(n^2)}\\\\
      \vdots \\\\
      \begin{bmatrix}
         \nu\_{11,1M},&\nu\_{12,1M},&...,&\nu\_{1M,1M},&\nu\_{21,1M},&...,&\nu\_{2M,1M},&...,&\nu\_{NM,1M}
      \end{bmatrix}
      \otimes I_{(n^2)}\\\\
      \begin{bmatrix}
          \nu\_{11,21},&\nu\_{12,21},&...,&\nu\_{1M,21},&\nu\_{21,21},&...,&\nu\_{2M,21},&...,&\nu\_{NM,21}
      \end{bmatrix}
      \otimes I_{(n^2)}\\\\
      \vdots \\\\
      \begin{bmatrix}
          \nu\_{11,2M},&\nu\_{12,2M},&...,&\nu\_{1M,2M},&\nu\_{21,2M},&...,&\nu\_{2M,2M},&...,&\nu\_{NM,2M}
      \end{bmatrix}
      \otimes I_{(n^2)}\\\\
      \vdots \\\\
      \begin{bmatrix}
          \nu\_{11,NM},&\nu\_{12,NM},&...,&\nu\_{1M,NM},&\nu\_{21,NM},&...,&\nu\_{2M,NM},&...,&\nu\_{NM,NM}
      \end{bmatrix}
      \otimes I_{(n^2)}
    \end{bmatrix}
  \right\\}\\\\
  &\times
  \begin{bmatrix}
      \text{vec}(Q\_{11})\\\\
      \vdots\\\\
      \text{vec}(Q\_{1M})\\\\
      \text{vec}(Q\_{21})\\\\
      \vdots\\\\
      \text{vec}(Q\_{2M})\\\\
      \vdots\\\\
      \text{vec}(Q\_{NM})
  \end{bmatrix}
  =
  \begin{bmatrix}
      \text{vec}(\mathcal{Q}\_{11})\\\\
      \vdots\\\\
      \text{vec}(\mathcal{Q}\_{1M})\\\\
      \text{vec}(\mathcal{Q}\_{21})\\\\
      \vdots\\\\
      \text{vec}(\mathcal{Q}\_{2M})\\\\
      \vdots\\\\
      \text{vec}(\mathcal{Q}\_{NM})
  \end{bmatrix}
\end{split}
$$
