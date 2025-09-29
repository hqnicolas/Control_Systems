# CAPÍTULO 1: SINAIS E SISTEMAS

## 1.6 SISTEMAS
[cite_start]Como mencionado na Seção 1.1, sistemas são utilizados para processar sinais para permitir modificação ou extração de informação adicional dos sinais. [cite: 4] [cite_start]Um sistema pode ser constituído por componentes físicos (implementação em hardware) ou pode ser um algoritmo que calcula o sinal de saída a partir de um sinal de entrada (implementação em software). [cite: 5]

[cite_start]Falando genericamente, um sistema físico é constituído por componentes interconectados, os quais são caracterizados por sua relação terminal (entrada/saída). [cite: 6] [cite_start]Além disso, o sistema é governado pelas leis de interconexão. [cite: 7] [cite_start]Por exemplo, em sistemas elétricos, as relações terminais são as relações tensão/corrente que conhecemos para resistores, capacitores, indutores, transformadores, transistores e assim por diante, além das leis de interconexão (por exemplo, leis de Kirchhoff). [cite: 8] [cite_start]Usando estas leis, podemos determinar equações matemáticas relacionando as saídas às entradas. [cite: 9] [cite_start]Estas equações, então, representam o modelo matemático do sistema. [cite: 10]

[cite_start]Um sistema pode ser convenientemente ilustrado por uma "caixa preta", como um conjunto de terminais acessíveis nos quais as variáveis de entrada $x_{1}(t),x_{2}(t),...,x_{j}(t)$ são aplicadas e outro conjunto de terminais acessíveis nos quais as variáveis de saída $y_{1}(t),y_{2}(t),...,y_{k}(t)$ são observadas (Fig. 1.25). [cite: 11]

[cite_start]*[Figura 1.25 Representação de um sistema.]* [cite: 34]

[cite_start]O estudo de sistemas consiste em três grandes áreas: modelagem matemática, análise e projeto. [cite: 12] [cite_start]Apesar de estarmos trabalhando com modelagem matemática, nosso objetivo principal está na análise e projeto. [cite: 13] [cite_start]A maior parte deste livro é dedicada ao problema de análise como determinar as saídas do sistema para dadas entradas, dado o modelo matemático do sistema (ou regras que governam o sistema). [cite: 14] [cite_start]Em uma proporção menor, também iremos considerar o problema de projeto ou síntese como construir um sistema que irá produzir um determinado conjunto de saídas de dadas entradas. [cite: 15]

### [cite_start]DADOS NECESSÁRIOS PARA DETERMINAR A RESPOSTA DO SISTEMA [cite: 16]
[cite_start]Para compreender quais dados são necessários para calcular a resposta de um sistema, considere um circuito RC simples com uma fonte de corrente $x(t)$ como entrada (Fig. 1.26). [cite: 17] [cite_start]A tensão de saída $y(t)$ é dada por [cite: 18]
$$
y(t)=Rx(t)+\frac{1}{C}\int_{-\infty}^{t}x(\tau)d\tau
$$
(1.36a) [cite_start][cite: 19, 21]

Dessa forma, a Eq. (1.36a) [cite_start]pode ser escrita como [cite: 23]
$$
y(t)=Rx(t)+\frac{1}{C}\int_{-\infty}^{0}x(\tau)d\tau+\frac{1}{C}\int_{0}^{t}x(\tau)d\tau
$$
(1.36b) [cite_start][cite: 24, 26]

O termo médio do lado direito é $v_{c}(0)$ a tensão do capacitor para $t=0$. [cite_start]Portanto, [cite: 25]
$$
y(t)=v_{C}(0)+Rx(t)+\frac{1}{C}\int_{0}^{t}x(t)dt \quad t\ge0
$$
(1.36c) [cite_start][cite: 27]

[cite_start]*[Figura 1.26 Exemplo de um sistema elétrico simples.]* [cite: 43]

[cite_start]Essa equação pode ser facilmente generalizada para [cite: 44]
$$
y(t)=v_{C}(t_{0})+Rx(t)+\frac{1}{C}\int_{t_{0}}^{t}x(\tau)d~\tau \quad t\ge t_{0}
$$
(1.36d) [cite_start][cite: 45, 46]

A partir da Eq. (1.36a)[cite_start], a tensão de saída $y(t)$ no instante pode ser calculada se soubermos a corrente de entrada fluindo no capacitor durante todo o seu passado. [cite: 47] [cite_start]Alternativamente, se soubermos a corrente de entrada $x(t)$ em algum momento $t_{0}$, então ainda podemos calcular $y(t)$ para $t\ge t_{0}$ a partir do conhecimento da corrente de entrada, desde que saibamos $v_{C}(t_{0})$, a tensão inicial do capacitor (tensão em $t_{0}$). [cite: 48] [cite_start]Portanto $v_{c}(t_{0})$ contém toda informação relevante sobre todo o passado do circuito que precisamos para calcular $y(t)$. [cite: 49]

