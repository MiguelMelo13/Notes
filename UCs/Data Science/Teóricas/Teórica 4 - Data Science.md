### #EDA Exploratory Data Analysis

Processo iterativo que permite compreender os dados e extrair insights significativos. As ferramentas de visualização e estatísticas descritivas são essenciais nesta fase.

##### EDA's Pipeline

1. Compreensão do problema - Definir os objetivos e questões de pesquisa
2. Recolha de dados
3. Pré-processamento de dados - Limpeza e tratamento de valores ausentes
4. Análise Univariada - Focada em entender as propriedades básicas de uma única variável
5. Análise Bi/Multivariada - Examinar relações entre duas ou mais variáveis
6. Visualização de dados
7. Interpretação de resultados

###### Amostra

Subconjunto de dados extraído de uma população usado para inferir características dessa população. Tamanho representado por *N*.

###### Distribuição

Descreve como os valores de uma variável estão espalhados entre os valores que podem ter.
A sua visualizção ajuda a identificar tendência central, dispersão, enviesamento e outliers numa variável.

---
### #Histograma

Gráfico de barras em que é representada a distribuição de valores. Podemos identificar a curva normal e a moda facilmente.

1. Dividir o intervalo de valores em bins de tamanho igual
2. Contar o número de observações em cada bin
3. Plotar os bins no eixo horizontal e as frequências no eixo vertical

---

### #BoxPlot

Resume a distribuição com base em quartis e destaca possíveis outliers.

1. Ordenar os dados de forma crescente
2. Calcular o primeiro quartil (Q1, 25%), mediana (Q2, 50%) e o terceiro quartil (Q3, 75%)
3. Determinar os *whiskers* e identificar outliers.
	1. $1.5 * IQR$ 
	2. Determinar o intervalo que via de $Q3$ a $Q3 + 1.5 * IQR$
	3. $Q1$ a $Q1 -1.5*IQR$


---

### Medidas de Dispersão

###### #Amplitude

Indica a extensão total dos dados. Influenciada por outliers.

$$Amplitude = x_{max} - x_{min}$$
###### #Variância

Mede a dispersão dos dados em relação à média; valores maiores indicam maior variabilidade.

$$
\sigma^2 = \frac{\sum_{i=1}^{N} (x_i - \bar{x})^2}{N}
$$
###### #DesvioPadrão

 Indica o desvio médio em relação à média. Mesma unidade dos dados originais.
 $$
 \sigma = \sqrt{ \sigma^2 }
 $$

###### #IntervaloInterQuartil

Menos influenciado por outliers. Representa a dispersão dos 50% centrais dos dados.

$$
IQR = Q_{3} - Q_{1}
$$

###### #Assimetria Skewness

Medida estatística que descreve a simetria ou falta dela de uma distribuição em torno da sua média. Indica se os dados estão ditribuídos de forma equilibrada ou se tendem a se concentrar mais numa das caudas da distribuição.

$$
\text{Assimetria} = \frac{\sum_{i=1}^{N} (x_i - \bar{x})^3}{(N - 1) \sigma^3}
$$

Onde:

- *N* é o tamanho da amostra
- $x_{i}$ são os valores individuais da amostra
- $\bar{x}$ é a média da amostra
- $\sigma$ é o desvio padrão da amostra

A assimetria avalia a simetria da distribuição, sendo:
- Positiva quando a cauda direita da distribuição é mais lounga ou pesada.
- Negativa quando a cauda esquerda é mais longa ou pesada
- Zero quando a distribuição é perfeitamente simétrica em torno da média.
Ajuda a identificar se os dados estão mais concentrados à esquerda ou à direita da média, oferecendo uma visão sobre a forma da distribuição.

---

### #Outliers

Estudo estatistico de eventos raros → Estudo de outliers

Definition of outliers. An outlier is **an observation that lies an abnormal distance from other values in a random sample from a population**. Este valor “estraga” os cálculos de média tornando os valores calculados pouco fiáveis e pouco representativos da realidade.

Classificação de outliers através de métodos estatísticos que podem ser discutidos. (A ser falado na Teorica 4 ou Teorica 5)

---

### #MissingValues

Inputation missing value através de fórmulas matemáticas para preencher campos em branco através de comparação com entidades que se assemelham à que tem o campo vazio ou de valor errado.

---

### #Scatterplot

Após serem produzidas as variáveis dependente e independente, os pontos são representados num gráfico. Podem ser tiradas duas conclusões, uma relação de linearidade entre os dados (y=mx+b) ou, no caso de os dados estarem dispersos, não é possível identificar uma relação entre as variáveis.

A distância dos data points à função extraída representam o valor de erro do modelo, chama-se residual.

---

### Aprendizagem estatística

VER PDF ANEXADO