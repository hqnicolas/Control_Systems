# Aula 05 - Estabilidade

## Principais requisitos no projeto de um sistema de controle:
- Resposta transitória;
- Estabilidade;
- Erro em regime permanente.

![image](https://github.com/user-attachments/assets/6b8af428-0573-4c64-8bd4-1d8345edd58b)

**Nota:** A estabilidade é a especificação mais importante. Existem muitas definições de estabilidade. Nesta aula, focaremos em sistemas lineares e invariantes no tempo.

---

## Estabilidade

Para esta classe de sistemas dinâmicos, a resposta total \( y(t) \) é composta por:
1. **Resposta natural (solução homogênea ou complementar):**
   - Descreve o modo como o sistema dissipa ou obtém energia;
   - A forma ou natureza desta resposta depende apenas do sistema, e não da entrada.

2. **Resposta forçada (solução particular):**
   - A forma ou natureza depende da entrada.

---

## Definições de Estabilidade
1. Um sistema linear invariante no tempo é **estável** se a resposta natural tende a zero à medida que o tempo tende a infinito.
2. Um sistema linear invariante no tempo é **instável** se a resposta natural aumenta sem limites à medida que o tempo tende a infinito.
3. Um sistema linear invariante no tempo é **marginalmente estável** caso a resposta natural:
   - Não decaia nem aumente;
   - Mas permaneça constante ou oscile à medida que o tempo tende a infinito.

---

## Estabilidade BIBO
**BIBO = Bounded-Input, Bounded-Output (entrada limitada, saída limitada):**
- Um sistema é **estável no sentido BIBO** se para todo sinal de entrada limitado, a saída do sistema permanecer limitada.
- Um sistema é **instável no sentido BIBO** se para todo sinal de entrada limitado, a saída do sistema crescer ilimitadamente.
- Um sistema é **marginalmente estável no sentido BIBO** se, para determinados sinais de entrada limitados, a saída do sistema crescer ilimitadamente.

---

## Estabilidade Assintótica Interna
**Conceito:** Um sistema é estável se:
1. A variável de saída e todas as variáveis internas do sistema nunca apresentarem valores ilimitados;
2. Elas convergirem para zero com o tempo tendendo a infinito, assumindo um conjunto de condições iniciais suficientemente pequeno.

### Exemplo:
- **Resposta natural:**
  O sistema será dito estável se, e somente se, todo termo da equação abaixo tender a zero com o tempo tendendo a infinito:

![image](https://github.com/user-attachments/assets/591b8fee-214b-44ff-b60f-84771a15187e)

  Isso ocorrerá se **todos os polos do sistema** estiverem estritamente localizados no semiplano esquerdo do plano \( s \).

---

## Exemplos de Estabilidade Assintótica Interna:
1. **Sistema estável:**

![image](https://github.com/user-attachments/assets/6c9a9688-d8d1-47a4-98d2-31818fa911c9)
   
3. **Sistema instável:** 

![image](https://github.com/user-attachments/assets/595f6ea2-375e-4d05-b18c-170e0678c7b2)


---

## Critério de Estabilidade de Routh-Hurwitz
**Passos:**
1. Requer a construção de uma tabela cujos elementos são funções dos coeficientes do denominador.
2. O número de mudanças de sinal na primeira coluna da tabela é igual ao número de polos no semiplano direito do plano \( s \).

![image](https://github.com/user-attachments/assets/101a950a-c273-46a0-a63e-3649030b4f86)

### Exemplo 1:
Construa a tabela de Routh para o sistema abaixo:

![image](https://github.com/user-attachments/assets/1715d08f-fbe2-457b-ac58-8b778a4dec21)

**Conclusão:** Ocorreram duas mudanças de sinal na primeira coluna. Logo, existem dois polos no semiplano direito do plano \( s \), indicando que o sistema é **instável**.

### Exemplo 2:
Determine a faixa de valores de ganho \( K \), admitindo \( K > 0 \), para que o sistema seja estável e instável:
- Sistema estável para \( 0 < K < 1386 \);
- Sistema instável para \( K > 1386 \).

![image](https://github.com/user-attachments/assets/cb8c119e-ea76-4227-a8ac-87831cef2a03)