[cite_start]No exemplo anterior, precisamos de apenas uma condição inicial. [cite: 51] [cite_start]Entretanto, em sistemas mais complexos, várias condições iniciais podem ser necessárias. [cite: 51] [cite_start]Sabemos, por exemplo, que em circuitos RLC passivos, os valores iniciais de todas as correntes nos indutores e todas as tensões nos capacitores são necessárias para determinar a saída em qualquer instante $t\ge0$ se as entradas forem fornecidas no intervalo [0, t]. [cite: 52]

## [cite_start]1.7 CLASSIFICAÇÃO DE SISTEMAS [cite: 53]
[cite_start]Os sistemas podem ser classificados genericamente nas seguintes categorias: [cite: 54]
1. [cite_start]Sistemas lineares e não lineares [cite: 55]
2. [cite_start]Sistemas com parâmetros constantes ou com parâmetros variando no tempo [cite: 56]
3. [cite_start]Sistemas instantâneos (sem memória) ou dinâmicos (com memória) [cite: 57]
4. [cite_start]Sistemas causais ou não causais [cite: 58]
5. [cite_start]Sistemas contínuos ou discretos no tempo [cite: 59]
6. [cite_start]Sistemas analógicos ou digitais [cite: 60]
7. [cite_start]Sistemas inversíveis ou não inversíveis [cite: 61]
8. [cite_start]Sistemas estáveis ou instáveis [cite: 62]

### [cite_start]1.7-1 Sistemas Lineares e Não Lineares [cite: 64]

#### [cite_start]CONCEITO DE LINEARIDADE [cite: 65]
[cite_start]Um sistema cuja saída seja proporcional a sua entrada é um exemplo de um sistema linear. [cite: 66] [cite_start]Mas a linearidade implica em mais do que isto, ela também implica a propriedade aditiva. [cite: 67] [cite_start]Ou seja, se várias entradas estão atuando em um sistema, então o efeito total no sistema devido a todas estas entradas pode ser determinado considerando uma entrada por vez e assumindo todas as outras entradas iguais a zero. [cite: 74] [cite_start]O efeito total é, então, a soma de todas as componentes de efeito. [cite: 75] [cite_start]Esta propriedade pode ser descrita por para um sistema linear, se uma entrada $x_{1}$ está atuando sozinha e possui efeito $y_{1}$, e se outra entrada $x_{2}$ também atua sozinha e possui efeito $y_{2}$, então, quando as duas entradas estiverem atuando no sistema, o efeito total será $y_{1}+y_{2}$. [cite: 76] [cite_start]Portanto, se [cite: 76]
$$
x_{1}\rightarrow y_{1}
$$
e
$$
x_{2}\rightarrow y_{2}
$$
[cite_start]então, para todo $x_{1}, x_{2}$ [cite: 77]
$$
x_{1}+x_{2}\rightarrow y_{1}+y_{2}
$$
(1.38) [cite_start][cite: 82, 83]

[cite_start]Além disso, um sistema linear deve satisfazer a propriedade de homogeneidade ou escalonamento, a qual afirma que para uma número real ou imaginário arbitrário k, se uma entrada aumentar k vezes, seu efeito também aumentará k vezes. [cite: 84] [cite_start]Portanto, se [cite: 85]
$$
x\rightarrow y
$$
[cite_start]então para todo k real ou imaginário [cite: 87]
$$
kx\rightarrow ky
$$
(1.39) [cite_start][cite: 88, 89]

[cite_start]Logo, a linearidade implica duas propriedades: homogeneidade (escalonamento) e aditividade. [cite: 90] [cite_start]As duas propriedades podem ser combinadas em uma única propriedade (superposição), a qual é descrita como mostrado a seguir. [cite: 91] [cite_start]Se, [cite: 92]
$$
x_{1}\rightarrow y_{1}
$$
e
$$
x_{2}\rightarrow y_{2}
$$
[cite_start]então para todos os valores de constantes $k_{1}$ e $k_{2}$. [cite: 97]
$$
k_{1}x_{1}+k_{2}x_{2}\longrightarrow k_{1}y_{1}+k_{2}y_{2}
$$
(1.40) [cite_start][cite: 98, 100]

> [cite_start]**EXERCÍCIO E1.11** [cite: 103]
> [cite_start]Mostre que um sistema com entrada $x(t)$ e saída $y(t)$ relacionadas por $y(t)=Re[x(t)]$ satisfaz a propriedade de aditividade mas viola a propriedade de homogeneidade. [cite: 104] Logo, tal sistema é não linear. [Dica: Mostre que a Eq. (1.39) [cite_start]não é satisfeita quando k é complexo.] [cite: 105]

#### [cite_start]RESPOSTA DE UM SISTEMA LINEAR [cite: 106]
[cite_start]A saída de um sistema para $t\ge0$ é o resultado de duas causas independentes: a condição inicial do sistema (ou o estado do sistema) para $t=0$ e a entrada $x(t)$ para $t\ge0$. [cite: 109] [cite_start]Se um sistema é linear, a saída deve ser a soma das suas componentes resultantes destas duas causas: primeiro, a componente de reposta a entrada nula que resulta somente das condições iniciais para $t=0$ com a entrada $x(t)=0$ para $t\ge0$ e, então, a componente de resposta a estado nulo que resulta apenas da entrada $x(t)$ para $t\ge0$ quando as condições iniciais (para $t=0$) são consideradas iguais a zero. [cite: 109] [cite_start]Quando todas as condições iniciais apropriadas são nulas, o sistema é dito estar em estado nulo. [cite: 110]

