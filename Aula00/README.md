# CAPÍTULO 1: SINAIS E SISTEMAS

## 1.6 SISTEMAS
Como mencionado na Seção 1.1, sistemas são utilizados para processar sinais para permitir modificação ou extração de informação adicional dos sinais. Um sistema pode ser constituído por componentes físicos (implementação em hardware) ou pode ser um algoritmo que calcula o sinal de saída a partir de um sinal de entrada (implementação em software). Falando genericamente, um sistema físico é constituído por componentes interconectados, os quais são caracterizados por sua relação terminal (entrada/saída). 

Além disso, o sistema é governado pelas leis de interconexão. Por exemplo, em sistemas elétricos, as relações terminais são as relações tensão/corrente que conhecemos para resistores, capacitores, indutores, transformadores, transistores e assim por diante, além das leis de interconexão (por exemplo, leis de Kirchhoff). Usando estas leis, podemos determinar equações matemáticas relacionando as saídas às entradas. Estas equações, então, representam o modelo matemático do sistema. 

Um sistema pode ser convenientemente ilustrado por uma "caixa preta", como um conjunto de terminais acessíveis nos quais as variáveis de entrada $x_{1}(t),x_{2}(t),...,x_{j}(t)$ são aplicadas e outro conjunto de terminais acessíveis nos quais as variáveis de saída $y_{1}(t),y_{2}(t),...,y_{k}(t)$ são observadas (Fig. 1.25). 

<img width="315" height="149" alt="image" src="https://github.com/user-attachments/assets/021d0b77-9512-4d4a-a120-513da18fe3d0" />

*[Figura 1.25 Representação de um sistema.]* 

O estudo de sistemas consiste em três grandes áreas: modelagem matemática, análise e projeto. Apesar de estarmos trabalhando com modelagem matemática, nosso objetivo principal está na análise e projeto. A maior parte deste livro é dedicada ao problema de análise como determinar as saídas do sistema para dadas entradas, dado o modelo matemático do sistema (ou regras que governam o sistema). Em uma proporção menor, também iremos considerar o problema de projeto ou síntese como construir um sistema que irá produzir um determinado conjunto de saídas de dadas entradas.

### DADOS NECESSÁRIOS PARA DETERMINAR A RESPOSTA DO SISTEMA 

Para compreender quais dados são necessários para calcular a resposta de um sistema, considere um circuito RC simples com uma fonte de corrente $x(t)$ como entrada (Fig. 1.26). A tensão de saída $y(t)$ é dada por 

$$
y(t)=Rx(t)+\frac{1}{C}\int_{-\infty}^{t}x(\tau)d\tau
$$

(1.36a) Dessa forma, a Eq. (1.36a) pode ser escrita como 

$$
y(t)=Rx(t)+\frac{1}{C}\int_{-\infty}^{0}x(\tau)d\tau+\frac{1}{C}\int_{0}^{t}x(\tau)d\tau
$$

(1.36b) O termo médio do lado direito é $v_{c}(0)$ a tensão do capacitor para $t=0$. Portanto, 

$$
y(t)=v_{C}(0)+Rx(t)+\frac{1}{C}\int_{0}^{t}x(t)dt \quad t\ge0
$$

<img width="583" height="279" alt="image" src="https://github.com/user-attachments/assets/5750daba-889b-4dd6-bbfd-4bd7c5824762" />

(1.36c) *[Figura 1.26 Exemplo de um sistema elétrico simples.]* 

Essa equação pode ser facilmente generalizada para 

$$
y(t)=v_{C}(t_{0})+Rx(t)+\frac{1}{C}\int_{t_{0}}^{t}x(\tau)d~\tau \quad t\ge t_{0}
$$

