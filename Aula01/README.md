## ✅ Classificação de sinais quanto à **energia** e à **potência**

### 1. **Sinal de Energia**

- **Definição:** Um sinal x(t) (ou x[n]) é **de energia** se a **energia total** dele for **finita**:

  - Contínuo:
  
    E = ∫ |x(t)|² dt, de -∞ até ∞ — e esse valor deve ser finito.

  - Discreto:
  
    E = Σ |x[n]|², de n = -∞ até ∞ — também com valor finito.

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
  
    P = lim (T → ∞) [1 / (2T)] ∫ |x(t)|² dt, de -T até T — e P deve ser finita e maior que zero.

  - Discreto:
  
    P = lim (N → ∞) [1 / (2N + 1)] Σ |x[n]|², de n = -N até N — idem.

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
