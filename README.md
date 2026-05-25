# Semana 06 - Polarização de Transistor

## Objetivos da Aula

* Compreender o funcionamento da polarização do transistor BJT em configuração emissor comum;
* Analisar como o ponto Q influencia a estabilidade e a linearidade de um amplificador de áudio;
* Interpretar cálculos elétricos e medições práticas em circuito real.

## Impactos no Projeto do Amplificador de Áudio

* Vamos além da visão **transistor como chave**
* entrar em **transistor como amplificador linear**
* mostrar que a polarização define:
  * distorção,
  * clipping,
  * estabilidade térmica,
  * excursão do sinal,
  * qualidade do áudio.
* Entender a aplicação dos componentes:
  * RC;
  * RE;
  * divisor R1/R2;
  * capacitores de acoplamento;
* Vamos nos preparar para medir tensões reais do circuito;
* Vamos na próxima aula poder comparar teoria × prática;
* Vamos nos preparar para identificar saturação, corte e região ativa;


# 1. Ponto de Partida - Os Autoestudos

### Por que alguns amplificadores distorcem mesmo sem aumentar muito o volume?

<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>

Pontos-chave que explicam isso:

* um áudio clipado --> transistores não estão no seu ponto intermediário entre corte e saturado. Esse ponto chama-se Q;
* um transistor funcionando como chave --> pode haver resistências e resistores mal dimencionados conectados aos transistores alterando o ponto Q;
* um transistor funcionando linearmente --> é o nosso alvo


## O transistor está apenas ligando e desligando ou existe uma região intermediária?

<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>

* corte;
* saturação;
* região ativa --> onde mora o ponto Q

## Como o circuito decide em qual ponto o transistor vai "descansar" antes do áudio chegar?

<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>

* transistor central;
* divisor de tensão;
* resistor de emissor;
* resistor de coletor;
* capacitores.


## Então, qual é a definição do ponto Q?

<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>

# 2. Construção Conceitual

## Parte 1 — O transistor como amplificador

Se o transistor estiver:

* em corte → áudio “morre”
* em saturação → áudio “amassa”
* no meio → amplifica linearmente

Portanto, podemos concluir que:

* áudio é uma pequena variação AC;
* polarização cria o “offset DC”.

Analogia: o ponto Q é como posicionar o elevador no meio do prédio para ele subir e descer igualmente rápido.


## Parte 2 — Polarização fixa vs divisor de tensão

* polarização fixa;
* sensibilidade ao β;
* temperatura.
* COLOCAR FIGURA NO QUADRO

#### Conclusão: o divisor de tensão nasce para tornar o ponto Q menos dependente do β.


## Parte 3 — Método aproximado