(1.36d) A partir da Eq. (1.36a), a tensão de saída $y(t)$ no instante pode ser calculada se soubermos a corrente de entrada fluindo no capacitor durante todo o seu passado. Alternativamente, se soubermos a corrente de entrada $x(t)$ em algum momento $t_{0}$, então ainda podemos calcular $y(t)$ para $t\ge t_{0}$ a partir do conhecimento da corrente de entrada, desde que saibamos $v_{C}(t_{0})$, a tensão inicial do capacitor (tensão em $t_{0}$). Portanto $v_{c}(t_{0})$ contém toda informação relevante sobre todo o passado do circuito que precisamos para calcular $y(t)$. No exemplo anterior, precisamos de apenas uma condição inicial. Entretanto, em sistemas mais complexos, várias condições iniciais podem ser necessárias. Sabemos, por exemplo, que em circuitos RLC passivos, os valores iniciais de todas as correntes nos indutores e todas as tensões nos capacitores são necessárias para determinar a saída em qualquer instante $t\ge0$ se as entradas forem fornecidas no intervalo [0, t]. 

## 1.7 CLASSIFICAÇÃO DE SISTEMAS 

Os sistemas podem ser classificados genericamente nas seguintes categorias: 1. Sistemas lineares e não lineares 2. Sistemas com parâmetros constantes ou com parâmetros variando no tempo 3. Sistemas instantâneos (sem memória) ou dinâmicos (com memória) 4. Sistemas causais ou não causais 5. Sistemas contínuos ou discretos no tempo 6. Sistemas analógicos ou digitais 7. Sistemas inversíveis ou não inversíveis 8. Sistemas estáveis ou instáveis 

### 1.7-1 Sistemas Lineares e Não Lineares 

#### CONCEITO DE LINEARIDADE 

Um sistema cuja saída seja proporcional a sua entrada é um exemplo de um sistema linear. Mas a linearidade implica em mais do que isto, ela também implica a propriedade aditiva. Ou seja, se várias entradas estão atuando em um sistema, então o efeito total no sistema devido a todas estas entradas pode ser determinado considerando uma entrada por vez e assumindo todas as outras entradas iguais a zero. O efeito total é, então, a soma de todas as componentes de efeito. Esta propriedade pode ser descrita por para um sistema linear, se uma entrada $x_{1}$ está atuando sozinha e possui efeito $y_{1}$, e se outra entrada $x_{2}$ também atua sozinha e possui efeito $y_{2}$, então, quando as duas entradas estiverem atuando no sistema, o efeito total será $y_{1}+y_{2}$. Portanto, se 

$$
x_{1}\rightarrow y_{1}
$$

e

$$
x_{2}\rightarrow y_{2}
$$

então, para todo $x_{1}, x_{2}$ 

$$
x_{1}+x_{2}\rightarrow y_{1}+y_{2}
$$

(1.38) Além disso, um sistema linear deve satisfazer a propriedade de homogeneidade ou escalonamento, a qual afirma que para uma número real ou imaginário arbitrário k, se uma entrada aumentar k vezes, seu efeito também aumentará k vezes. Portanto, se 

$$
x\rightarrow y
$$

então para todo k real ou imaginário $$
kx\rightarrow ky
$$

(1.39) Logo, a linearidade implica duas propriedades: homogeneidade (escalonamento) e aditividade. As duas propriedades podem ser combinadas em uma única propriedade (superposição), a qual é descrita como mostrado a seguir. Se, 

$$
x_{1}\rightarrow y_{1}
$$

e

$$
x_{2}\rightarrow y_{2}
$$

então para todos os valores de constantes $k_{1}$ e $k_{2}$. 

$$
k_{1}x_{1}+k_{2}x_{2}\longrightarrow k_{1}y_{1}+k_{2}y_{2}
$$

(1.40) 
> **EXERCÍCIO E1.11**
> > Mostre que um sistema com entrada $x(t)$ e saída $y(t)$ relacionadas por $y(t)=Re[x(t)]$ satisfaz a propriedade de aditividade mas viola a propriedade de homogeneidade. Logo, tal sistema é não linear.

 [Dica: Mostre que a Eq. (1.39) não é satisfeita quando k é complexo.]

#### RESPOSTA DE UM SISTEMA LINEAR 

