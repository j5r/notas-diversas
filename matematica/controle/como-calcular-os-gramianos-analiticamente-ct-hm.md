<script>MathJax = {tex: {inlineMath: [['$', '$']]}, svg: {fontCache: 'global'}};</script>
<script type="text/javascript" id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js"> </script>

# Resolvendo analiticamente os gramianos

Considere o seguinte sistema

$$
\left\{
\begin{aligned}
x(t)&=A_{\theta(t)}x(t)+B_{\theta(t)}u(t)+H_{\theta(t)}w(t)\\
y(t)&=C_{\theta(t)}x(t)+D_{\theta(t)}u(t)\\
u(t)&=F_{\eta(t)}x(t),\\
\theta(t)&\in\mathcal{N}=\{1,...,N\},\\
\eta(t)&\in\mathcal{M}=\{1,...,M\},\\
x(t)&\in\Re^n,\;\;t\ge0,
\end{aligned}
\right.
$$

com $C_i'D_i=0$ com $D_i'D_i>0$.

A cadeia de Markov $ \\{ \theta(t),t\ge0 \\} $ tem matriz de transição dada por $\Lambda=[\lambda_{ij}]$ e o processo observado é $\\{\eta(t),t\ge0 \\}$. O processo conjunto $Z(t)=(\theta(t),\eta(t))$ é tal que, para $h>0$ pequeno,

$$
Prob(Z(t+h)=(j,\ell)\mid Z(t)=(i,k)) =
\begin{cases}
\nu_{ik,j\ell} h + o(h), & (ik)\neq (j\ell),\\
1 + \nu_{ik,j\ell} h + o(h) & (ik) = (j\ell),
\end{cases}
$$

onde se tem as taxas $\nu_{ik,j\ell}$ para cada $(ik),(j\ell)\in\mathcal{N}\times \mathcal{M}$ dadas por

$$
\nu_{ik,\,j\ell}=
\begin{cases}
\alpha^k_{j\ell} \lambda_{ij}, & i\neq j,\\
q^i_{k\ell}, & i=j, \ell\neq k,\\
\lambda_{ii}+q_{kk}^i, & (ik)=(j\ell).
\end{cases}
$$

As matrizes de malha fechada são

$$\hat{A}_{ik}=A_i+B_iF_k\qquad\mbox{ e }\qquad\hat{C}_{ik}=C_i+D_iF_{ik},\quad \forall\; (ik)\in\mathcal{N}\times\mathcal{M}$$

e definimos, para cada $(ik)\in\mathcal{N}\times\mathcal{M}$, 

$$\mathcal{O}_{ik}=\hat{C}_{ik}'\hat{C}_{ik}.$$

Denote por $I_{(m)}$ a matriz identidade de ordem $m$, $\otimes$ o produto de Kronecker, e $\text{vec}(X)$ o operador de vetorização (empilhamento das colunas de X).

## Gramiano de Observabilidade

Considere o operador $\mathcal{T}_{ik}(P)$, para cada $(ik)\in\mathcal{N}\times\mathcal{M}$, dado por

$$
\mathcal{T}_{ik}(P) = \hat{A}_{ik}'P_{ik} + P_{ik}\hat{A}_{ik} +
\sum_{j\in\mathcal{N}} \sum_{\ell\in\mathcal{M}} \nu_{ik,j\ell} P_{j\ell}
$$

A solução $P=\{P_{j\ell},j\in\mathcal{M},\ell\in\mathcal{M}\}$ da equação

$$
\mathcal{T}_{ik}(P) + \mathcal{O}_{ik} = 0
$$

é o gramiano de observabilidade.

Para resolvê-lo analiticamente, escrevemos o seguinte sistema de equações lineares, nas variáveis $P_{j\ell}$.

$$
\begin{split}
&\left\{
  \begin{bmatrix}
  I_{(n)}\otimes \hat{A}_{11}'\\
  &...\\
  &&I_{(n)}\otimes \hat{A}_{1M}'\\
  &&&I_{(n)}\otimes \hat{A}_{21}'\\
  &&&&...\\
  &&&&&I_{(n)}\otimes \hat{A}_{2M}'\\
  &&&&&&...\\
  &&&&&&&I_{(n)}\otimes \hat{A}_{NM}'
  \end{bmatrix}
\right.\\[8pt]
&+\begin{bmatrix}
\hat{A}_{11}\otimes I_{(n)}\\
  &...\\
  && \hat{A}_{1M}\otimes I_{(n)}\\
  &&& \hat{A}_{21}\otimes I_{(n)}\\
  &&&&...\\
  &&&&& \hat{A}_{2M}\otimes I_{(n)}\\
  &&&&&&...\\
  &&&&&&& \hat{A}_{NM}\otimes I_{(n)}
\end{bmatrix}\\[8pt]
&+\left.
  \begin{bmatrix}
\begin{bmatrix}
\nu_{11,11},&\nu_{11,12},&...,&\nu_{11,1M},&\nu_{11,21},&...,&\nu_{11,2M},&...,&\nu_{11,NM}\end{bmatrix}
\otimes I_{(n^2)}\\
\begin{bmatrix}\nu_{12,11},&\nu_{12,12},&...,&\nu_{12,1M},&\nu_{12,21},&...,&\nu_{12,2M},&...,&\nu_{12,NM}\end{bmatrix}
\otimes I_{(n^2)}\\
\vdots \\
\begin{bmatrix}\nu_{1M,11},&\nu_{1M,12},&...,&\nu_{1M,1M},&\nu_{1M,21},&...,&\nu_{1M,2M},&...,&\nu_{1M,NM}\end{bmatrix}
\otimes I_{(n^2)}\\
\begin{bmatrix}\nu_{21,11},&\nu_{21,12},&...,&\nu_{21,1M},&\nu_{21,21},&...,&\nu_{21,2M},&...,&\nu_{21,NM}\end{bmatrix}
\otimes I_{(n^2)}\\
\vdots \\
\begin{bmatrix}\nu_{2M,11},&\nu_{2M,12},&...,&\nu_{2M,1M},&\nu_{2M,21},&...,&\nu_{2M,2M},&...,&\nu_{2M,NM}\end{bmatrix}
\otimes I_{(n^2)}\\
\vdots \\
\begin{bmatrix}\nu_{NM,11},&\nu_{NM,12},&...,&\nu_{NM,1M},&\nu_{NM,21},&...,&\nu_{NM,2M},&...,&\nu_{NM,NM}\end{bmatrix}
\otimes I_{(n^2)}
\end{bmatrix}
\right\}\\
&\times
\begin{bmatrix}
\text{vec}(P_{11})\\
\vdots\\
\text{vec}(P_{1M})\\
\text{vec}(P_{21})\\
\vdots\\
\text{vec}(P_{2M})\\
\vdots\\
\text{vec}(P_{NM})
\end{bmatrix}=
\begin{bmatrix}
\text{vec}(\mathcal{O}_{11})\\
\vdots\\
\text{vec}(\mathcal{O}_{1M})\\
\text{vec}(\mathcal{O}_{21})\\
\vdots\\
\text{vec}(\mathcal{O}_{2M})\\
\vdots\\
\text{vec}(\mathcal{O}_{NM})
\end{bmatrix}
\end{split}
$$

## Gramiano de Controlabilidade?[refazer as contas]

Considere a distribuição inicial de $Z(0)$ conforme $\pi_{j\ell}=Prob(Z(0)=(j\ell))$ e também, para todo $(j\ell)\in\mathcal{N}\times\mathcal{M}$,

$$\mathcal{Q}_{j\ell}=\pi_{j\ell}H_jH_j'.$$

Considere o operador $\mathcal{L}_{j\ell}(P)$, para cada $(j\ell)\in\mathcal{N}\times\mathcal{M}$, dado por

$$
\mathcal{L}_{j\ell}(Q) = \hat{A}_{j\ell}Q_{j\ell} + Q_{j\ell}\hat{A}_{j\ell}' +
\sum_{i\in\mathcal{N}} \sum_{k\in\mathcal{M}} \nu_{ik,j\ell} Q_{ik}
$$

A solução $Q=\{Q_{j\ell},j\in\mathcal{M},\ell\in\mathcal{M}\}$ da equação

$$
\mathcal{L}_{j\ell}(Q) + \mathcal{Q}_{j\ell} = 0
$$

é o gramiano de controlabilidade.

Para resolvê-lo analiticamente, escrevemos o seguinte sistema de equações lineares, nas variáveis $Q_{j\ell}$.

$$
\begin{split}
  &\left\{
    \begin{bmatrix}
      I_{(n)}\otimes \hat{A}_{11}\\
      &...\\
      &&I_{(n)}\otimes \hat{A}_{1M}\\
      &&&I_{(n)}\otimes \hat{A}_{21}\\
      &&&&...\\
      &&&&&I_{(n)}\otimes \hat{A}_{2M}\\
      &&&&&&...\\
      &&&&&&&I_{(n)}\otimes \hat{A}_{NM}
    \end{bmatrix}
  \right.\\[8pt]
  &+\begin{bmatrix}
    \hat{A}_{11}'\otimes I_{(n)}\\
      &...\\
      && \hat{A}_{1M}'\otimes I_{(n)}\\
      &&& \hat{A}_{21}'\otimes I_{(n)}\\
      &&&&...\\
      &&&&& \hat{A}_{2M}'\otimes I_{(n)}\\
      &&&&&&...\\
      &&&&&&& \hat{A}_{NM}'\otimes I_{(n)}
  \end{bmatrix}\\[8pt]
  &+\left.\begin{bmatrix}
      \begin{bmatrix}
        \nu_{11,11},&\nu_{12,11},&...,&\nu_{1M,11},&\nu_{21,11},&...,&\nu_{2M,11},&...,&\nu_{NM,11}
      \end{bmatrix}
      \otimes I_{(n^2)}\\
      \begin{bmatrix}
        \nu_{11,12},&\nu_{12,12},&...,&\nu_{1M,12},&\nu_{21,12},&...,&\nu_{2M,12},&...,&\nu_{NM,12}
      \end{bmatrix}
      \otimes I_{(n^2)}\\
      \vdots \\
      \begin{bmatrix}
         \nu_{11,1M},&\nu_{12,1M},&...,&\nu_{1M,1M},&\nu_{21,1M},&...,&\nu_{2M,1M},&...,&\nu_{NM,1M}
      \end{bmatrix}
      \otimes I_{(n^2)}\\
      \begin{bmatrix}
          \nu_{11,21},&\nu_{12,21},&...,&\nu_{1M,21},&\nu_{21,21},&...,&\nu_{2M,21},&...,&\nu_{NM,21}
      \end{bmatrix}
      \otimes I_{(n^2)}\\
      \vdots \\
      \begin{bmatrix}
          \nu_{11,2M},&\nu_{12,2M},&...,&\nu_{1M,2M},&\nu_{21,2M},&...,&\nu_{2M,2M},&...,&\nu_{NM,2M}
      \end{bmatrix}
      \otimes I_{(n^2)}\\
      \vdots \\
      \begin{bmatrix}
          \nu_{11,NM},&\nu_{12,NM},&...,&\nu_{1M,NM},&\nu_{21,NM},&...,&\nu_{2M,NM},&...,&\nu_{NM,NM}
      \end{bmatrix}
      \otimes I_{(n^2)}
    \end{bmatrix}
  \right\}\\
  &\times
  \begin{bmatrix}
      \text{vec}(Q_{11})\\
      \vdots\\
      \text{vec}(Q_{1M})\\
      \text{vec}(Q_{21})\\
      \vdots\\
      \text{vec}(Q_{2M})\\
      \vdots\\
      \text{vec}(Q_{NM})
  \end{bmatrix}
  =
  \begin{bmatrix}
      \text{vec}(\mathcal{Q}_{11})\\
      \vdots\\
      \text{vec}(\mathcal{Q}_{1M})\\
      \text{vec}(\mathcal{Q}_{21})\\
      \vdots\\
      \text{vec}(\mathcal{Q}_{2M})\\
      \vdots\\
      \text{vec}(\mathcal{Q}_{NM})
  \end{bmatrix}
\end{split}
$$
