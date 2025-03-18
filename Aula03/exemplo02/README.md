# Exercício de Sistemas de Controle com Octave

Neste exercício, continuamos a análise de sistemas de controle utilizando o Octave, focando em duas funções de transferência diferentes.

![Octave_stepg1g2](https://github.com/user-attachments/assets/6902d2bb-7d9b-40ec-8a46-bbbdcb2b0895)


## 1. Definindo as Funções de Transferência

Definimos duas funções de transferência `g1` e `g2` com os seguintes parâmetros:

### Função de Transferência g1

```octave
g1 = tf([0 0 200],[1 200 0])
```

A função de transferência `g1` é dada por:

\[
g_1(s) = \frac{200}{s^2 + 200s}
\]

### Função de Transferência g2

```octave
g2 = tf([0 0 200],[1 200 200])
```

A função de transferência `g2` é dada por:

\[
g_2(s) = \frac{200}{s^2 + 200s + 200}
\]

## 2. Resposta ao Degrau das Funções de Transferência

Calculamos e plotamos a resposta ao degrau para ambas as funções de transferência `g1` e `g2`:

```octave
step(g1, g2)
```

## Conclusão

Neste exercício, definimos duas funções de transferência e analisamos suas respostas ao degrau. A comparação das respostas ao degrau de `g1` e `g2` nos permite entender melhor o comportamento dinâmico de cada sistema.