[cite_start]Em resumo, a resposta de um sistema linear pode ser expressa como a soma das componentes de entrada nula e estado nulo: [cite: 118]
$$
\text{resposta total = resposta entrada nula + resposta estado nulo}
$$
(1.41) [cite_start][cite: 119, 120]

[cite_start]Essa propriedade de sistemas lineares, a qual permite a separação de uma saída em componentes resultantes das condições iniciais e da entrada, é chamada de propriedade de decomposição. [cite: 121] Para o circuito RC da Fig. 1.26, a resposta $y(t)$ foi determinada como sendo [veja Eq. (1.36c)[cite_start]] [cite: 122]
$$
y(t)=\underbrace{v_{C}(0)}_{\text{componente entrada nula}}+\underbrace{Rx(t)+\frac{1}{C}\int_{0}^{t}x(\tau)d\tau}_{\text{componente estado nulo}}
$$
(1.42) [cite_start][cite: 123, 124]

A partir da Eq. 1.42, fica claro que se a entrada $x(t)=0$ para $t\ge0$, a saída será $y(t)=v_{c}(0)$. [cite_start]Logo $v_{c}(0)$ é a componente de entrada nula da resposta $y(t)$. [cite: 125] Similarmente, se o estado do sistema (a tensão $v_{c}$ neste caso) for zero para $t=0$ a saída é dada pela segunda componente do lado direito da Eq. (1.42)[cite_start]. [cite: 125] [cite_start]Claramente, esta é a componente de estado nulo da resposta $y(t)$. [cite: 126]

> [cite_start]**EXEMPLO 1.9** [cite: 133]
> [cite_start]Mostre que o sistema descrito pela equação [cite: 134]
> $$
> \frac{dy}{dt}+3y(t)=x(t)
> $$
> [cite_start]é linear. [cite: 135, 136]
> [cite_start]Seja a resposta do sistema às entradas $x_{1}(t)$ e $x_{2}(t)$, $y_{1}(t)$ e $y_{2}(t)$ respectivamente. [cite: 137] Então
> $$
> \frac{dy_{1}}{dt}+3y_{1}(t)=x_{1}(t)
> $$
> e
> $$
> \frac{dy_{2}}{dt}+3y_{2}(t)=x_{2}(t)
> $$
> [cite_start]multiplicando a primeira equação por $k_{1}$, a segunda por $k_{2}$ e somando os resultados teremos [cite: 141]
> $$
> \frac{d}{dt}[k_{1}y_{1}(t)+k_{2}y_{2}(t)]+3[k_{1}y_{1}(t)+k_{2}y_{2}(t)]=k_{1}x_{1}(t)+k_{2}x_{2}(t)
> $$
> (1.43) [cite_start][cite: 142, 143]
> mas essa é a equação do sistema [Eq. (1.43)[cite_start]] com [cite: 150]
> $$
> x(t)=k_{1}x_{1}(t)+k_{2}x_{2}(t)
> $$
> e
> $$
> y(t)=k_{1}y_{1}(t)+k_{2}y_{2}(t)
> $$
> [cite_start]Portanto, quando a entrada é $k_{1}x_{1}(t)+k_{2}x_{2}(t)$, a resposta do sistema é $k_{1}y_{1}(t)+k_{2}y_{2}(t)$. [cite: 156] [cite_start]Consequentemente, o sistema é linear. [cite: 156]

[cite_start]Usando esse argumento, podemos facilmente generalizar o resultado para mostrar que um sistema descrito por uma equação diferencial na forma [cite: 157]
$$
a_{0}\frac{d^{N}y}{dt^{N}}+a_{1}\frac{d^{N-1}y}{dt^{N-1}}+\cdot\cdot\cdot+a_{N}y(t)=b_{N-M}\frac{d^{M}x}{dt^{M}}+\cdot\cdot\cdot+b_{N-1}\frac{dx}{dt}+b_{N}x(t)
$$
(1.44) [cite_start][cite: 158]
[cite_start]é um sistema linear. [cite: 159]

> [cite_start]**EXERCÍCIO E1.12** [cite: 161]
> [cite_start]Mostre que o sistema descrito pela seguinte equação é linear: [cite: 162]
> $$
> \frac{dy}{dt}+t^{2}y(t)=(2t+3)x(t)
> $$

> [cite_start]**EXERCÍCIO E1.13** [cite: 164]
> [cite_start]Mostre que o sistema descrito pela seguinte equação não é linear: [cite: 165]
> $$
> y(t)\frac{dy}{dt}+3y(t)=x(t)
> $$

