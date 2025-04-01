## Exercício no Octave

Neste exercício, analisamos diferentes valores de \( k \) para observar a resposta e os polos do sistema utilizando o Octave.

---

### Passos:
1. Definir o valor de \( k \) (exemplo: \( k = 1386 \)):
```octave
k = 1386
>> t = tf([0 0 k], [1 18 77 k])
```

![exemplo2](https://github.com/user-attachments/assets/7e3cb5a5-ad28-4c40-b5ee-9c6d0974d90e)


**Resultado:**
Transfer function do sistema:
\[
T(s) = \frac{1386}{s^3 + 18s^2 + 77s + 1386}
\]

---

2. Alterar o valor de \( k \) (exemplo: \( k = 1 \)):
```octave
k = 1
>> t = tf([0 0 k], [1 18 77 k])
```

![exemplo2 1](https://github.com/user-attachments/assets/a2a8d8d9-ac05-4c10-b994-94e768b06235)


**Resultado:**
Transfer function do sistema:
\[
T(s) = \frac{1}{s^3 + 18s^2 + 77s + 1}
\]

---

3. Simular resposta ao impulso por 5 segundos:
```octave
>> impulse(t,5)
```

---

4. Calcular os polos do sistema:
```octave
>> pole(t)
ans =
  -11.023
  -6.964
  -0.013
```

**Explicação dos Polos:**
- As partes reais de todos os polos são negativas, indicando que o sistema é **estável**.
- Os valores dos polos ajudam a determinar o comportamento dinâmico do sistema.

---

5. Simular resposta ao degrau:
```octave
>> step(t)
```

![exemplo2 2](https://github.com/user-attachments/assets/f92dc24e-0999-4f6e-8d6a-817b622e81bc)


**Observação:** A resposta ao degrau pode ser utilizada para verificar o comportamento transitório e em regime permanente do sistema.

---

### Conclusão:
- Para \( k = 1386 \), o sistema apresenta diferentes polos e uma resposta mais intensa devido ao valor do ganho elevado.
- Para \( k = 1 \), o sistema possui polos diferentes, com uma dinâmica mais atenuada.
