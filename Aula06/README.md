# Análise de Motor de Corrente Contínua ⚙️

![Status](https://img.shields.io/badge/Status-Concluído-success)
![Disciplina](https://img.shields.io/badge/Disciplina-Sinais%20e%20Sistemas-blue)
![Linguagem](https://img.shields.io/badge/Docs-Markdown%20%7C%20LaTeX-lightgrey)

## 📑 Índice

- [Introdução](#introdução)
  - [Dados Utilizados](#dados-utilizados)
- [Tarefa 1: Obtenção da Função de Transferência](#tarefa-1-obtenção-da-função-de-transferência)
- [Tarefa 2: Função de Transferência (Motor sem Carga)](#tarefa-2-função-de-transferência-motor-sem-carga)
- [Tarefa 3: Análise do Motor sem Carga](#tarefa-3-análise-do-motor-sem-carga)
- [Tarefa 4: Função de Transferência (Motor com Carga)](#tarefa-4-função-de-transferência-motor-com-carga)
- [Tarefa 5: Análise do Motor com Carga](#tarefa-5-análise-do-motor-com-carga)
- [Tarefa 6: Comparação e Análise](#tarefa-6-comparação-e-análise)
- [Conclusão](#conclusão)
- [Apêndice A: Resultados Numéricos Resumidos](#apêndice-a-resultados-numéricos-resumidos)

---

## Introdução

Este documento apresenta a resolução detalhada da Avaliação 03, referente à disciplina de Sinais e Sistemas Lineares. O trabalho aborda a modelagem e análise de um motor de corrente contínua (CC) com controle pela armadura, considerando seu funcionamento com e sem carga acoplada ao eixo.

Os parâmetros do motor e da carga utilizados para a análise numérica foram fornecidos no enunciado da avaliação e são listados abaixo para referência.

### Dados Utilizados

| Parâmetro | Símbolo | Valor | Unidade |
| :--- | :---: | :--- | :--- |
| Resistência de Armadura | $R_a$ | $7,75$ | $\Omega$ |
| Indutância de Armadura | $L_a$ | $4,1$ | $H$ |
| Constante de Torque | $K_t$ | $0,0131$ | $N \cdot m/A$ |
| Constante de F.C.E.M. | $K_b$ | $0,0131$ | $V \cdot s/rad$ |
| Inércia do Motor | $J$ | $5,2 \times 10^{-7}$ | $kg \cdot m^2$ |
| Atrito do Motor | $B$ | $2,7 \times 10^{-7}$ | $N \cdot m \cdot s/rad$ |
| Inércia da Carga | $J_c$ | $52 \times 10^{-6}$ | $kg \cdot m^2$ |
| Atrito da Carga | $B_c$ | $2,7 \times 10^{-6}$ | $N \cdot m \cdot s/rad$ |

---

## Tarefa 1: Obtenção da Função de Transferência

A primeira tarefa consiste em descrever o processo de obtenção da função de transferência $G(s) = \frac{\omega(s)}{V_a(s)}$ a partir das equações fundamentais do motor.

O modelo do motor CC é composto por uma parte elétrica (Lei de Kirchhoff) e uma parte mecânica (Segunda Lei de Newton).

### Derivação Matemática

1.  **Equação Elétrica:**
    $$V_a(t) = R_a I_a(t) + L_a \frac{dI_a(t)}{dt} + E_a(t)$$

2.  **Equação Mecânica:**
    $$T_m(t) = J_m \frac{d\omega(t)}{dt} + B_m \omega(t)$$

3.  **Equações de Acoplamento:**
    $$T_m(t) = K_t I_a(t)$$
    $$E_a(t) = K_b \omega(t)$$

Aplicando a Transformada de Laplace:

$$V_a(s) = (R_a + L_a s)I_a(s) + K_b \omega(s)$$
$$K_t I_a(s) = (J_m s + B_m)\omega(s)$$

Isolando $I_a(s)$ na segunda equação e substituindo na primeira, chegamos à função de transferência:

$$G(s) = \frac{\omega(s)}{V_a(s)} = \frac{K_t}{(R_a + L_a s)(J_m s + B_m) + K_t K_b}$$

Expandindo o denominador:

$$G(s) = \frac{K_t}{(L_a J_m)s^2 + (R_a J_m + L_a B_m)s + (R_a B_m + K_t K_b)}$$

-----

## Tarefa 2: Função de Transferência (Motor sem Carga)

Considerando apenas a inércia e atrito do motor:

  * $J_m = J = 5,2 \times 10^{-7} \, kg \cdot m^2$
  * $B_m = B = 2,7 \times 10^{-7} \, N \cdot m \cdot s/rad$

Cálculo dos coeficientes:

  * $a = L_a J_m = 2,132 \times 10^{-6}$
  * $b = R_a J_m + L_a B_m = 5,137 \times 10^{-6}$
  * $c = R_a B_m + K_t K_b = 1,737 \times 10^{-4}$

**Função de Transferência Resultante:**

$$G_{sem\_carga}(s) = \frac{0,0131}{2,132 \times 10^{-6} s^2 + 5,137 \times 10^{-6} s + 1,737 \times 10^{-4}}$$

-----

## Tarefa 3: Análise do Motor sem Carga

  * **Zeros:** Não possui zeros finitos.
  * **Polos:** Raízes do denominador:
    $$p_{1,2} = -1,205 \pm j8,946$$

**Conclusão:** O sistema é **subamortecido** e **estável**. A resposta transitória será oscilatória.

-----

## Tarefa 4: Função de Transferência (Motor com Carga)

Considerando a soma dos componentes do motor e da carga:

  * $J_m = 5,252 \times 10^{-5} \, kg \cdot m^2$
  * $B_m = 2,97 \times 10^{-6} \, N \cdot m \cdot s/rad$

Cálculo dos coeficientes:

  * $a = 2,153 \times 10^{-4}$
  * $b = 4,192 \times 10^{-4}$
  * $c = 1,946 \times 10^{-4}$

**Função de Transferência Resultante:**

$$G_{com\_carga}(s) = \frac{0,0131}{2,153 \times 10^{-4} s^2 + 4,192 \times 10^{-4} s + 1,946 \times 10^{-4}}$$

-----

## Tarefa 5: Análise do Motor com Carga

  * **Polos:** Raízes reais e distintas:
    $$p_1 = -0,764$$
    $$p_2 = -1,182$$

**Conclusão:** O sistema é **superamortecido** e **estável**. A resposta não apresentará oscilações (overshoot).

-----

## Tarefa 6: Comparação e Análise

### Comparação de Polos

| Característica | Motor sem Carga | Motor com Carga |
| :--- | :--- | :--- |
| **Tipo de Polos** | Complexos Conjugados | Reais Distintos |
| **Valores** | $-1,205 \pm j8,946$ | $-0,764$, $-1,182$ |
| **Comportamento** | Oscilatório (Subamortecido) | Não Oscilatório (Superamortecido) |

*Figura 1: Comparação da posição dos polos no plano s. (Nota: Certifique-se de que a imagem existe na pasta /images)*

### Mudança nos Modos Característicos

A adição da carga aumentou significativamente a inércia ($J$) e o atrito ($B$). Isso alterou o discriminante da equação característica de negativo para positivo, eliminando as oscilações naturais do sistema.

*Figura 2: Comparação da resposta ao degrau unitário.*

### Análise no Domínio da Frequência

O diagrama de Bode confirma a análise temporal: o pico de ressonância presente no sistema sem carga desaparece quando a carga é acoplada.

*Figura 3: Diagramas de Bode comparando a resposta em frequência.*

-----

## Conclusão

1.  A modelagem resultou em sistemas de segunda ordem estáveis.
2.  **Sem Carga:** O motor é rápido, mas oscilatório ($\tau \approx 0,83s$).
3.  **Com Carga:** O motor torna-se mais lento e suave ($\tau \approx 1,31s$).
4.  A carga atua como um "amortecedor" dinâmico, alterando a natureza da resposta de subamortecida para superamortecida.

-----

## Apêndice A: Resultados Numéricos Resumidos

### Motor sem Carga

$$G(s) = \frac{0,0131}{2,132 \times 10^{-6} s^2 + 5,137 \times 10^{-6} s + 1,737 \times 10^{-4}}$$

  * $\omega_n \approx 9,02 \, rad/s$
  * $\zeta \approx 0,134$

### Motor com Carga

$$G(s) = \frac{0,0131}{2,153 \times 10^{-4} s^2 + 4,192 \times 10^{-4} s + 1,946 \times 10^{-4}}$$

  * Modo dominante: $\tau_1 = 1,31 \, s$