A saída de um sistema para $t\ge0$ é o resultado de duas causas independentes: a condição inicial do sistema (ou o estado do sistema) para $t=0$ e a entrada $x(t)$ para $t\ge0$. Se um sistema é linear, a saída deve ser a soma das suas componentes resultantes destas duas causas: primeiro, a componente de reposta a entrada nula que resulta somente das condições iniciais para $t=0$ com a entrada $x(t)=0$ para $t\ge0$ e, então, a componente de resposta a estado nulo que resulta apenas da entrada $x(t)$ para $t\ge0$ quando as condições iniciais (para $t=0$) são consideradas iguais a zero. Quando todas as condições iniciais apropriadas são nulas, o sistema é dito estar em estado nulo. Em resumo, a resposta de um sistema linear pode ser expressa como a soma das componentes de entrada nula e estado nulo: 

$$
\text{resposta total = resposta entrada nula + resposta estado nulo}
$$

(1.41) Essa propriedade de sistemas lineares, a qual permite a separação de uma saída em componentes resultantes das condições iniciais e da entrada, é chamada de propriedade de decomposição. Para o circuito RC da Fig. 1.26, a resposta $y(t)$ foi determinada como sendo [veja Eq. (1.36c)] 

$$
y(t)=\underbrace{v_{C}(0)}_{\text{componente entrada nula}}+\underbrace{Rx(t)+\frac{1}{C}\int_{0}^{t}x(\tau)d\tau}_{\text{componente estado nulo}}
$$

(1.42) A partir da Eq. 1.42, fica claro que se a entrada $x(t)=0$ para $t\ge0$, a saída será $y(t)=v_{c}(0)$. Logo $v_{c}(0)$ é a componente de entrada nula da resposta $y(t)$. Similarmente, se o estado do sistema (a tensão $v_{c}$ neste caso) for zero para $t=0$ a saída é dada pela segunda componente do lado direito da Eq. (1.42). Claramente, esta é a componente de estado nulo da resposta $y(t)$. > **EXEMPLO 1.9** > Mostre que o sistema descrito pela equação >
>
> $$
> \frac{dy}{dt}+3y(t)=x(t)
> $$
> 
> é linear. > Seja a resposta do sistema às entradas $x_{1}(t)$ e $x_{2}(t)$, $y_{1}(t)$ e $y_{2}(t)$ respectivamente. Então
>
> $$
> \frac{dy_{1}}{dt}+3y_{1}(t)=x_{1}(t)
> $$
> 
> e
> 
> $$
> \frac{dy_{2}}{dt}+3y_{2}(t)=x_{2}(t)
> $$
> 
> multiplicando a primeira equação por $k_{1}$, a segunda por $k_{2}$ e somando os resultados teremos >
> $$
> \frac{d}{dt}[k_{1}y_{1}(t)+k_{2}y_{2}(t)]+3[k_{1}y_{1}(t)+k_{2}y_{2}(t)]=k_{1}x_{1}(t)+k_{2}x_{2}(t)
> $$
> 
> (1.43) > mas essa é a equação do sistema [Eq. (1.43)] com >
> $$
> x(t)=k_{1}x_{1}(t)+k_{2}x_{2}(t)
> $$
> 
> e
> 
> $$
> y(t)=k_{1}y_{1}(t)+k_{2}y_{2}(t)
> $$
> 
> Portanto, quando a entrada é $k_{1}x_{1}(t)+k_{2}x_{2}(t)$, a resposta do sistema é $k_{1}y_{1}(t)+k_{2}y_{2}(t)$. Consequentemente, o sistema é linear. Usando esse argumento, podemos facilmente generalizar o resultado para mostrar que um sistema descrito por uma equação diferencial na forma
>
>$$
a_{0}\frac{d^{N}y}{dt^{N}}+a_{1}\frac{d^{N-1}y}{dt^{N-1}}+\cdot\cdot\cdot+a_{N}y(t)=b_{N-M}\frac{d^{M}x}{dt^{M}}+\cdot\cdot\cdot+b_{N-1}\frac{dx}{dt}+b_{N}x(t)
$$

(1.44) é um sistema linear. > **EXERCÍCIO E1.12** > Mostre que o sistema descrito pela seguinte equação é linear: >
>
> $$
> \frac{dy}{dt}+t^{2}y(t)=(2t+3)x(t)
> $$
> 

> **EXERCÍCIO E1.13** > Mostre que o sistema descrito pela seguinte equação não é linear: >
>
> $$
> y(t)\frac{dy}{dt}+3y(t)=x(t)
> $$
> 

