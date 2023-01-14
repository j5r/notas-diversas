<script>MathJax = {tex: {inlineMath: [['$', '$']]}, svg: {fontCache: 'global'}};</script>
<script type="text/javascript" id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-svg.js"> </script>

# Representação de números inteiros

Um número inteiro $N$ pode ser representado, no nosso sistema decimal posicional adotado, da seguinte forma:

$$
N = a_0 \times 10^0 + a_1 \times 10^1+a_2 \times 10^2+a_3 \times 10^3+...,
$$

onde cada número $a_i$ é um dígito de $N$, e portanto respeita $0\le a_i<10$.

No entanto, podemos mudar a base do sistema de numeração de $10$ para qualquer outra base $\beta\ge 2$, dando-nos a seguinte forma genérica

<div style="background-color:#dde;border-radius:15px;padding:5px;">
$$ N = a_0 \times \beta^0 + a_1 \times \beta^1+a_2 \times \beta^2+a_3 \times \beta^3+...,\quad \mbox{ com }\quad 0\le a_i < \beta \;\;\forall i. $$
O número $N$ é então representado pela tupla ordenada
$$
N=(...,a_5,a_4,a_3,a_2,a_1,a_0),
$$
na base $\beta$.
</div>

Nos exemplos abaixo, faremos:

