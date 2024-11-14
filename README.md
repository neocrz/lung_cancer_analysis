# lung_cancer_analysis
O objetivo principal desse projeto é analisar os fatores e característiccas que possam estar associados ao risco de desenvolver câncer de pulmão.

Iremos realizar várias análises exploratórias e modelagens preditivas para entender melhor os dados e identificar padrões ou correlações.

## Dados de origem
Os dados de origem do projetos foram obtidos do dataset disponível publicamente pelo Kaggle em: https://www.kaggle.com/datasets/akashnath29/lung-cancer-dataset seguindo a licença Open Database License (ODbL) v1.0.

Os dados resultantes deste projeto são disponibilizados de acordo com a licença ODbL v1.0.

## Planejamento
### Análise Exploratória de Dados
Iremos realizar uma análise exploratória para entender as características e a distribuição dos dados.

#### Distribuição das Variáveis
- Distribuição da variável dependente `LUNG_CANCER`
    - Qual a proporção de pessoas com e sem câncer de pulmão (0 vs 1)?
    - Verificar se a classe está balanceada ou desbalanceada (ex: 70% sem câncer, 30% com câncer).
- Distribuição das variáveis independentes
    - Como as variáveis como `AGE`, `SMOKING`, `PEER_PRESSURE`, entre outras, estão distribuídas nas duas classes de `LUNG_CANCER`?
    - Existem outliers nas variável numérica `AGE`?
- Proporção de valores binários
    - Verificar a distribuição de 0 e 1 nas variáveis binárias, como `SMOKING`, `YELLOW_FINGERS`, `ANXIETY`, etc.

#### Correlação entre Variáveis
- Correlação entre as variáveis independentes
    - Usar uma matriz de correlação para verificar se há alguma correlação forte entre as variáveis independentes, como AGE e SMOKING, ou SMOKING e YELLOW_FINGERS.
- Correlação entre variáveis e a variável dependente LUNG_CANCER
    - Calcular a correlação de Pearson (para variáveis numéricas) ou a tabela de contingência (para variáveis binárias) com a variável dependente LUNG_CANCER.

#### Análise Univariada e Bivariada
- Análise Univariada
    - Explorar cada variável de forma isolada, como histograma para AGE ou gráfico de barras para variáveis binárias como SMOKING e YELLOW_FINGERS.
- Análise Bivariada
    - Explorar como as variáveis independentes afetam LUNG_CANCER.
    - Boxplot ou violino para comparar a distribuição de AGE entre pessoas com e sem câncer.
    - Gráficos de barras para variáveis binárias, como SMOKING e YELLOW_FINGERS, separando os grupos por LUNG_CANCER.

### Análise de Associação / Causalidade
#### Associação entre Fatores de Risco e Câncer de Pulmão
- Tabulação Cruzada
    - Tabular as variáveis binárias como SMOKING, YELLOW_FINGERS, ANXIETY contra LUNG_CANCER para verificar a associação entre esses fatores e a ocorrência de câncer.
    - Exemplo: observar se a taxa de câncer é significativamente maior entre os fumantes (SMOKING = 1) em comparação com os não fumantes (SMOKING = 0).
- Teste qui-quadrado (Chi-Square Test)
    - Realizar testes qui-quadrado para determinar se há uma associação estatística significativa entre variáveis categóricas (ex: SMOKING e LUNG_CANCER).
- Análise de Variância (ANOVA)
    - Análise de variância para verificar se a média de idade (AGE) difere significativamente entre as pessoas com e sem câncer.

### Modelagem Preditiva
Iremos construir modelos preditivos para prever a probabilidade de um indivíduo desenvolver câncer de pulmão.
#### Modelos de Regressão Logística
Como LUNG_CANCER é uma variável binária (0 ou 1), a regressão logística é uma boa escolha para modelar a probabilidade de alguém ter câncer de pulmão com base nas variáveis independentes.

A regressão logística pode ajudar a entender a importância relativa de cada variável explicativa (por exemplo, SMOKING, AGE, etc.) na previsão de LUNG_CANCER.

#### Árvores de Decisão
Utilizaremos árvores de decisão para prever LUNG_CANCER com base nas características do paciente.

As árvores de decisão oferecem uma boa interpretação visual de como as variáveis influenciam a classificação de câncer de pulmão.

#### Random Forests e Gradient Boosting
Utilizaremos métodos como Random Forest ou Gradient Boosting para melhorar a precisão da previsão e lidar com possíveis interações não lineares entre as variáveis.

Esses modelos também fornecem a importância relativa das variáveis, ajudando a identificar quais fatores mais contribuem para a probabilidade de câncer de pulmão.

#### SVM (Máquinas de Vetores de Suporte)
Utilizaremos SVM para classificar pacientes com ou sem câncer de pulmão, especialmente se houver uma separação não linear entre as classes.

#### Validação Cruzada
Utilizaremos validação cruzada para avaliar a performance do modelo (precisão, recall, F1-score, AUC-ROC, etc.), especialmente porque a classe de LUNG_CANCER pode ser desbalanceada (muitos mais pacientes sem câncer do que com câncer).

### Análise de Impacto de Fatores de Risco
Realizaremos uma análise profunda para investigar como fatores de risco interagem com o câncer de pulmão:
- **Fumo**: O tabagismo é conhecido como um dos maiores fatores de risco para câncer de pulmão. Um modelo preditivo pode mostrar qual o impacto do fumo sobre a probabilidade de um diagnóstico de câncer de pulmão
- **Idade**: A idade pode ser um fator significativo, investigar se a probabilidade de câncer de pulmão aumenta com a idade será uma análise importante.
- Variáveis como PEER_PRESSURE (pressão social), ALLERGY, CHRONIC_DISEASE, etc., podem ter efeitos moderadores ou interações com o risco de desenvolver câncer de pulmão. Isso será investigado através de modelos estatísticos ou de aprendizado de máquina.

