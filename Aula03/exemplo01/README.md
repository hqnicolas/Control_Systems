# Exercício de Sistemas de Controle com Octave

Neste exercício, utilizamos o Octave para analisar um sistema de controle representado por uma função de transferência.

## 1. Carregando o Pacote de Sinal

Primeiro, carregamos o pacote de sinal necessário para trabalhar com funções de transferência:

```octave
pkg load signal
```

## 2. Definindo a Função de Transferência

Definimos a função de transferência `g` com os seguintes parâmetros:

```octave
g = tf([0 0 100],[1 2 25])
```

A função de transferência `g` é dada por:

\[
g(s) = \frac{100}{s^2 + 2s + 25}
\]

## 3. Análise de Polos e Zeros

Calculamos os polos e zeros da função de transferência:

### Polos

```octave
pole(g)
```

Os polos são:

```
-1.0000 + 4.8990i
-1.0000 - 4.8990i
```

### Zeros

```octave
zero(g)
```

Os zeros são:

```
ans = [](0x1)
```

## 4. Ganho de Corrente Contínua

Calculamos o ganho de corrente contínua da função de transferência:

```octave
dcgain(g)
```

O ganho de corrente contínua é:

```
ans = 4
```

## 5. Resposta ao Impulso e Resposta ao Degrau

Calculamos a resposta ao impulso e a resposta ao degrau do sistema:

```octave
impulse(g)
step(g)
step(g)
step(g, 10)
```

## 6. Análise da Resposta ao Degrau

Armazenamos a resposta ao degrau em uma variável `y` e plotamos o resultado:

```octave
y = step(g);
plot(y)
```

## 7. Valor Máximo da Resposta ao Degrau

Por fim, calculamos o valor máximo da resposta ao degrau:

```octave
max(y)
```

O valor máximo é:

```
ans = 6.0974
```

## Conclusão

Neste exercício, analisamos a função de transferência de um sistema de controle, calculamos seus polos, zeros, ganho de corrente contínua e analisamos a resposta ao degrau. O valor máximo da resposta ao degrau foi encontrado como 6.0974.
