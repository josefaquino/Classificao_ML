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
O Random Forest Otimizado apresentou a melhor combinação de alta acurácia, um bom F1-score para a classe de churn e, crucialmente, uma alta Precision para a classe 'Churn' (0.71). Isso significa que, quando o modelo prevê que um cliente irá dar churn, essa previsão é altamente confiável, minimizando o desperdício de recursos em clientes que não iriam embora. Embora o KNN tenha um Recall ligeiramente superior, o Random Forest oferece um equilíbrio mais robusto e uma performance geral mais forte.

Implicações para o Negócio:

O Random Forest Otimizado é o modelo recomendado para ser implementado, pois ele oferece uma alta confiabilidade nas previsões de churn, permitindo que a empresa direcione seus esforços de retenção de forma mais eficiente. A identificação das características mais importantes pelo Random Forest também pode fornecer insights valiosos sobre os fatores que mais contribuem para o churn.

Como Reutilizar os Modelos

Os modelos treinados e os transformadores de dados estão salvos na pasta raiz desse projeto no formato pkl.

Principais aprendizados nesse curso:
 Árvores de Decisão: Explorei modelos mais simples que oferecem boa interpretabilidade, mostrando um equilíbrio entre complexidade e capacidade preditiva.

Modelos de Ensemble (Random Forest): O Random Forest se destacou, me ensinando sobre o poder de combinar múltiplos modelos simples para criar um mais robusto e preciso. Ele mostrou um desempenho superior na maioria das métricas.

KNN (K-Nearest Neighbors): Compreendi como modelos baseados em "vizinhança" funcionam e como a normalização dos dados é vital para eles.

Por fim, e talvez o mais importante, foi aprofundar na avaliação dos modelos. Não é só a acurácia que importa, especialmente com classes desbalanceadas. Aprendi a usar e interpretar métricas como Precision, Recall e F1-score, que me dão uma visão muito mais rica sobre os tipos de erros que o modelo comete. Também usei a Matriz de Confusão para visualizar esses erros e acertos, e a Curva ROC para entender o poder de discriminação do modelo.

E, claro, a parte de visualização de dados foi fundamental para apresentar esses resultados. Usar bibliotecas como Plotly, Seaborn e Matplotlib me permitiu criar gráficos interativos e bem elaborados que comunicam o desempenho dos modelos de forma clara e eficaz.

Para fechar, a ideia de salvar os modelos treinados (persistência com Pickle) foi um aprendizado prático e essencial para qualquer projeto de ML que vise ir para a produção, permitindo que os modelos sejam reutilizados sem precisar de retreinamento constante.

Em resumo, a aula me proporcionou uma visão completa do ciclo de vida de um projeto de classificação, desde a preparação dos dados até a avaliação e a persistência dos modelos, sempre com foco em métricas que realmente importam para o problema de negócio.