#### [cite_start]MAIS COMENTÁRIOS SOBRE SISTEMAS LINEARES [cite: 167]
[cite_start]A propriedade de superposição (linearidade) simplifica em muito a análise de sistemas lineares. [cite: 173] [cite_start]Devido à propriedade de decomposição, podemos calcular separadamente as duas componentes da saída. [cite: 174] [cite_start]Além disso, se descrevermos a entrada $x(t)$ pela soma de funções mais simples, [cite: 176]
$$
x(t)=a_{1}x_{1}(t)+a_{2}x_{2}(t)+\cdot\cdot\cdot+a_{m}x_{m}(t)
$$
[cite_start]então, pela linearidade, a resposta $y(t)$ é dada por [cite: 180]
$$
y(t)=a_{1}y_{1}(t)+a_{2}y_{2}(t)+\cdot\cdot\cdot+a_{m}y_{m}(t)
$$
(1.45) [cite_start][cite: 182, 183]

[cite_start]Esta observação aparentemente trivial possui profundas implicações. [cite: 184] [cite_start]Por exemplo, considere uma entrada arbitrária $x(t)$ tal como a mostrada na Fig. 1.27a. [cite: 186] [cite_start]Podemos aproximar $x(t)$ pela soma de pulsos retangulares de largura $\Delta t$ e alturas variáveis. [cite: 187] [cite_start]Portanto, se soubermos a resposta do sistema a um impulso unitário, podemos determinar imediatamente a resposta do sistema a uma entrada $x(t)$ arbitrária através da soma das respostas do sistema a cada componente impulso de $x(t)$. [cite: 189]

[cite_start]*[Figura 1.27 Representação de sinais em termos de componentes de impulso e degrau.]* [cite: 212]

### [cite_start]1.7-2 Sistemas Invariantes e Variantes no Tempo [cite: 195]
[cite_start]Sistemas cujos parâmetros não são alterados com o tempo são invariantes no tempo (também chamados de sistemas com parâmetros constantes). [cite: 196] [cite_start]Para tais sistemas, se a entrada for atrasada por T segundos, a saída é a mesma anterior, porém atrasada também por T segundos (assumindo que as condições iniciais também sejam atrasadas T segundos). [cite: 197] [cite_start]Esta propriedade é mostrada graficamente na Fig. 1.28. [cite: 198]

[cite_start]*[Figura 1.28 Propriedade de invariância no tempo.]* [cite: 220]

[cite_start]Também podemos ilustrar esta propriedade como apresentado na Fig. 1.29. [cite: 198] [cite_start]Se o sistema for invariante no tempo, então a saída atrasada $y(t-T)$ pode ser obtida, também, atrasando primeiro a entrada $x(t)$ antes de aplicá-la ao sistema, como mostrado na Fig. 1.29b. [cite: 200] [cite_start]Em outras palavras, o sistema S e o atraso de tempo são comutativos se o sistema for invariante no tempo. [cite: 201]

[cite_start]*[Figura 1.29 Ilustração da propriedade de invariância no tempo.]* [cite: 242]

Um sistema com uma relação de entrada/saída descrita por uma equação diferencial linear na forma dada no Exemplo 1.9 [Eq. (1.44)[cite_start]] é um sistema linear invariante no tempo (LIT) quando os coeficientes $a_i$ e $b_i$ são constantes. [cite: 243] [cite_start]Se estes coeficientes forem funções do tempo, então o sistema é um sistema linear variante no tempo. [cite: 244]

> [cite_start]**EXERCÍCIO E1.14** [cite: 248]
> [cite_start]Mostre que um sistema descrito pela seguinte equação é um sistema com parâmetros variantes no tempo: [cite: 249]
> $$
> y(t)=(sen~t)x(t-2)
> $$
> [cite_start][Dica: mostre que o sistema falha ao satisfazer a propriedade de invariância no tempo.] [cite: 251]

### [cite_start]1.7-3 Sistemas Instantâneos e Dinâmicos [cite: 252]
[cite_start]Em uma classe especial de sistemas, a saída a qualquer instante $t$ depende apenas da entrada naquele instante. [cite: 254] [cite_start]Tais sistemas são chamados de sistemas instantâneos ou sem memória. [cite: 261] [cite_start]Mais precisamente, um sistema é dito instantâneo (ou sem memória) se sua saída a qualquer instante $t$ depender, no máximo, da força de sua(s) entrada(s) no mesmo instante t e não de qualquer valor passado ou futuro da(s) entrada(s). [cite: 262] [cite_start]Caso contrário, o sistema é chamado de dinâmico (ou sistema com memória). [cite: 263]

### [cite_start]1.7-4 Sistemas Causal e Não Causal [cite: 268]
[cite_start]Um sistema causal (também conhecido como físico ou não antecipativo) é aquele no qual a saída em qualquer instante $t_{0}$ depende apenas do valor da entrada $x(t)$ para $t\le t_{0}$. [cite: 269] [cite_start]Em outras palavras, o valor da saída no instante presente depende apenas do valor presente e passado da entrada $x(t)$, e não de seus valores futuros. [cite: 269] [cite_start]Para simplificar, em um sistema causal, a saída não pode começar antes da entrada ser aplicada. [cite: 270] [cite_start]Um sistema que viola a condição de causalidade é chamado de sistema não causal (ou antecipativo). [cite: 272]