### Testes de Significância e Análise Estatística
Realizaremos testes estatísticos para identificar se as diferenças observadas entre os grupos (pessoas com e sem câncer de pulmão) são estatisticamente significativas.

Testes como t-test, ANOVA, e qui-quadrado serão utilizados para verificar a relação entre as variáveis independentes e a variável dependente.

## Teste de Hipótese
### Fumo e Câncer de Pulmão
#### Hipótese 
O fumo é significativamente mais comum em pessoas com câncer de pulmão do que em pessoas sem câncer de pulmão.

- **Hipótese nula (H₀)**: A proporção de fumantes (SMOKING = 1) entre as pessoas com câncer de pulmão é igual à proporção de fumantes entre as pessoas sem câncer de pulmão.
- **Hipótese alternativa (H₁)**: A proporção de fumantes entre as pessoas com câncer de pulmão é maior do que a proporção de fumantes entre as pessoas sem câncer de pulmão.

#### Teste
**Teste qui-quadrado de independência** ou **Teste de proporções**

Para realizar o teste qui-quadrado, podemos tabular as variáveis **`SMOKING`** e **`LUNG_CANCER`** para ver se há uma associação significativa entre ser fumante e ter câncer de pulmão.

### Idade e Câncer de Pulmão
#### Hipótese
A idade média das pessoas com câncer de pulmão é maior do que a idade média das pessoas sem câncer de pulmão.

- **Hipótese nula (H₀)**: A média de idade (`AGE`) para as pessoas com câncer de pulmão é igual à média de idade para as pessoas sem câncer de pulmão.
- **Hipótese alternativa (H₁)**: A média de idade para as pessoas com câncer de pulmão é maior do que a média de idade para as pessoas sem câncer de pulmão.

#### Teste
**Teste t de Student para duas amostras independentes** (caso os dados sigam uma distribuição aproximadamente normal) ou **Teste de Mann-Whitney U** (se os dados não forem normalmente distribuídos).

### Pressão dos Amigos e Câncer de Pulmão
#### Hipótese
A pressão social (`PEER_PRESSURE`) está associada ao aumento do risco de câncer de pulmão, ou seja, pessoas com câncer de pulmão são mais propensas a relatar pressão dos amigos.

- **Hipótese nula (H₀)**: A proporção de pessoas que reportam pressão dos amigos (PEER_PRESSURE = 1) é a mesma entre as pessoas com câncer de pulmão e as pessoas sem câncer de pulmão.
- **Hipótese alternativa (H₁)**: A proporção de pessoas que reportam pressão dos amigos é maior entre as pessoas com câncer de pulmão do que entre as pessoas sem câncer de pulmão.

#### Teste
**Teste qui-quadrado de independência**.

### Câncer de Pulmão e Doenças Crônicas
#### Hipótese
Pessoas com doenças crônicas têm maior risco de desenvolver câncer de pulmão.

- **Hipótese nula (H₀)**: A proporção de pessoas com doenças crônicas (`CHRONIC_DISEASE = 1`) é a mesma entre as pessoas com câncer de pulmão e as pessoas sem câncer de pulmão.
- **Hipótese alternativa (H₁)**: A proporção de pessoas com doenças crônicas é maior entre as pessoas com câncer de pulmão.

#### Teste
**Teste qui-quadrado de independência** ou **Teste de proporções**.

### Câncer de Pulmão e Sintomas Respiratórios (Chiado, Tosse, Dificuldade para Engolir)
#### Hipótese
Sintomas respiratórios, como tosse frequente (`COUGHING`), chiado no peito (`WHEEZING`) e dificuldade para engolir (`SWALLOWING_DIFFICULTY`), estão associados ao câncer de pulmão.

- **Hipótese nula (H₀)**: A proporção de pessoas com tosse frequente, chiado no peito ou dificuldade para engolir é a mesma entre as pessoas com câncer de pulmão e as pessoas sem câncer de pulmão.
- **Hipótese alternativa (H₁)**: A proporção de pessoas com tosse, chiado no peito ou dificuldade para engolir é maior entre as pessoas com câncer de pulmão do que entre as pessoas sem câncer.

#### Teste
**Teste qui-quadrado de independência**.

### Consumo de Álcool e Câncer de Pulmão
#### Hipótese
O consumo de álcool (`ALCOHOL_CONSUMING`) está associado ao aumento do risco de câncer de pulmão.

- **Hipótese nula (H₀)**: A proporção de pessoas que consomem álcool (ALCOHOL_CONSUMING = 1) é a mesma entre as pessoas com câncer de pulmão e as pessoas sem câncer de pulmão.
- **Hipótese alternativa (H₁)**: A proporção de pessoas que consomem álcool é maior entre as pessoas com câncer de pulmão do que entre as pessoas sem câncer.

#### Teste
**Teste qui-quadrado de independência** ou **Teste de proporções**.

### Câncer de Pulmão e Fadiga (Fatigue)
#### Hipótese
Pessoas com câncer de pulmão são mais propensas a relatar cansaço constante (`FATIGUE`).

- **Hipótese nula (H₀)**: A proporção de pessoas que relatam fadiga (FATIGUE = 1) é a mesma entre as pessoas com câncer de pulmão e as pessoas sem câncer de pulmão.
- **Hipótese alternativa (H₁)**: A proporção de pessoas que relatam fadiga é maior entre as pessoas com câncer de pulmão do que entre as pessoas sem câncer.

#### Teste
**Teste qui-quadrado de independência**.

