# Exercício de Sistemas de Controle com Octave

![ex3](https://github.com/user-attachments/assets/51591003-f391-431b-b758-6933692c08a2)

Neste exercício, analisaremos uma função de transferência utilizando o Octave, definindo seus parâmetros, calculando a resposta ao degrau e explorando o comportamento do sistema.

## 1. Definição da Função de Transferência

A função de transferência `g` é definida com os seguintes parâmetros:

```octave
k = 644
g = tf([0 0 k],[1 30 k])
```

A função de transferência `g` é dada por:

$$
g(s) = \frac{644}{s^2 + 30s + 644}
$$

## 2. Resposta ao Degrau

Plotamos a resposta ao degrau para a função de transferência `g`:

```octave
step(g)
```

A resposta ao degrau fornece informações sobre o comportamento do sistema em relação ao tempo. Observamos que o valor máximo da saída é:

$$
\text{Máximo da saída } y_{\text{máx}} = 1.1000
$$

![ex3_octave](https://github.com/user-attachments/assets/797a3a44-c544-44c3-9ddd-38ecf7fb4a60)


## Conclusão

Este exercício demonstrou o uso do Octave para definir uma função de transferência e analisar sua resposta ao degrau. Com o parâmetro `k = 644`, a função apresenta um pico na saída, permitindo entender melhor o comportamento dinâmico do sistema. O estudo de sistemas como este é essencial para projetar e ajustar modelos de controle em aplicações reais.