#### MAIS COMENTÁRIOS SOBRE SISTEMAS LINEARES A propriedade de superposição (linearidade) simplifica em muito a análise de sistemas lineares. Devido à propriedade de decomposição, podemos calcular separadamente as duas componentes da saída. Além disso, se descrevermos a entrada $x(t)$ pela soma de funções mais simples, 

$$
x(t)=a_{1}x_{1}(t)+a_{2}x_{2}(t)+\cdot\cdot\cdot+a_{m}x_{m}(t)
$$

então, pela linearidade, a resposta $y(t)$ é dada por 

$$
y(t)=a_{1}y_{1}(t)+a_{2}y_{2}(t)+\cdot\cdot\cdot+a_{m}y_{m}(t)
$$

(1.45) Esta observação aparentemente trivial possui profundas implicações. Por exemplo, considere uma entrada arbitrária $x(t)$ tal como a mostrada na Fig. 1.27a. Podemos aproximar $x(t)$ pela soma de pulsos retangulares de largura $\Delta t$ e alturas variáveis. Portanto, se soubermos a resposta do sistema a um impulso unitário, podemos determinar imediatamente a resposta do sistema a uma entrada $x(t)$ arbitrária através da soma das respostas do sistema a cada componente impulso de $x(t)$. 

<img width="718" height="306" alt="image" src="https://github.com/user-attachments/assets/7f5b8ad5-7038-44ce-ae9f-4310469cdece" />


*[Figura 1.27 Representação de sinais em termos de componentes de impulso e degrau.]* 

### 1.7-2 Sistemas Invariantes e Variantes no Tempo 

Sistemas cujos parâmetros não são alterados com o tempo são invariantes no tempo (também chamados de sistemas com parâmetros constantes). Para tais sistemas, se a entrada for atrasada por T segundos, a saída é a mesma anterior, porém atrasada também por T segundos (assumindo que as condições iniciais também sejam atrasadas T segundos). Esta propriedade é mostrada graficamente na Fig. 1.28. 

<img width="724" height="534" alt="image" src="https://github.com/user-attachments/assets/f26a8dfd-3d5e-4963-b057-4747c9e25694" />


*[Figura 1.28 Propriedade de invariância no tempo.]* 

Também podemos ilustrar esta propriedade como apresentado na Fig. 1.29. Se o sistema for invariante no tempo, então a saída atrasada $y(t-T)$ pode ser obtida, também, atrasando primeiro a entrada $x(t)$ antes de aplicá-la ao sistema, como mostrado na Fig. 1.29b. Em outras palavras, o sistema S e o atraso de tempo são comutativos se o sistema for invariante no tempo. 

<img width="545" height="250" alt="image" src="https://github.com/user-attachments/assets/64841297-61a9-4579-acd9-412fc079d842" />

*[Figura 1.29 Ilustração da propriedade de invariância no tempo.]* 

Um sistema com uma relação de entrada/saída descrita por uma equação diferencial linear na forma dada no Exemplo 1.9 [Eq. (1.44)] é um sistema linear invariante no tempo (LIT) quando os coeficientes $a_i$ e $b_i$ são constantes. Se estes coeficientes forem funções do tempo, então o sistema é um sistema linear variante no tempo. 

> **EXERCÍCIO E1.14**
> Mostre que um sistema descrito pela seguinte equação é um sistema com parâmetros variantes no tempo: >
>
> $$
> y(t)=(sen~t)x(t-2)
> $$
> 
> [Dica: mostre que o sistema falha ao satisfazer a propriedade de invariância no tempo.]

### 1.7-3 Sistemas Instantâneos e Dinâmicos 

Em uma classe especial de sistemas, a saída a qualquer instante $t$ depende apenas da entrada naquele instante. Tais sistemas são chamados de sistemas instantâneos ou sem memória. Mais precisamente, um sistema é dito instantâneo (ou sem memória) se sua saída a qualquer instante $t$ depender, no máximo, da força de sua(s) entrada(s) no mesmo instante t e não de qualquer valor passado ou futuro da(s) entrada(s). Caso contrário, o sistema é chamado de dinâmico (ou sistema com memória).