[cite_start]Qualquer sistema prático que opera no tempo real deve, necessariamente, ser causal. [cite: 273] [cite_start]Por exemplo, considere o sistema especificado por [cite: 276]
$$
y(t)=x(t-2)+x(t+2)
$$
(1.46) [cite_start][cite: 277, 278]

Para a entrada $x(t)$ mostrada na Fig. 1.30a, a saída $y(t)$, calculada a partir da Eq. (1.46) [cite_start](mostrada na Fig. 1.30b), começa antes mesmo da entrada ser aplicada. [cite: 279, 280]

[cite_start]*[Figura 1.30 Um sistema não causal e sua realização por um sistema causal atrasado.]* [cite: 293]

#### [cite_start]POR QUE ESTUDAR SISTEMAS NÃO CAUSAIS? [cite: 300]
[cite_start]Eles são importantes no estudo de sistemas por diversas razões. [cite: 302]
1.  [cite_start]Sistemas não causais são realizáveis quando a variável independente for outra que não o "tempo" (por exemplo, o espaço). [cite: 303]
2.  [cite_start]Para o processamento de sinais, temos todos os dados de entrada gravados anteriormente. [cite: 309, 310] [cite_start]Um sistema não causal pode ser realizável, apesar de não ser em tempo real. [cite: 314] [cite_start]Podemos, portanto, ser capazes de implementar um sistema não causal desde que estejamos dispostos a aceitar um atraso de tempo na saída. [cite: 315] Considere um sistema cuja saída é a mesma que $y(t)$ da Eq. (1.46) [cite_start]atrasada por 2 segundos (Fig 1.30c), tal que [cite: 316, 317]
    $$
    \hat{y}(t)=y(t-2) = x(t-4)+x(t)
    $$
    [cite_start]Neste caso, a saída a qualquer instante $t$ não depende de valores futuros da entrada e o sistema é causal. [cite: 319]
3.  [cite_start]Eles fornecem um limite superior para o desempenho de sistemas causais. [cite: 330]

> [cite_start]**EXERCÍCIO E1.15** [cite: 341]
> [cite_start]Mostre que um sistema descrito pela seguinte equação é não causal: [cite: 342]
> $$
> y(t)=\int_{t-S}^{t+S}x(\tau)d\tau
> $$
> [cite_start]Mostre que esse sistema pode ser implementado fisicamente se aceitarmos um atraso de 5 segundos da saída. [cite: 344]

### [cite_start]1.7-5 Sistemas em Tempo Contínuo e em Tempo Discreto [cite: 345]
[cite_start]Sinais definidos ou especificados em uma faixa de valores contínua de tempo são sinais contínuos no tempo, representados pelos símbolos $x(t)$, $y(t)$ e assim por diante. [cite: 346] [cite_start]sistemas cujas entradas e saídas são sinais contínuos no tempo são sistemas em tempo contínuo. [cite: 347] [cite_start]Por outro lado, sinais definidos apenas em instantes discretos de tempo $t_{0},t_{1},t_{2},...t_{n},...$ são sinais discretos no tempo. [cite: 348] [cite_start]Sistemas cujas entradas e saídas são sinais discretos no tempo são sistemas em tempo discreto. [cite: 349] [cite_start]Por conveniência, iremos simplificar esta notação para $x[n], y[n],...$, onde fica entendido que $x[n]=x(nT)$ e que n é algum inteiro. [cite: 355]

[cite_start]*[Figura 1.31 Um sinal em tempo discreto.]* [cite: 373]

[cite_start]*[Figura 1.32 Processamento de sinais contínuos no tempo por sistemas discretos no tempo.]* [cite: 384]

### [cite_start]1.7-6 Sistemas Analógicos e Digitais [cite: 386]
[cite_start]Um sistema cujos sinais de entrada e saída são analógicos é um sistema analógico. [cite: 388] [cite_start]Um sistema cujos sinais de entrada e saída são digitais é um sistema digital. [cite: 389] [cite_start]Um computador digital é um exemplo de um sistema digital (binário). [cite: 390]

### [cite_start]1.7-7 Sistemas Inversíveis e Não Inversíveis [cite: 392]
[cite_start]Se pudermos obter a entrada $x(t)$ da saída $y(t)$ correspondente através de alguma operação, o sistema S é dito ser inversível. [cite: 394] [cite_start]Para um sistema inversível, é essencial que toda entrada possua uma única saída, de tal forma que exista um mapeamento de um-para-um entre a entrada e a saída correspondente. [cite: 396] [cite_start]O sistema que efetua a operação inversa é o sistema inverso de S. [cite: 397]

[cite_start]*[Figura 1.33 O cascateamento de um sistema com sua inversa resulta em um sistema identidade.]* [cite: 411]

### [cite_start]1.7-8 Sistemas Estáveis e Instáveis [cite: 401]
[cite_start]Se cada entrada limitada aplicada ao terminal de entrada resultar em uma saída limitada, o sistema é dito ser externamente estável. [cite: 403] [cite_start]Este tipo de estabilidade também é conhecida como estabilidade no sentido BIBO (bounded-input/bounded-output). [cite: 405]

