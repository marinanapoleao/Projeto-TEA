# Projeto Aplicação de Machine Learning na Análise do Transtorno do Espectro Autista
<img width="1280" height="698" alt="image" src="https://github.com/user-attachments/assets/47e622b1-70c6-4e8e-9366-0468a2a69d09" />

### *Um estudo comparativo de algoritmos de classificação para apoio à tomada de decisão.*
### *Nosso modelo de Machine Learning, alimentado por dados precisos e análises detalhadas, representa um caminho promissor para a busca do diagnóstico de TEA, proporcionando um suporte importante para que as pessoas busquem ajuda de profissionais da saúde.*

## 📌 Sobre o Projeto

Este projeto aplica técnicas de ciência de dados e machine learning sobre uma base de triagem de Transtorno do Espectro Autista (TEA) em adultos, construída a partir do questionário AQ-10 — um instrumento de 10 perguntas usado para rastrear traços associados ao espectro autista. O trabalho foi dividido em duas etapas (dois notebooks): consolidação/tratamento dos dados e, em seguida, um "duelo" comparativo entre quatro modelos de classificação.



## 🎯 Problema de Negócio / Pergunta de Pesquisa
Problema: Identificar, a partir das respostas do questionário AQ-10 e de dados demográficos, padrões associados a um resultado positivo de triagem para TEA.

## Objetivo
Treinar e comparar quatro modelos de classificação (Regressão Logística, Random Forest, XGBoost, SVM) para prever a classe de triagem (Class/ASD), avaliando qual oferece o melhor equilíbrio entre sensibilidade (recall) e precisão.
Público/impacto: Times de saúde ou plataformas de triagem que busquem uma ferramenta de apoio inicial para sinalizar respondentes que merecem avaliação clínica mais aprofundada.


## 📊 Fonte de Dados
*Origem:* dataset de triagem Autism Screening Adult (autism_screening.csv), baseado no questionário AQ-10.

*Variáveis principais:* 10 perguntas do questionário (quest1 a quest10, respostas binárias), idade, gênero, etnia, histórico de icterícia ao nascer, parentesco com pessoa autista, país, uso prévio de triagem, resultado numérico do teste, maioridade, quem respondeu o questionário, e a classe-alvo Class/ASD.

*Pré-processamento realizado:*
Remoção de registros sem idade preenchida
Padronização de variáveis categóricas binárias (yes/no, m/f etc.) via mapeamento seguro de strings
Renomeação de todas as colunas para português
Detecção e remoção de outliers (idades impossíveis, acima de 120 anos)
Análise de balanceamento das classes antes da modelagem
## 🛠️ Tecnologias Utilizadas
*Python:* 
pandas / numpy — manipulação de dados
matplotlib / seaborn / plotly — visualização
scikit-learn — pré-processamento, modelos, métricas, GridSearchCV, validação cruzada
imbalanced-learn (SMOTE) — balanceamento de classes
XGBoost
Jupyter Notebook



## 🔍 Metodologia
*Coleta de dados:* leitura da base de triagem autism_screening.csv.

*Limpeza e tratamento:* remoção de nulos, padronização de variáveis binárias, renomeação de colunas.

*Análise exploratória (EDA):* análise univariada (boxplots por questão) e bivariada (cada pergunta do AQ-10 vs. classe TEA), além de análise de balanceamento das classes.

*Tratamento de outliers:* identificação via IQR e remoção de idades impossíveis (> 120 anos).

*Correlação:* matriz de correlação entre variáveis numéricas (heatmap).

*Modelagem:* divisão treino/teste (80/20) e comparação de 4 algoritmos — Regressão Logística, Random Forest, XGBoost e SVM.

*Balanceamento e padronização:* pipelines com SMOTE + StandardScaler para lidar com o desbalanceamento das classes.

*Otimização de hiperparâmetros:* GridSearchCV com validação cruzada estratificada (5-fold), otimizando recall como métrica-alvo (prioridade: minimizar falsos negativos).

*Validação:* avaliação final com matriz de confusão e relatório de classificação no conjunto de teste.



## 📈 Resultados e Métricas
Modelo	Accuracy	Precisão (Classe TEA)	Recall (Classe TEA)

Regressão Logística	0.95	0.86	1.00

Random Forest	0.92	0.81	0.98

XGBoost	0.93	0.82	0.98

SVM (kernel RBF)	0.91	0.78	1.00

#### Modelo final escolhido: XGBoost — melhor equilíbrio entre sensibilidade e precisão, com boa capacidade de generalização.



## 💡Principais Insights e Implicações

*Regressão Logística e SVM* atingiram recall máximo (1.00) na classe positiva — nenhum caso de TEA passou despercebido, o que é especialmente desejável em cenários de triagem, onde um falso negativo é mais custoso que um falso positivo.

*Random Forest e XGBoost* apresentaram menos falsos positivos, com desempenho mais equilibrado entre precisão e recall.

O dataset mostrou padrões fortemente separáveis entre as classes, o que explica as métricas elevadas obtidas por todos os modelos testados.


### ⚠️ Nota: este modelo é uma ferramenta de apoio à triagem construída para fins de estudo/portfólio — não substitui avaliação ou diagnóstico clínico profissional.


<img width="2000" height="1156" alt="image" src="https://github.com/user-attachments/assets/5c86fc8d-3ea2-4334-881b-0efdf7f303c3" />

### 𓂃🖊 Apresentação Storytelling: <https://canva.link/lbkaeskb6mf3bwj>

## 👩‍💻 Sobre a Autora

Desenvolvido por Marina Napoleão — Cientista de Dados / Analista de Dados. 
### LinkedIn <https://www.linkedin.com/in/marina-napoleao/>
### GitHub <https://github.com/marinanapoleao> 