### 1.7-4 Sistemas Causal e Não Causal 

Um sistema causal (também conhecido como físico ou não antecipativo) é aquele no qual a saída em qualquer instante $t_{0}$ depende apenas do valor da entrada $x(t)$ para $t\le t_{0}$. Em outras palavras, o valor da saída no instante presente depende apenas do valor presente e passado da entrada $x(t)$, e não de seus valores futuros. Para simplificar, em um sistema causal, a saída não pode começar antes da entrada ser aplicada. Um sistema que viola a condição de causalidade é chamado de sistema não causal (ou antecipativo). Qualquer sistema prático que opera no tempo real deve, necessariamente, ser causal. Por exemplo, considere o sistema especificado por
>
>$$
y(t)=x(t-2)+x(t+2)
$$

(1.46) Para a entrada $x(t)$ mostrada na Fig. 1.30a, a saída $y(t)$, calculada a partir da Eq. (1.46) (mostrada na Fig. 1.30b), começa antes mesmo da entrada ser aplicada. *[Figura 1.30 Um sistema não causal e sua realização por um sistema causal atrasado.]* #### POR QUE ESTUDAR SISTEMAS NÃO CAUSAIS? Eles são importantes no estudo de sistemas por diversas razões. 1.  Sistemas não causais são realizáveis quando a variável independente for outra que não o "tempo" (por exemplo, o espaço). 2.  Para o processamento de sinais, temos todos os dados de entrada gravados anteriormente. Um sistema não causal pode ser realizável, apesar de não ser em tempo real. Podemos, portanto, ser capazes de implementar um sistema não causal desde que estejamos dispostos a aceitar um atraso de tempo na saída. Considere um sistema cuja saída é a mesma que $y(t)$ da Eq. (1.46) atrasada por 2 segundos (Fig 1.30c), tal que 

$$
\hat{y}(t)=y(t-2) = x(t-4)+x(t)
$$
    
    Neste caso, a saída a qualquer instante $t$ não depende de valores futuros da entrada e o sistema é causal. 4.  Eles fornecem um limite superior para o desempenho de sistemas causais. > **EXERCÍCIO E1.15** > Mostre que um sistema descrito pela seguinte equação é não causal: >
>
> $$
> y(t)=\int_{t-S}^{t+S}x(\tau)d\tau
> $$
> 
> Mostre que esse sistema pode ser implementado fisicamente se aceitarmos um atraso de 5 segundos da saída.

### 1.7-5 Sistemas em Tempo Contínuo e em Tempo Discreto 

Sinais definidos ou especificados em uma faixa de valores contínua de tempo são sinais contínuos no tempo, representados pelos símbolos $x(t)$, $y(t)$ e assim por diante. sistemas cujas entradas e saídas são sinais contínuos no tempo são sistemas em tempo contínuo. Por outro lado, sinais definidos apenas em instantes discretos de tempo $t_{0},t_{1},t_{2},...t_{n},...$ são sinais discretos no tempo. 

Sistemas cujas entradas e saídas são sinais discretos no tempo são sistemas em tempo discreto. Por conveniência, iremos simplificar esta notação para $x[n], y[n],...$, onde fica entendido que $x[n]=x(nT)$ e que n é algum inteiro. 

*[Figura 1.31 Um sinal em tempo discreto.]* 


*[Figura 1.32 Processamento de sinais contínuos no tempo por sistemas discretos no tempo.]* 

### 1.7-6 Sistemas Analógicos e Digitais 

Um sistema cujos sinais de entrada e saída são analógicos é um sistema analógico. Um sistema cujos sinais de entrada e saída são digitais é um sistema digital. Um computador digital é um exemplo de um sistema digital (binário). 

### 1.7-7 Sistemas Inversíveis e Não Inversíveis Se pudermos obter a entrada $x(t)$ da saída $y(t)$ correspondente através de alguma operação, o sistema S é dito ser inversível. Para um sistema inversível, é essencial que toda entrada possua uma única saída, de tal forma que exista um mapeamento de um-para-um entre a entrada e a saída correspondente. O sistema que efetua a operação inversa é o sistema inverso de S. 

