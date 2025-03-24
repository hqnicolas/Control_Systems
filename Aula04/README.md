# Exercício de Sistemas de Controle com Octave

Neste exercício, exploraremos duas funções de transferência e compararemos suas respostas ao degrau e seus diagramas de polos e zeros utilizando o Octave.

## 1. Definição das Funções de Transferência

Definimos duas funções de transferência `g1` e `g2` com os seguintes parâmetros:

### Função de Transferência `g1`

```octave
g1 = tf([0 0 50],[1 32 0])
```

A função de transferência `g1` é dada por:

$$
g_1(s) = \frac{50}{s^2 + 32s}
$$

### Função de Transferência `g2`

```octave
g2 = tf([0 0 50],[1 32 50])
```

A função de transferência `g2` é dada por:

$$
g_2(s) = \frac{50}{s^2 + 32s + 50}
$$

## 2. Resposta ao Degrau

Calculamos e plotamos a resposta ao degrau para ambas as funções de transferência `g1` e `g2`:

```octave
step(g1, g2)
```
![step](https://github.com/user-attachments/assets/0d1610a1-7ff5-44bc-a01d-8db0029db490)

A comparação das respostas ao degrau de `g1` e `g2` ajuda a entender o comportamento dinâmico de cada sistema.

## 3. Diagrama de Polos e Zeros

Para estudar os polos e zeros das funções de transferência, geramos o diagrama de polos e zeros para `g1` e `g2`:

```octave
pzmap(g1, g2)
```
![pzmap](https://github.com/user-attachments/assets/d726245a-c992-4514-b1b0-fd24b9487cca)

O diagrama de polos e zeros fornece uma representação gráfica que ajuda a analisar a estabilidade e o comportamento de cada sistema.

## Conclusão

Neste exercício, definimos e analisamos duas funções de transferência, `g1` e `g2`, comparando suas respostas ao degrau e os diagramas de polos e zeros. Isso nos permite entender como pequenas mudanças nos coeficientes da função de transferência impactam o comportamento dinâmico do sistema.