> [cite_start]**EXERCÍCIO E1.16** [cite: 416]
> [cite_start]Mostre que o sistema descrito pela equação $y(t)=x^{2}(t)$ é não inversível com estabilidade no sentido BIBO. [cite: 417]

## [cite_start]1.8 MODELO DE SISTEMA: DESCRIÇÃO ENTRADA-SAÍDA [cite: 418]
[cite_start]A descrição de um sistema em termos de medidas nos terminais de entrada e saída é chamada de descrição entrada-saída. [cite: 419] [cite_start]O primeiro passo na análise de um sistema é a construção do modelo do sistema, o qual é a expressão matemática ou regra que aproxima satisfatoriamente o comportamento dinâmico do sistema. [cite: 421]

### [cite_start]1.8-1 Sistemas Elétricos [cite: 423]
[cite_start]Para construir um modelo de sistema, devemos estudar as relações entre as diferentes variáveis do sistema. [cite: 424] [cite_start]Em sistemas elétricos, por exemplo, devemos determinar um modelo satisfatório para a relação tensão-corrente de cada elemento e as leis de interconexão (Leis de Kirchhoff). [cite: 425, 427]

> [cite_start]**EXEMPLO 1.10** [cite: 430]
> [cite_start]Para o circuito RLC série da Fig. 1.34, determine a equação de entrada-saída que relaciona a tensão de entrada $x(t)$ com a corrente de saída (corrente de malha) $y(t)$. [cite: 431]
> 
> [cite_start]*[Figura 1.34]* [cite: 432]
> 
> [cite_start]Aplicando a lei de Kirchhoff das tensões para a malha teremos, [cite: 439]
> $$
> v_{L}(t)+v_{R}(t)+v_{C}(t)=x(t)
> $$
> [cite_start]Utilizando as leis de tensão-corrente de cada elemento, podemos escrever esta equação como [cite: 442]
> $$
> \frac{dy}{dt}+3y(t)+2\int_{-\infty}^{t}y(\tau)d\tau=x(t)
> $$
> [cite_start]Diferenciando os dois lados desta equação, obtemos [cite: 446]
> $$
> \frac{d^{2}y}{dt^{2}}+3\frac{dy}{dt}+2y(t)=\frac{dx}{dt}
> $$
> [cite_start]É conveniente utilizarmos a notação compacta D para o operador diferencial $d/dt$, logo, [cite: 451]
> $$
> \frac{dy}{dt}\equiv Dy(t), \quad \frac{d^{2}y}{dt^{2}}\equiv D^{2}y(t)
> $$
> Com esta notação a Eq. (1.49) [cite_start]pode ser escrita por [cite: 453]
> $$
> (D^{2}+3D+2)y(t)=Dx(t)
> $$

> [cite_start]**EXEMPLO 1.11** [cite: 487]
> [cite_start]Determine a equação relacionando a entrada e a saída para o circuito RC série da Fig. 1.35 se a entrada for a tensão $x(t)$ e a saída for (a) a corrente de malha $i(t)$ (b) a tensão do capacitor $y(t)$. [cite: 488, 489, 491]
> 
> [cite_start]*[Figura 1.35]* [cite: 492]
> 
> (a) [cite_start]A equação de malha para o circuito é [cite: 502]
> $$
> R~i(t)+\frac{1}{C}\int_{-\infty}^{t}i(\tau)d\tau=x(t) \quad \Rightarrow \quad 15~i(t)+5\int_{-\infty}^{t}i(\tau)d\tau=x(t)
> $$
> (b) [cite_start]...Substituindo a relação $i(t)=C\frac{dy}{dt} = \frac{1}{5}Dy(t)$ na equação diferencial da malha resulta em [cite: 514, 515, 516]
> $$
> (3D+1)y(t)=x(t)
> $$
> [cite_start]ou [cite: 520]
> $$
> 3\frac{dy}{dt}+y(t)=x(t)
> $$

> [cite_start]**EXERCÍCIO E1.17** [cite: 526]
> [cite_start]Para o circuito RLC da Fig. 1.34, determine a relação de entrada-saída se a saída for a tensão $v_{L}(t)$ do indutor. [cite: 527]
> [cite_start]**RESPOSTA:** $(D^{2}+3D+2)v_{L}(t)=D^{2}x(t)$ [cite: 528, 529]

> [cite_start]**EXERCÍCIO E1.18** [cite: 530]
> [cite_start]Para o circuito RLC da Fig. 1.34, determine a relação de entrada-saída se a saída for a tensão $v_{c}(t)$ do capacitor. [cite: 531]
> [cite_start]**RESPOSTA:** $(D^{2}+3D+2)v_{C}(t)=2x(t)$ [cite: 532, 533]

### [cite_start]1.8-2 Sistemas Mecânicos [cite: 534]
#### [cite_start]SISTEMAS TRANSLACIONAIS [cite: 537]
[cite_start]Os elementos básicos são massas ideais, molas lineares e amortecedores. [cite: 538]
* [cite_start]**Massa M:** $x(t)=M\ddot{y}(t)=M\frac{d^{2}y}{dt^{2}}=MD^{2}y(t)$ [cite: 541, 542]
* [cite_start]**Mola Linear K:** $x(t)=Ky(t)$ [cite: 543, 545]
* [cite_start]**Amortecedor Linear B:** $x(t)=B\dot{y}(t)=B\frac{dy}{dt}=BDy(t)$ [cite: 549, 550]