*[Figura 1.33 O cascateamento de um sistema com sua inversa resulta em um sistema identidade.]* 


### 1.7-8 Sistemas Estáveis e Instáveis Se cada entrada limitada aplicada ao terminal de entrada resultar em uma saída limitada, o sistema é dito ser externamente estável. Este tipo de estabilidade também é conhecida como estabilidade no sentido BIBO (bounded-input/bounded-output). 
> **EXERCÍCIO E1.16**
> > Mostre que o sistema descrito pela equação $y(t)=x^{2}(t)$ é não inversível com estabilidade no sentido BIBO.

## 1.8 MODELO DE SISTEMA: DESCRIÇÃO ENTRADA-SAÍDA 

A descrição de um sistema em termos de medidas nos terminais de entrada e saída é chamada de descrição entrada-saída. O primeiro passo na análise de um sistema é a construção do modelo do sistema, o qual é a expressão matemática ou regra que aproxima satisfatoriamente o comportamento dinâmico do sistema. 


### 1.8-1 Sistemas Elétricos Para construir um modelo de sistema, devemos estudar as relações entre as diferentes variáveis do sistema. Em sistemas elétricos, por exemplo, devemos determinar um modelo satisfatório para a relação tensão-corrente de cada elemento e as leis de interconexão (Leis de Kirchhoff). 
> **EXEMPLO 1.10**
> > Para o circuito RLC série da Fig. 1.34, determine a equação de entrada-saída que relaciona a tensão de entrada $x(t)$ com a corrente de saída (corrente de malha) $y(t)$.
> 
> *[Figura 1.34]* > 
> Aplicando a lei de Kirchhoff das tensões para a malha teremos, >
>
> $$
> v_{L}(t)+v_{R}(t)+v_{C}(t)=x(t)
> $$
> 
> Utilizando as leis de tensão-corrente de cada elemento, podemos escrever esta equação como >
> $$
> \frac{dy}{dt}+3y(t)+2\int_{-\infty}^{t}y(\tau)d\tau=x(t)
> $$
> 
> Diferenciando os dois lados desta equação, obtemos >
> $$
> \frac{d^{2}y}{dt^{2}}+3\frac{dy}{dt}+2y(t)=\frac{dx}{dt}
> $$
> 
> É conveniente utilizarmos a notação compacta D para o operador diferencial $d/dt$, logo, >
>
> $$
> \frac{dy}{dt}\equiv Dy(t), \quad \frac{d^{2}y}{dt^{2}}\equiv D^{2}y(t)
> $$
> 
> Com esta notação a Eq. (1.49) pode ser escrita por >
>
> $$
> (D^{2}+3D+2)y(t)=Dx(t)
> $$

> **EXEMPLO 1.11** > Determine a equação relacionando a entrada e a saída para o circuito RC série da Fig. 1.35 se a entrada for a tensão $x(t)$ e a saída for (a) a corrente de malha $i(t)$ (b) a tensão do capacitor $y(t)$. > 
> *[Figura 1.35]*
> 
> (a) A equação de malha para o circuito é >
>
> $$
> R~i(t)+\frac{1}{C}\int_{-\infty}^{t}i(\tau)d\tau=x(t) \quad \Rightarrow \quad 15~i(t)+5\int_{-\infty}^{t}i(\tau)d\tau=x(t)
> $$
> 
> (b) ...Substituindo a relação $i(t)=C\frac{dy}{dt} = \frac{1}{5}Dy(t)$ na equação diferencial da malha resulta em >
>
> $$
> (3D+1)y(t)=x(t)
> $$
> 
> ou
>
> $$
> 3\frac{dy}{dt}+y(t)=x(t)
> $$

