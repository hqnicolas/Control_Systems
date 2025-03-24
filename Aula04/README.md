# Exercícios de Sistemas de Controle com Octave

Este repositório contém exemplos de exercícios para análise de sistemas de controle utilizando o Octave. Abaixo, são apresentados dois exemplos que abordam funções de transferência e suas respostas ao degrau, além de diagramas de polos e zeros.

## 1. Função de Transferência com Parâmetro `k = 644`

[Link](https://github.com/hqnicolas/Control_Systems/tree/main/Aula04/Exemplo01)Neste exercício, é definida uma função de transferência e analisada sua resposta ao degrau.

### Definição da Função de Transferência

A função de transferência `g` é definida como:

```octave
k = 644
g = tf([0 0 k],[1 30 k])
```

A função de transferência `g` é dada por:

$$
g(s) = \frac{644}{s^2 + 30s + 644}
$$

### Resposta ao Degrau

A resposta ao degrau do sistema é calculada com o seguinte comando:

```octave
step(g)
```

O valor máximo da saída da resposta ao degrau é:

$$
\text{Máximo da saída } y_{\text{máx}} = 1.1000
$$

## 2. Comparação entre Duas Funções de Transferência

[Link](https://github.com/hqnicolas/Control_Systems/tree/main/Aula04/Exemplo02) Neste exercício, comparamos duas funções de transferência, `g1` e `g2`, e analisamos suas respostas ao degrau, além de visualizar seus diagramas de polos e zeros.

### Definição das Funções de Transferência

#### Função de Transferência `g1`

```octave
g1 = tf([0 0 50],[1 32 0])
```

A função de transferência `g1` é dada por:

$$
g_1(s) = \frac{50}{s^2 + 32s}
$$

#### Função de Transferência `g2`

```octave
g2 = tf([0 0 50],[1 32 50])
```

A função de transferência `g2` é dada por:

$$
g_2(s) = \frac{50}{s^2 + 32s + 50}
$$

### Resposta ao Degrau

A resposta ao degrau para as duas funções de transferência é gerada com o comando:

```octave
step(g1, g2)
```

### Diagrama de Polos e Zeros

Os diagramas de polos e zeros das funções `g1` e `g2` são gerados com o comando:

```octave
pzmap(g1, g2)
```

O diagrama de polos e zeros ajuda a visualizar a estabilidade e o comportamento dinâmico de ambos os sistemas.
