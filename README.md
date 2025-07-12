Previsão de Churn de Clientes

Este projeto de Machine Learning tem como objetivo desenvolver e comparar diferentes modelos preditivos para identificar clientes com alta probabilidade de churn (abandono) em um serviço. A previsão de churn é crucial para as empresas, permitindo que elas tomem medidas proativas para reter clientes valiosos, como oferecer promoções personalizadas ou suporte aprimorado.

Estrutura do Projeto

O projeto está organizado da seguinte forma:

    churn.csv: O conjunto de dados principal contendo informações sobre os clientes e seu status de churn.

    Notebooks (ou scripts Python):

        [Nome do seu notebook/script de análise de dados] (Ex: analise_exploratoria.ipynb): Contém a Análise Exploratória de Dados (EDA) e o pré-processamento inicial.

        [Nome do seu notebook/script de modelagem] (Ex: modelagem_churn.ipynb): Onde os modelos são construídos, treinados, otimizados e avaliados.

    modelos_churn_salvos/: Diretório que armazena os modelos treinados e os transformadores de dados (como OneHotEncoder e StandardScaler) em formato .pkl para futura reutilização sem necessidade de retreinamento.

Visão Geral do Problema

O churn de clientes é um desafio significativo para muitas empresas. Nossos dados contêm diversas características dos clientes, como score de crédito, idade, saldo, número de serviços adquiridos, salário estimado, e informações demográficas como país, sexo, estado, entre outros. O objetivo é utilizar essas informações para prever se um cliente irá "dar churn" (deixar o serviço) ou não.

Modelos e Métricas Avaliadas

Para abordar o problema de classificação de churn, foram explorados e comparados os seguintes modelos de Machine Learning:

    Dummy Classifier: Usado como linha de base para entender o desempenho mínimo aceitável.

    Regressão Logística: Um modelo linear simples e interpretável.

    Árvore de Decisão: Um modelo baseado em regras, com profundidade limitada para manter a interpretabilidade.

    KNeighbors Classifier (KNN): Um algoritmo baseado em distância, que classifica pontos com base em seus vizinhos mais próximos.

    Random Forest Classifier: Um modelo de ensemble poderoso, que combina múltiplas árvores de decisão para melhorar a robustez e a acurácia.

Dada a natureza desbalanceada dos dados de churn (geralmente poucos clientes dão churn), as métricas de avaliação focaram não apenas na Acurácia, mas também no F1-score, Recall e Precision especificamente para a classe minoritária (Churn), que são mais reveladoras nesses cenários. O SMOTE (Synthetic Minority Over-sampling Technique) foi aplicado para balancear as classes no conjunto de treinamento.