> **EXERCÍCIO E1.17** > Para o circuito RLC da Fig. 1.34, determine a relação de entrada-saída se a saída for a tensão $v_{L}(t)$ do indutor. > **RESPOSTA:** $(D^{2}+3D+2)v_{L}(t)=D^{2}x(t)$ > **EXERCÍCIO E1.18** > Para o circuito RLC da Fig. 1.34, determine a relação de entrada-saída se a saída for a tensão $v_{c}(t)$ do capacitor. > **RESPOSTA:** $(D^{2}+3D+2)v_{C}(t)=2x(t)$ ### 1.8-2 Sistemas Mecânicos #### SISTEMAS TRANSLACIONAIS Os elementos básicos são massas ideais, molas lineares e amortecedores. * **Massa M:** $x(t)=M\ddot{y}(t)=M\frac{d^{2}y}{dt^{2}}=MD^{2}y(t)$ * **Mola Linear K:** $x(t)=Ky(t)$ * **Amortecedor Linear B:** $x(t)=B\dot{y}(t)=B\frac{dy}{dt}=BDy(t)$ *[Figura 1.36 Alguns elementos em sistemas mecânicos translacionais.]* > **EXEMPLO 1.12** > Determine a relação entrada-saída para o sistema mecânico translacional mostrado na Fig. 1.37a. A entrada é a força $x(t)$ e a saída é a posição da massa $y(t)$. > 
> *[Figura 1.37]* > 
> Usando a segunda lei de Newton, a força total deve ser $M\ddot{y}(t)$. Logo, >
>
> $$
> M\ddot{y}(t)=-B\dot{y}(t)-Ky(t)+x(t)
> $$
> 
> ou >
>
> $$
> (MD^{2}+BD+K)y(t)=x(t)
> $$

#### SISTEMAS ROTACIONAIS As variáveis são torque, posição angular ($\theta$), etc. * **Momento de Inércia J:** $torque=J\ddot{\theta}=J\frac{d^{2}\theta}{dt^{2}}=JD^{2}\theta(t)$ * **Mola de Torção K:** $torque=K\theta$ * **Amortecedor de Torção B:** $torque=B\dot{\theta}(t)=BD\theta(t)$ ### 1.8-3 Sistemas Eletromecânicos Consideraremos um exemplo de um motor CC controlado pela armadura. O torque $\mathcal{T}(t)$ gerado pelo motor é proporcional a corrente de armadura $x(t)$. Portanto, 

$$
\mathcal{T}(t)=K_{T}x(t)
$$

Se J é o momento de inércia da carga e B o coeficiente de amortecimento, então 

$$
J\ddot{\theta}(t)=\mathcal{T}(t)-B\dot{\theta}(t)
$$

Logo, 

$$
(JD^{2}+BD)\theta(t)=\mathcal{T}(t) = K_{T}x(t)
$$

ou 

$$
J\frac{d^{2}\theta}{dt^{2}}+B\frac{d\theta}{dt}=K_{T}x(t)
$$

## 1.9 DESCRIÇÃO INTERNA E EXTERNA DE UM SISTEMA A relação de entrada-saída de um sistema é uma descrição externa do sistema. Uma descrição interna é capaz de fornecer a informação completa sobre todos os possíveis sinais do sistema. Uma descrição externa pode não fornecer uma informação completa como esta. Considere o circuito da Fig. 1.41a. Para a descrição externa, nenhuma medição ou observação externa pode detectar a presença do capacitor. Se o circuito estiver encapsulado, é impossível determinar as correntes ou tensões internas a partir de medições externas. *[Figura 1.41 Um sistema que não pode ser descrito por medidas externas.]* Isso ocorre quando o sistema é não controlável ou não observável. Na Fig. 1.42a, parte do sistema (subsistema $S_{2}$) não pode ser controlada pela entrada $x(t)$. Na Fig. 1.42b, algumas das saídas do sistema (aquelas no subsistema $S_{2}$) não podem ser observadas a partir dos terminais de saída. *[Figura 1.42 Estruturas de sistemas não controláveis e não observáveis.]* ## 1.10 DESCRIÇÃO INTERNA: DESCRIÇÃO EM ESPAÇO DE ESTADO Nesta abordagem, identificamos certas variáveis chave, chamadas de variáveis de estado. Em um circuito RLC passivo, as tensões independentes dos capacitores e as correntes dos indutores são as variáveis de estado. O conhecimento das variáveis de estado permite que toda possível saída do sistema seja calculada. > **EXEMPLO 1.14** > Considere o circuito da Fig. 1.43 com $q_{1}$ e $q_{2}$ como variáveis de estado e escreva as equações de estado. > 
> *[Figura 1.43 Escolhendo condições iniciais adequadas em um circuito.]* > 
> Como $\dot{q}_{1}$ é a corrente através do capacitor, >
>
> $$
> \dot{q}_{1}=i_{c}=i_{1}-i_{2}-q_{2} = (x-q_{1})-0,5q_{1}-q_{2} = -1.5q_{1}-q_{2}+x
> $$
> 
> Além disso, $2\dot{q}_{2}$, a tensão do indutor, é dada por >
>
> $$
> 2\dot{q}_{2}=q_{1}-v_{3} = q_{1}-5q_{2} \quad \Rightarrow \quad \dot{q}_{2}=0.5q_{1}-2.5q_{2}
> $$
> 
> Portanto, as equações de estado são >
>
> $$
> \dot{q}_{1}=-1.5q_{1}-q_{2}+x
> $$
> 
> $$
> \dot{q}_{2}=0,5q_{1}-2.5q_{2}
> $$

