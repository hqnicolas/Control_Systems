## ✅ Classificação de sinais quanto à **energia** e à **potência**

### 1. **Sinal de Energia**

- **Definição:** Um sinal x(t) (ou x[n]) é **de energia** se a **energia total** dele for **finita**:

  - Contínuo:

    $$

    E = \int_{-\infty}^{\infty} |x(t)|^2 \, dt < \infty

    $$

  - Discreto:

    $$

    E = \sum_{n=-\infty}^{\infty} |x[n]|^2 < \infty

    $$


- **Características:**
  - Tipicamente **transitórios**
  - **Tendem a zero** conforme t → ∞
  - Exemplos:
    - Pulsos
    - Exponenciais decrescentes
    - Sinais com duração finita

### 2. **Sinal de Potência**

- **Definição:** Um sinal é de **potência** se sua **potência média** for **finita e diferente de zero**, mesmo que a energia total seja infinita:

  - Contínuo:

    $$

    P = \lim_{T \to \infty} \frac{1}{2T} \int_{-T}^{T} |x(t)|^2 \, dt < \infty, \quad P > 0

    $$

  - Discreto:

    $$

    P = \lim_{N \to \infty} \frac{1}{2N+1} \sum_{n=-N}^{N} |x[n]|^2 < \infty, \quad P > 0

    $$

- **Características:**
  - Tipicamente **periódicos**
  - Não tendem a zero
  - Energia total é **infinita**
  - Exemplos:
    - Senoides
    - Cossenos
    - Qualquer sinal periódico com amplitude constante

---

### ❌ Um sinal **não pode ser** de energia **e** de potência ao mesmo tempo.

---

## 🎯 Resumo:

| Tipo de Sinal   | Energia Total | Potência Média | Exemplos                          |
|-----------------|----------------|----------------|-----------------------------------|
| **De Energia**  | Finita         | Zero           | Pulsos, exponenciais decrescentes |
| **De Potência** | Infinita       | Finita (> 0)   | Senoides, sinais periódicos       |


- **Sinais periódicos** → normalmente **sinais de potência**
- **Sinais que tendem a zero** → normalmente **sinais de energia**
