
## 1. Motor Sem Carga
Neste cenário, o sistema apresenta **polos complexos conjugados**, indicando um comportamento oscilatório (subamortecido).

### 🔹 Função de Transferência
$$G(s) = \frac{0.0131}{2.132000 \times 10^{-6}s^2 + 5.137000 \times 10^{-6}s + 1.737025 \times 10^{-4}}$$

### 🔹 Polos
$$p_{1,2} = -1.204737 \pm 8.945534j$$

* **p1:** $-1.204737 + 8.945534j$
* **p2:** $-1.204737 - 8.945534j$

---

## 2. Motor Com Carga
Com a adição de carga, os polos tornam-se **reais e distintos**, alterando o comportamento para superamortecido (sem oscilação).

### 🔸 Função de Transferência
$$G(s) = \frac{0.0131}{2.153320 \times 10^{-4}s^2 + 4.192070 \times 10^{-4}s + 1.946275 \times 10^{-4}}$$

### 🔸 Polos
* **p1:** $-1.182330$
* **p2:** $-0.764464$

---

## 📋 Resumo Comparativo

| Parâmetro | Motor Sem Carga | Motor Com Carga |
| :--- | :--- | :--- |
| **Tipo de Polos** | Complexos Conjugados | Reais Distintos |
| **Estabilidade** | Estável (Parte real negativa) | Estável (Parte real negativa) |
| **Comportamento** | Oscilatório | Não-Oscilatório |