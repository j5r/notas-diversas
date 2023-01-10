<script>MathJax = {tex: {inlineMath: [['$', '$']]}, svg: {fontCache: 'global'}};</script>
<script type="text/javascript" id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js"> </script>

## Cálculo da soma de uma progressão geométrica

Vamos calcular a soma $S_m^n=aq^m+aq^{m+1}+...+aq^{n-1}+aq^n$, para $n>m$.

$$
S_m^n=aq^m+aq^{m+1}+...+aq^{n-1}+aq^n
$$

Divida a expressão acima por $q^m$.

$$
(*)\quad \frac{S_m^n}{q^m}=aq^0+aq^{1}+...+aq^{n-m-1}+aq^{n-m}
$$

Subtraia $aq^0$ e divida a expressão acima por $q$.

$$
\frac{\frac{S_m^n}{q^m}-aq^0}{q} = aq^{0}+...+aq^{n-m-2}+aq^{n-m-1}
$$

Note que o membro direito é igual a $(*)$ menos $aq^{n-m}$. Escrevemos.

$$
\frac{\frac{S_m^n}{q^m}-aq^0}{q} = \frac{S_m^n}{q^m}- aq^{n-m}
$$

Multiplicamos tudo por $q$.

$$
\frac{S_m^n}{q^m}-aq^0 = \frac{qS_m^n}{q^m}- aq^{n-m+1}
$$

Multiplicamos tudo por $q^m$.

$$
S_m^n-aq^m = qS_m^n- aq^{n+1}
$$

Agora isolamos $S_m^n$.

$$
S_m^n- qS_m^n = aq^m- aq^{n+1}
$$

$$
S_m^n(1- q) = a(q^m- q^{n+1})
$$

<div style="background-color:#ccd;border-radius:15px;padding:5px;">
$$
S_m^n = \frac{a(q^m- q^{n+1})}{(1- q)} = aq^m+aq^{m+1}+...+aq^{n-1}+aq^n
$$
</div>

### Soma de uma P.G. infinita 

Aproveitando o resultado acima, tomando o limite $n\to\infty$, temos

<div style="background-color:#ccd;border-radius:15px;padding:5px;">
$$
S_m^\infty = \lim_{n\to\infty}\frac{a(q^m- q^{n+1})}{(1- q)} = 
\begin{cases}
0,& q=0,\\\\[4pt]
\frac{aq^m}{(1- q)}, & q\in (-1,0)\cup(0,1),\\\\[4pt]
\pm\infty, & q\in (-\infty,-1]\cup[1,\infty).
\end{cases}
$$
</div>