[cite_start]*[Figura 1.36 Alguns elementos em sistemas mecânicos translacionais.]* [cite: 562]

> [cite_start]**EXEMPLO 1.12** [cite: 566]
> Determine a relação entrada-saída para o sistema mecânico translacional mostrado na Fig. 1.37a. [cite_start]A entrada é a força $x(t)$ e a saída é a posição da massa $y(t)$. [cite: 567, 568]
> 
> [cite_start]*[Figura 1.37]* [cite: 586]
> 
> Usando a segunda lei de Newton, a força total deve ser $M\ddot{y}(t)$. [cite_start]Logo, [cite: 591]
> $$
> M\ddot{y}(t)=-B\dot{y}(t)-Ky(t)+x(t)
> $$
> [cite_start]ou [cite: 592]
> $$
> (MD^{2}+BD+K)y(t)=x(t)
> $$

#### [cite_start]SISTEMAS ROTACIONAIS [cite: 596]
[cite_start]As variáveis são torque, posição angular ($\theta$), etc. [cite: 598]
* [cite_start]**Momento de Inércia J:** $torque=J\ddot{\theta}=J\frac{d^{2}\theta}{dt^{2}}=JD^{2}\theta(t)$ [cite: 603, 604]
* [cite_start]**Mola de Torção K:** $torque=K\theta$ [cite: 609, 610]
* [cite_start]**Amortecedor de Torção B:** $torque=B\dot{\theta}(t)=BD\theta(t)$ [cite: 612, 613]

### [cite_start]1.8-3 Sistemas Eletromecânicos [cite: 665]
[cite_start]Consideraremos um exemplo de um motor CC controlado pela armadura. [cite: 667] [cite_start]O torque $\mathcal{T}(t)$ gerado pelo motor é proporcional a corrente de armadura $x(t)$. [cite: 668] [cite_start]Portanto, [cite: 668]
$$
\mathcal{T}(t)=K_{T}x(t)
$$
[cite_start]Se J é o momento de inércia da carga e B o coeficiente de amortecimento, então [cite: 672]
$$
J\ddot{\theta}(t)=\mathcal{T}(t)-B\dot{\theta}(t)
$$
[cite_start]Logo, [cite: 691]
$$
(JD^{2}+BD)\theta(t)=\mathcal{T}(t) = K_{T}x(t)
$$
[cite_start]ou [cite: 692, 694]
$$
J\frac{d^{2}\theta}{dt^{2}}+B\frac{d\theta}{dt}=K_{T}x(t)
$$

## [cite_start]1.9 DESCRIÇÃO INTERNA E EXTERNA DE UM SISTEMA [cite: 697]
[cite_start]A relação de entrada-saída de um sistema é uma descrição externa do sistema. [cite: 699] [cite_start]Uma descrição interna é capaz de fornecer a informação completa sobre todos os possíveis sinais do sistema. [cite: 707] [cite_start]Uma descrição externa pode não fornecer uma informação completa como esta. [cite: 708]

[cite_start]Considere o circuito da Fig. 1.41a. [cite: 711] [cite_start]Para a descrição externa, nenhuma medição ou observação externa pode detectar a presença do capacitor. [cite: 744, 745] [cite_start]Se o circuito estiver encapsulado, é impossível determinar as correntes ou tensões internas a partir de medições externas. [cite: 746]

[cite_start]*[Figura 1.41 Um sistema que não pode ser descrito por medidas externas.]* [cite: 737]

[cite_start]Isso ocorre quando o sistema é não controlável ou não observável. [cite: 750] [cite_start]Na Fig. 1.42a, parte do sistema (subsistema $S_{2}$) não pode ser controlada pela entrada $x(t)$. [cite: 752] [cite_start]Na Fig. 1.42b, algumas das saídas do sistema (aquelas no subsistema $S_{2}$) não podem ser observadas a partir dos terminais de saída. [cite: 752]

[cite_start]*[Figura 1.42 Estruturas de sistemas não controláveis e não observáveis.]* [cite: 760]

## [cite_start]1.10 DESCRIÇÃO INTERNA: DESCRIÇÃO EM ESPAÇO DE ESTADO [cite: 766]
[cite_start]Nesta abordagem, identificamos certas variáveis chave, chamadas de variáveis de estado. [cite: 768] [cite_start]Em um circuito RLC passivo, as tensões independentes dos capacitores e as correntes dos indutores são as variáveis de estado. [cite: 770] [cite_start]O conhecimento das variáveis de estado permite que toda possível saída do sistema seja calculada. [cite: 785]

