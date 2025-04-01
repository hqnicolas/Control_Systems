## Exercício no Octave - Análise de Polos e Resposta ao Degrau

Neste exercício, analisamos a resposta ao degrau e os polos do sistema para diferentes valores de \( k \) utilizando Octave.

---

### Passos:

1. **Definir o valor de \( k = 19 \) e calcular a função de transferência:**
```octave
k = 19
t = tf([0 0 k (6*k)], [1 5 (4+k) (6*k)])
pole(t)
step(t)
```

![exemplo3 1](https://github.com/user-attachments/assets/2f060df7-705e-4fcc-94f6-219b2dd9be2b)

---

2. **Definir \( k = 1 \) e calcular a função de transferência:**
```octave
k = 1
t = tf([0 0 k (6*k)], [1 5 (4+k) (6*k)])
pole(t)
step(t)
```

![exemplo3 2](https://github.com/user-attachments/assets/8f2bc7dc-6104-481c-98c3-96fb24cca1e4)

---

3. **Repetir a análise para \( k = 19 \):**
```octave
k = 19
t = tf([0 0 k (6*k)], [1 5 (4+k) (6*k)])
pole(t)
step(t)
```
---

### Explicação:

- **Polos do sistema:**  
  Os valores dos polos indicam a estabilidade do sistema. Se todos os polos tiverem parte real negativa, o sistema será **estável**; se houver polos com parte real positiva, ele será **instável**.

- **Resposta ao degrau:**  
  A resposta ao degrau ajuda a visualizar o comportamento do sistema em relação a uma entrada em regime permanente.


![exempl03 3](https://github.com/user-attachments/assets/cd60a4b2-addd-4d28-a0ec-536d778204f5)

---

### Conclusão:

- A alteração do valor de \( k \) influencia diretamente a estabilidade e a resposta ao degrau do sistema.
- O comportamento do sistema pode ser analisado observando os polos e a curva da resposta ao degrau.
