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

# Algoritmo: Precisão da máquina

```matlab
epsilon = 1;
exponent = 0;

while true
  exponent = exponent - 1;
  epsilon = epsilon/2;

  if (1 + epsilon) <= 1
    disp(exponent + 1);
    break;
  end%if
end%while
```

O valor de `exponent - 1` escrito na tela refere-se à menor potência de $2$ que ainda é diferente de $1$, isto é, $1+2^{\text{exponent}+1}>1$, ao passo que $1+2^{\text{exponent}}=1$.

Assim, o valor $\epsilon=2^{\text{exponent}}$ é chamado de "epsilon da máquina" ou "precisão da máquina".