> **EXEMPLO 1.15** > Neste exemplo, investigaremos a natureza das equações de estado e a questão de controlabilidade e observabilidade para o circuito da Fig. 1.41a. Existe apenas uma variável de estado, a tensão do capacitor $q(t)$. > ... a equação da malha acba é >
>
> $$
> q=2[-\frac{x}{10}-\frac{\dot{q}}{2}]+2[\frac{x}{10}-\frac{\dot{q}}{2}]=-2\dot{q}
> $$
> 
> ou >
>
> $$
> \dot{q}=-0.5q
> $$
> 
> Esta é a equação de estado desejada. A saída $y(t)$ é dada por >
>
> $$
> y(t)=2[\frac{x}{10}-\frac{\dot{q}}{2}]+2[\frac{x}{10}+\frac{\dot{q}}{2}] = \frac{2}{5}x(t)
> $$
> 
> A equação de estado mostra que o estado $q(t)$ é independente da entrada $x(t)$, portanto, o estado do sistema q não pode ser controlado pela entrada. Além disso, a equação de saída mostra que a saída $y(t)$ não depende do estado $q(t)$. Logo, o estado do sistema não pode ser observado a partir dos terminais de saída. Desta forma, o sistema não é nem controlável e nem observável. Técnicas de espaço de estado são úteis por várias razões, incluindo: 1.  Grande generalidade (sistemas não lineares, variantes no tempo, MIMO). 2.  Uso de notação matricial e álgebra linear. 3.  Fácil simulação em computadores digitais. 4.  Para sistemas de segunda ordem, um método gráfico (análise no plano de fase) pode ser utilizado. > **EXERCÍCIO Ε1.20** > Escreva as equações de estado para o circuito RLC série mostrado na Fig. 1.45 utilizando a corrente do indutor $q_{1}(t)$ e a tensão do capacitor $q_{2}(t)$ como variáveis de estado. > 
> *[Figura 1.45]* > 
> **RESPOSTA** >
>
> $$
> \dot{q}_{1}=-3q_{1}-q_{2}+x
> $$
> 
> $$
> \dot{q}_{2}=2q_{1}
> $$

## 1.11 RESUMO Um sinal é um conjunto de dados ou informação. Um sistema processa um sinal de entrada para produzir sinais de saída. Um sistema pode ser implementado em hardware ou software. Uma medida do tamanho de um sinal é sua energia ou potência. Sinais podem ser classificados de diversas formas: 1.  **Contínuo no tempo** vs. **Discreto no tempo**: qualifica a natureza do sinal ao longo do eixo do tempo. 2.  **Analógico** vs. **Digital**: qualifica a natureza da amplitude do sinal. 3.  **Periódico** vs. **Não periódico**: um sinal periódico $x(t)$ satisfaz $x(t)=x(t+T_{0})$ e existe em todo o intervalo de tempo de $-\infty<t<\infty$. Um sinal causal é zero para $t<0$. 4.  **Sinal de energia** vs. **Sinal de potência**: um sinal pode ser um ou outro, mas não os dois. Existem também sinais que não são nem de energia nem de potência. 