- [a representação do inteiro $N=681$ na base decimal $(\beta=10)$;](#exemplo-1)
- [a representação de $N=681$ na base binária $(\beta=2)$ e a conversão da binária para a decimal;](#exemplo-2)
- [a conversão de $N=1010101001$ da base binária para a base decimal;](#exemplo-3)
- [um exemplo na base hexadecimal.](#exemplo-4)

Para evitar ambiguidade, denotamos a base da seguinte forma: $N_\beta$. Como exemplo, $1010101001\_2$ significa que o número está escrito na base binária e $681\_{10}$ está na base decimal.

### **Exemplo 1**

Considere a base decimal, $\beta=10$, e o seguinte $N$:

$$
N = (...,0,0,0,0,6,8,1).
$$

Fazemos a conta

$$
\begin{aligned}
N &= 1\times 10^0+8\times 10^1+6\times 10^2+0\times 10^3+0\times 10^4+0\times 10^5+0\times 10^6+...\\\\
&=1\times 1+8\times 10+6\times 100+0\times 1\,000+0\times 10\,000+0\times 100\,000+0\times 1\,000\,000+...\\\\
&=1+80+600=681.
\end{aligned}
$$

Perceba que na base decimal (a base que usamos), a representação de $N$ não se modifica.

$$
N = (...,0,0,0,0,6,8,1)=...0000681,
$$

_**os zeros à esquerda são insignificantes.**_

<div style="background-color:#dde;border-radius:15px;padding:5px;font-weight:bold;">
A partir de agora, não vamos mais escrever os zeros à esquerda, porque ficam subentendidos.
</div>

### **Exemplo 2**

Vamos escrever o $N=681$ na base $\beta=2$.

$$
N=(...,1,0,1,0,1,0,1,0,0,1).
$$

Perceba que os dígitos $a_i\in\\{0,1\\}$ satisfazem $0\le a_i<\beta=2$.

Fazemos a conta (mudando da base $\beta=2$ para $\beta=10$, simplesmente fazendo a conta).

$$
\begin{aligned}
N&=1\times 2^0+0\times 2^1+0\times 2^2+1\times 2^3+0\times 2^4+1\times 2^5+0\times 2^6+1\times 2^7+0\times 2^8+1\times 2^9\\\\
&=1\times 1+0\times 2+0\times 4+1\times 8+0\times 16+1\times 32+0\times 64+1\times 128+0\times 256+1\times 512\\\\
&= 1+0+0+8+32+0+128+512=681.
\end{aligned}
$$

### **Exemplo 3**

Vamos agora mudar o número $N=681$ da base $\beta=10$ para $\beta=2$. Para realizar essa tarefa, precisamos fazer sucessivas divisões euclidianas de $N$ por $\beta=2$ e observar os restos.

Primeira divisão euclidiana de $N_0=N=681$ por $2$:

$$
N_0=681=2\times 340 +1.
$$

O resto $1$ é o nosso dígito $a_0$. Repetimos o procedimento para o cociente $N_1=340$.

[Até o momento temos $N=(...,1)$]

$$
N_1=340=2\times 170+0.
$$

O resto $0$ é o nosso dígito $a_1$. Repetimos o procedimento para o cociente $N_2=170$.

[Até o momento temos $N=(...,0,1)$]

$$
N_2=170=2\times 85+0.
$$

O resto $0$ é o nosso dígito $a_2$. Repetimos o procedimento para o cociente $N_3=85$.

[Até o momento temos $N=(...,0,0,1)$]

$$
N_3=85=2\times 42+1.
$$

O resto $1$ é o nosso dígito $a_3$. Repetimos o procedimento para o cociente $N_4=42$.

[Até o momento temos $N=(...,1,0,0,1)$]

$$
N_4=42=2\times 21+0.
$$

O resto $0$ é o nosso dígito $a_4$. Repetimos o procedimento para o cociente $N_5=21$.

[Até o momento temos $N=(...,0,1,0,0,1)$]

$$
N_5=21=2\times 10+1.
$$

O resto $1$ é o nosso dígito $a_5$. Repetimos o procedimento para o cociente $N_6=10$.

[Até o momento temos $N=(...,1,0,1,0,0,1)$]

$$
N_6=10=2\times 5+0.
$$

O resto $0$ é o nosso dígito $a_6$. Repetimos o procedimento para o cociente $N_7=5$.

[Até o momento temos $N=(...,0,1,0,1,0,0,1)$]

$$
N_7=5=2\times 2+1.
$$

O resto $1$ é o nosso dígito $a_7$. Repetimos o procedimento para o cociente $N_8=2$.

[Até o momento temos $N=(...,1,0,1,0,1,0,0,1)$]

$$
N_8=2=2\times 1+0.
$$

O resto $0$ é o nosso dígito $a_8$. Repetimos o procedimento para o cociente $N_9=1$.

[Até o momento temos $N=(...,0,1,0,1,0,1,0,0,1)$]

$$
N_9=1=2\times 0+1.
$$

O resto $1$ é o nosso dígito $a_9$. Repetimos o procedimento para o cociente $N\_{10}=0$.

[Até o momento temos $N=(...,1,0,1,0,1,0,1,0,0,1)$]

$$
N_{10}=0=2\times 0+0.
$$

O resto $0$ é o nosso dígito $a_{10}$. Repetimos o procedimento para o cociente $N\_{11}=0$.

[Até o momento temos $N=(...,0,1,0,1,0,1,0,1,0,0,1)$]

**A partir desse ponto, se continuarmos o processo, obteremos sempre dígitos zero, os famosos "zeros à esquerda".**

<div style="background-color:#dde;border-radius:15px;padding:5px;font-weigth:bold;">
O procedimento acima pode ser usado para fazer a mudança de base de $10$ para qualquer outra base $\beta\ge 2.$ Já vimos no <a href="#exemplo-2">Exemplo 2</a> que a mudança de base de $\beta$ para $10$ é feita simplesmente fazendo a soma ponderada das potências de $\beta$.
</div>

### **Exemplo 4**

Lembramos que, em uma determinada base $\beta$, os dígitos $a_i$ vão desde $0$ até $\beta-1$. A base **hexadecimal**, base $\beta=16$, carece de símbolos para representar todos os seus dígitos. Por esse motivo, resolvemos escrever as primeiras letras do alfabeto, ficando da seguinte forma:

| $\beta=10$ |  0  |  1  |  2  |  3  |  4  |  5  |  6  |  7  |  8  |  9  | 10  | 11  | 12  | 13  | 14  | 15  |
| :--------: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: | :-: |
| $\beta=16$ |  0  |  1  |  2  |  3  |  4  |  5  |  6  |  7  |  8  |  9  |  A  |  B  |  C  |  D  |  E  |  F  |

Assim, temos a representação hexadecimal do número 
$N=681\_{10}=(6,8,1)_{10}$ $=2A9\_{16}=(2,A,9)\_{16}.$
Façamos as contas.

$$
\begin{aligned}
N&=9\times 16^0+A\times 16^{1}+2\times 16^2\\\\
&=9\times 1 + 10\times 16 + 2\times 256\\\\
&=9+160+512=681.
\end{aligned}
$$

Da próxima vez que você vir um número em formato hexadecimal, já sabe do que se trata. 

### **Exercícios**

Escreva o número $N=783_{10}$ nas bases $\beta\in\\{2,5,12,16\\}$.