> [cite_start]**EXEMPLO 1.14** [cite: 804]
> [cite_start]Considere o circuito da Fig. 1.43 com $q_{1}$ e $q_{2}$ como variáveis de estado e escreva as equações de estado. [cite: 806, 807]
> 
> [cite_start]*[Figura 1.43 Escolhendo condições iniciais adequadas em um circuito.]* [cite: 800]
> 
> [cite_start]Como $\dot{q}_{1}$ é a corrente através do capacitor, [cite: 808]
> $$
> \dot{q}_{1}=i_{c}=i_{1}-i_{2}-q_{2} = (x-q_{1})-0,5q_{1}-q_{2} = -1.5q_{1}-q_{2}+x
> $$
> [cite_start]Além disso, $2\dot{q}_{2}$, a tensão do indutor, é dada por [cite: 813]
> $$
> 2\dot{q}_{2}=q_{1}-v_{3} = q_{1}-5q_{2} \quad \Rightarrow \quad \dot{q}_{2}=0.5q_{1}-2.5q_{2}
> $$
> [cite_start]Portanto, as equações de estado são [cite: 814]
> $$
> \dot{q}_{1}=-1.5q_{1}-q_{2}+x
> $$
> $$
> \dot{q}_{2}=0,5q_{1}-2.5q_{2}
> $$

> [cite_start]**EXEMPLO 1.15** [cite: 827]
> [cite_start]Neste exemplo, investigaremos a natureza das equações de estado e a questão de controlabilidade e observabilidade para o circuito da Fig. 1.41a. [cite: 828] [cite_start]Existe apenas uma variável de estado, a tensão do capacitor $q(t)$. [cite: 829]
> [cite_start]... a equação da malha acba é [cite: 858]
> $$
> q=2[-\frac{x}{10}-\frac{\dot{q}}{2}]+2[\frac{x}{10}-\frac{\dot{q}}{2}]=-2\dot{q}
> $$
> [cite_start]ou [cite: 889]
> $$
> \dot{q}=-0.5q
> $$
> [cite_start]Esta é a equação de estado desejada. [cite: 891] [cite_start]A saída $y(t)$ é dada por [cite: 897]
> $$
> y(t)=2[\frac{x}{10}-\frac{\dot{q}}{2}]+2[\frac{x}{10}+\frac{\dot{q}}{2}] = \frac{2}{5}x(t)
> $$
> [cite_start]A equação de estado mostra que o estado $q(t)$ é independente da entrada $x(t)$, portanto, o estado do sistema q não pode ser controlado pela entrada. [cite: 901] [cite_start]Além disso, a equação de saída mostra que a saída $y(t)$ não depende do estado $q(t)$. [cite: 902] [cite_start]Logo, o estado do sistema não pode ser observado a partir dos terminais de saída. [cite: 902] [cite_start]Desta forma, o sistema não é nem controlável e nem observável. [cite: 903]

[cite_start]Técnicas de espaço de estado são úteis por várias razões, incluindo: [cite: 908]
1.  [cite_start]Grande generalidade (sistemas não lineares, variantes no tempo, MIMO). [cite: 909, 910, 911]
2.  [cite_start]Uso de notação matricial e álgebra linear. [cite: 912]
3.  [cite_start]Fácil simulação em computadores digitais. [cite: 915]
4.  [cite_start]Para sistemas de segunda ordem, um método gráfico (análise no plano de fase) pode ser utilizado. [cite: 916]

> [cite_start]**EXERCÍCIO Ε1.20** [cite: 926]
> [cite_start]Escreva as equações de estado para o circuito RLC série mostrado na Fig. 1.45 utilizando a corrente do indutor $q_{1}(t)$ e a tensão do capacitor $q_{2}(t)$ como variáveis de estado. [cite: 927]
> 
> [cite_start]*[Figura 1.45]* [cite: 935]
> 
> [cite_start]**RESPOSTA** [cite: 936]
> $$
> \dot{q}_{1}=-3q_{1}-q_{2}+x
> $$
> $$
> \dot{q}_{2}=2q_{1}
> $$

## [cite_start]1.11 RESUMO [cite: 938]
[cite_start]Um sinal é um conjunto de dados ou informação. [cite: 939] [cite_start]Um sistema processa um sinal de entrada para produzir sinais de saída. [cite: 939] [cite_start]Um sistema pode ser implementado em hardware ou software. [cite: 940]

[cite_start]Uma medida do tamanho de um sinal é sua energia ou potência. [cite: 941, 942] [cite_start]Sinais podem ser classificados de diversas formas: [cite: 946]
1.  [cite_start]**Contínuo no tempo** vs. **Discreto no tempo**: qualifica a natureza do sinal ao longo do eixo do tempo. [cite: 947, 948, 951]
2.  [cite_start]**Analógico** vs. **Digital**: qualifica a natureza da amplitude do sinal. [cite: 949, 950, 952]
3.  [cite_start]**Periódico** vs. **Não periódico**: um sinal periódico $x(t)$ satisfaz $x(t)=x(t+T_{0})$ e existe em todo o intervalo de tempo de $-\infty<t<\infty$. [cite: 953, 955] [cite_start]Um sinal causal é zero para $t<0$. [cite: 957]
4.  [cite_start]**Sinal de energia** vs. **Sinal de potência**: um sinal pode ser um ou outro, mas não os dois. [cite: 958, 959, 960] [cite_start]Existem também sinais que não são nem de energia nem de potência. [cite: 961]