Ver a equação 4.33 do PDF [AQUI](https://drive.google.com/file/d/1_7p3mcqvUH_jVqHbjrk3s6PnXa21Ybk-/view?usp=sharing)

* se essa condição é satisfeita,
* IB fica desprezível,
* o divisor “manda” na tensão da base.

Isso é MUITO importante para o projeto real.

# 4. Parte Matemática Aplicada ao Amplificador

Tabela resumida:

| Grandeza | Significado físico            |
| -------- | ----------------------------- |
| VB       | tensão que “posiciona” a base |
| VE       | referência do emissor         |
| VCE      | espaço para o sinal oscilar   |
| IC       | corrente de repouso           |
| Ponto Q  | condição sem áudio            |


## Equações principais

### Tensão da base
### Tensão do emissor
### Corrente de emissor
### Tensão coletor-emissor

[AQUI](https://drive.google.com/file/d/1_7p3mcqvUH_jVqHbjrk3s6PnXa21Ybk-/view?usp=sharing)

# 6. Fechamento Conceitual

| Situação          | Consequência no áudio |
| ----------------- | --------------------- |
| ponto Q central   | áudio limpo           |
| corte             | meia onda perdida     |
| saturação         | topo achatado         |
| β varia           | circuito instável, não confiável     |
| divisor de tensão | estabilidade          |


# Roteiro Prático — Polarização de Transistor BJT em Emissor Comum

## Lista de materiais

* Calculadora;
* Folha para cálculos;
* Simulador Tinkercad;
* Transistor BC548 ou equivalente;
* Resistores:

  * R1 = 39 kΩ
  * R2 = 3,9 kΩ
  * RC = 10 kΩ
  * RE = 1,5 kΩ
* Capacitores:

  * C1 = 10 µF
  * C2 = 10 µF
* Fonte DC de 22 V;
* Gerador de sinais senoidais;
* Osciloscópio virtual.

## Circuito da atividade

Monte o circuito da **Figura 4.35** no Tinkercad:

* Polarização por divisor de tensão;
* Emissor comum;
* Entrada AC via capacitor de acoplamento;
* Saída AC retirada do coletor via capacitor de desacoplamento.

Parâmetros do transistor:

* β = 100
* VBE = 0,7 V

Valores:

* VCC = 22 V
* R1 = 39 kΩ
* R2 = 3,9 kΩ
* RC = 10 kΩ
* RE = 1,5 kΩ

# ETAPA 1 — Observação inicial do circuito

Antes de iniciar os cálculos, observe o circuito montado e responda:

## 1.1) Qual é a função de:

* R1?
* R2?
* RC?
* RE?
* C1?
* C2?

## 1.2) O sinal de áudio entra em qual terminal do transistor?

## 1.3) O sinal amplificado sai de qual terminal?

## 1.4) O transistor deste circuito trabalha:

* como chave?
* ou como amplificador linear?

Justifique.


# ETAPA 2 — Cálculo da tensão de base (método aproximado)



## 2.1) Utilize a equação 4.32 do divisor de tensão e calcule VB

## 2.2) O valor encontrado está:

* próximo de 0 V?
* próximo de VCC?
* ou intermediário?

Explique.

# ETAPA 3 — Cálculo da tensão no emissor

## 3.1) Utilize a equação 4.34, considere VBE = 0,7 V e calcule: VE

## 3.2) Explique: por que a tensão do emissor é menor que a tensão da base?

# ETAPA 4 — Corrente do emissor e coletor

## 4.1) Utilize a equação 4.35 e calcule IE

## 4.2) Considerando IC aproximadamente igual a IE, calcule ICQ

# ETAPA 5 — Tensão coletor-emissor

## 5.1) Utilize a equação 4.37 e calcule VCE

## 5.2) O transistor está:

* em corte?
* em saturação?
* ou na região ativa?

Justifique utilizando o valor de VCE.

## 5.3) O circuito possui espaço para amplificar sinais AC positivos e negativos? Explique.

# ETAPA 6 — Verificação da condição de estabilidade

## 6.1) Utilize a condição 4.33 e verifique matematicamente se o circuito atende essa condição.

## 6.2) Explique se o ponto Q deste circuito tende a ser:

* estável?
* ou muito dependente de β?

# ETAPA 7 — Simulação no Tinkercad. Monte o circuito 4.35 no Tinkercad.

## 7.1) Meça:

* VB
* VE
* VC
* VCE

## 7.2) Compare:

* valores teóricos;
* valores simulados.

## 7.3) Calcule o erro percentual entre:

* teoria;
* simulação.

# ETAPA 8 — Inserção do sinal AC. Configure:

* senoide;
* 1 kHz;
* 100 mVpp.

## 8.1) Observe usando o osciloscópio

* entrada;
* saída.

## 8.2) O sinal de saída está:

* invertido?
* não invertido?

## 8.3) O sinal de saída possui maior amplitude?

## 8.4) Explique:
Por que o capacitor de entrada impede que a fonte AC altere a polarização DC do transistor?

# ETAPA 9 — Alterando o ponto Q

## 9.1) Altere R2 de 3,9 kΩ para 22 kΩ.

## 9.2) Recalcule:

* VB
* VE
* IC
* VCE

## 9.3) O ponto Q mudou? Como?

## 9.3) A forma de onda piorou? Explique

# ETAPA 10 — Investigação da saturação [PRO LAR, FAZER EM CASA]

Agora altere: RC para 1 kΩ.

## 10.1) Calcule ICsat utilizando 4.38

## 10.2) O transistor ficou mais próximo:

* da saturação?
* ou da região ativa?

## 10.3) Observe o sinal no osciloscópio. Existe clipping?

# Conclusão da atividade

## 1) Qual é a principal função da polarização em um amplificador BJT?

## 2) O que acontece quando o ponto Q é mal ajustado?

## 3) Por que o resistor de emissor melhora a estabilidade do circuito?

## 4) Por que a polarização por divisor de tensão é mais estável que a polarização fixa?

## 5) Qual foi a principal relação observada entre:

* cálculos teóricos;
* simulação;
* comportamento do sinal AC?

