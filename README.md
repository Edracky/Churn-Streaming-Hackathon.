# CHURN-STREAMING-HACKATHON

Projeto de hackathon para prever **evasão de clientes (churn)** em um serviço de streaming, usando Regressão Logística e Random Forest dentro de um pipeline completo de machine learning.

***

## OBJETIVO DO PROJETO

- Identificar clientes com maior probabilidade de cancelar a assinatura, gerando um score de risco de churn para cada usuário.
- Apoiar o time de negócio com insights sobre quais variáveis numéricas (ex.: valor por hora, engajamento, satisfação) mais influenciam o churn.
- Entregar um **modelo treinado e salvo** em pipeline (`scikit-learn`) pronto para ser consumido por uma API do back-end do hackathon.

***

## DADOS E RECURSOS

- Base principal: `dados_streaming.csv`, contendo informações de uso da plataforma, perfil do cliente e status de churn.
- Ambiente: Google Colab, com notebooks organizados em etapas (EDA, preparação, modelagem e recomendações de negócio).
- Principais bibliotecas: `pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`.

***

## ETAPAS REALIZADAS

- **Exploração e limpeza de dados (EDA)**  
  - Tratamento de valores ausentes, correção de tipos e remoção de outliers críticos.  
  - Análises gráficas para entender distribuição de variáveis, proporção de churn e comportamento por segmento.

- **Engenharia de atributos**  
  - Criação de variáveis como `valor_por_hora`, indicadores de engajamento e métricas agregadas de uso e satisfação.  
  - Seleção de variáveis relevantes com base em correlação entre variáveis numéricas e comportamento de churn.

- **Modelagem e avaliação**  
  - Construção de um pipeline com pré-processamento e modelos de Regressão Logística e RandomForestClassifier com `class_weight='balanced'`.
  - Avaliação por AUC-ROC, matriz de confusão e análise de importância de features para interpretação dos resultados.

- **Geração de insights e recomendações**  
  - Identificação de perfis de maior risco (alto custo por hora, baixo engajamento, baixa satisfação).  
  - Definição de ações de retenção sugeridas para o time de negócio, como descontos segmentados e campanhas de reengajamento.

***

## COMO REPRODUZIR

- Clonar o repositório e instalar as dependências listadas em `requirements.txt` em um ambiente Python 3.8+.  
- Executar os notebooks na ordem sugerida na pasta `notebooks/` ou rodar o pipeline treinado carregando o arquivo de modelo salvo na pasta `models/`.

 ---

> 🧠 Projeto desenvolvido por **André** durante o **CHURN-STREAMING-HACKATHON**, atuando na trilha de **Data Science** com foco em previsão de churn e geração de insights acionáveis para o negócio.

