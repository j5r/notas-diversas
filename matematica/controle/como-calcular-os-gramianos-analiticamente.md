<script>
MathJax = {
  tex: {
    inlineMath: [['$', '$']]
  },
  svg: {
    fontCache: 'global'
  }
};
</script>
<script type="text/javascript" id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js">
</script>

# Resolvendo analiticamente os gramianos

Considere o seguinte sistema

$$
\left\{
\begin{aligned}
x(k+1)&=A_{\theta(k)}x(k)+B_{\theta(k)}u(k)+E_{\theta(k)}w(k)\\
y(k)&=C_{\theta(k)}x(k)+D_{\theta(k)}u(k)\\
u(k)&=F_{\theta(k)}x(k),\\
\theta(k)&\in\mathbf{S}=\{1,...,N\},\;x(k)\in\Re^n,\;\;k\ge0,
\end{aligned}
\right.
$$

com $C_i'D_i=0$ com $D_i'D_i>0$.

A cadeia de Markov $ \\{ \theta(k),k\ge0 \\} $ tem matriz de transição dada por $P=[p_{ij}]\in[0,1]^{N\times N}$ tal que $Prob(\theta(k)=j\mid\theta(k-1)=i)=p_{ij}$, com distribuição inicial $\pi_i=Prob(\theta(0)=i)$.

As matrizes de malha fechada são

$$\hat{A}_i=A_i+B_iF_i\qquad\mbox{ e }\qquad\hat{C}_i=C_i+D_iF_i,$$

e definimos $\mathcal{O}_i=\hat{C}_i'\hat{C}_i$, para cada $i\in\mathbf{S}$.

Denote por $I_{(m)}$ a matriz identidade de ordem $m$, $\otimes$ o produto de Kronecker, e $\text{vec}(X)$ o operador de vetorização (empilhamento das colunas de X).

## Gramiano de Observabilidade

Resolva o seguinte sistema linear, nas variáveis $\text{vec}(S_i)$.

$$
\begin{bmatrix}
I_{(Nn^2)} - \left(
{\color{red}
  \begin{bmatrix}
  \hat{A}_1'\otimes \hat{A}_1'&&&\\
  &\hat{A}_2'\otimes \hat{A}_2'&&\\
  &&\ddots&\\
  &&&\hat{A}_N'\otimes \hat{A}_N'
  \end{bmatrix}
}\cdot {\color{blue}
  \Bigg(P\otimes I_{(n^2)}\Bigg)
}
\right)
\end{bmatrix}
{\color{blue}
\begin{bmatrix}
\text{vec}(S_1)\\
\text{vec}(S_2)\\
\vdots\\
\text{vec}(S_N)
\end{bmatrix}
}
=
\begin{bmatrix}
\text{vec}(\mathcal{O}_1)\\
\text{vec}(\mathcal{O}_2)\\
\vdots\\
\text{vec}(\mathcal{O}_N)
\end{bmatrix}
$$

$S_i=\text{vec}^{-1}(S_i)$ é o $i$-ésimo gramiano de observabilidade, para cada $i\in\mathbf{S}$.

## Gramiano de Controlabilidade?[refazer as contas]

Resolva o seguinte sistema linear, nas variáveis $\text{vec}(V_i)$.

$$
\begin{bmatrix}
I_{(Nn^2)} -
\left(
{\color{red}
  \begin{bmatrix}
  \hat{A}_1\otimes \hat{A}_1&&&\\
  &\hat{A}_2\otimes \hat{A}_2&&\\
  &&\ddots&\\
  &&&\hat{A}_N\otimes \hat{A}_N
  \end{bmatrix}
}
\cdot {\color{blue}
  \Bigg(P'\otimes I_{(n^2)}\Bigg)
}
\right)
\end{bmatrix}
\begin{bmatrix}
\text{vec}(V_1)\\
\text{vec}(V_2)\\
\vdots\\
\text{vec}(V_N)
\end{bmatrix}
$$

$$ =
{\color{red}
  \Big(P'\otimes I_{(n^2)} \Big)
}
\cdot{\color{blue}
  \Big(\text{diag}(\pi)\otimes I_{(n^2)}\Big)
}
\begin{bmatrix}
\text{vec}(E_1E_1')\\
\text{vec}(E_2E_2')\\
\vdots\\
\text{vec}(E_NE_N')
\end{bmatrix}
$$

$V_i=\text{vec}^{-1}(V_i)$ é o $i$-ésimo gramiano de controlabilidade, para cada $i\in\mathbf{S}$.
