## **Definições de variáveis**

Uma variável é simplesmente um espaço na memória do computador que batizamos com um nome e guardamos informações nela. Para recuperar as informações, simplesmente chamamos pelo seu nome durante o programa.

A definição de variáveis pode acontecer em duas etapas:

1. **declarando-se** a variável (em linguagens estaticamente tipadas como C, C++, Java, etc.)
2. **atribuindo-se-lhe** um valor

A etapa 1 normalmente não acontece nas linguagens dinamicamente tipadas.

### **_Declarando_ uma variável**

Quando declaramos uma variável, dizemos qual o seu **tipo** e o seu **nome** e às vezes o seu **tamanho**.

- **Tipo:** cada informação pode ser de tipo "texto", "número inteiro", "número real", "valor lógico verdadeiro/falso", e variantes desses. Além desses tipos padrão, podemos criar tipos personalizados, os dados compostos que são chamados de estruturas (relembre o ["struct"](./linguagem-de-programacao#linguagem-estruturada))

- **Nome:** batizamos a variável (um bloco de memória) com o nome que quisermos, dentro das regras de "batismo" da determinada linguagem. Cada linguagem tem um conjunto de palavras-chave que têm seu próprio propósito, e por isso não podemos batizar as variáveis com esses nomes. Os nomes normalmente não podem ter espaços e muitas vezes também não podem ser acentuados (há linguagens que permitem acentuação, mas normalmente não se recomenda usar esse recurso).

- **Tamanho:** a quantidade de bytes necessária para armazenar a requerida informação.

Quando declaramos uma variável, uma chamada é feita ao Sistema Operacional - SO (exemplos de SO: Windows, Linux, MacOS, Android, iOS, e outros menos comuns) - requisitando um bloco de memória de um certo tamanho, um tipo específico para essa informação e batizando-o com um nome. Se pedirmos um tamanho muito grande de memória, o SO pode recusar e obtemos uma mensagem de erro, caso o computador não tenha toda essa memória disponível ou ocorra outro problema.

### **_Atribuindo_ um valor à variável**

Perceba que até o momento não foi dado nenhum valor para a variável. O seu correspondente bloco de memória já pode ter qualquer valor armazenado anteriormente e que ainda não fora limpado, o que chamamos de lixo de memória.

Neste ponto, a linguagem de programação tem um **operador de atribuição** que é um símbolo usado para transferir alguma informação para dentro do bloco de memória da variável. Normalmente (nem sempre), o operador de atribuição é o sinal de igual "=". O que estiver **à esquerda** do operador de atribuição **precisa ser uma variável**, isto é, precisa ser uma referência para um endereço de memória, e o que estiver **à direita** do operador de atribuição pode ser **qualquer dado ou mesmo outra variável ou operação entre dados e variáveis**.

### **Exemplo 1**

Vamos ver como seria **declarar** e **atribuir** valor a uma variável nas linguagens C e C++.

```C
// C ou C++
1. int idade, nascimento;
2. idade = 28;
3.
4. int ano = 2023;
5. nascimento = ano - idade;
```

- linha 1: `declaramos` **idade** e **nascimento** duas variáveis do tipo inteiro **int**;
- linha 2: `atribuímos` o valor **28** à variável **idade** (guardamos esse valor na memória);
- linha 4: `declaramos` e `atribuímos` o valor **2023** à variável **ano** do tipo **int**;
- linha 5: realizamos uma operação aritmética com as variáveis **ano** e **idade** (os valores em memória são recuperados quando as variáveis estão do lado direito da atribuição) e atribuímos seu resultado à variável **nascimento**.

Quando a linha 5 terminar de ser executada, teremos o valor **1995** armazenado na memória referente à variável **nascimento**.

### **Exemplo 2**

Vamos fazer o mesmo acima com uma linguagem dinamicamente tipada (Python). Tais linguagens não necessitam de se declarar seu tipo explicitamente, simplificando a programação (a tarefa de entender qual tipo de informação fica a cargo de outros programas que são acionados quando executamos o nosso programa).

```python
# Python
1. idade = 28
2. ano = 2023
3.
4. nascimento = ano - idade
```

Nas linguagens dinamicamente tipadas, a etapa da `declaração` é automaticamente feita durante a `atribuição`.

- linha 1: atribuímos **28** à variável **idade**;
- linha 2: atribuímos **2023** à variável **ano**;
- linha 4: atribuímos **1995** à variável **nascimento**, resultado da operação aritmética de subtração em questão.


### **Conversão de tipos**

Algumas vezes é necessário fazer uma conversão forçada de um tipo de dado para outro, o que chamamos de _casting_. Tal necessidade é inerente às linguagens estaticamente tipadas. Vamos ver um exemplo.

```c
// C ou C++
1. float base = 145.72, altura = 49.28;
2. int area = (int) base * altura;
```

- linha 1: as variáveis **base** e **altura** são inicializadas com números os reais (tipo **float**) **145.72** e **49.28** respectivamente.

- linha 2: a variável **area** do tipo **int** é inicializada com **7181**, que é o resultado da conversão do número real **7181.0816** para o tipo **int** por meio do _casting_, representado por `(int)` logo após o sinal de atribuição.
