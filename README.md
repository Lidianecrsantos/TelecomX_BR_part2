Análise de Evasão de Clientes - TelecomX BR
Visão Geral do Projeto
Este projeto realiza uma análise detalhada do comportamento de evasão (churn) de clientes da TelecomX no Brasil. O objetivo é identificar os principais fatores que levam os clientes a cancelar seus serviços e desenvolver um modelo preditivo para identificar clientes em risco, permitindo a implementação de estratégias de retenção direcionadas.

Dados
Os dados utilizados nesta análise foram carregados a partir do arquivo telecomx_processed_data.csv. Este dataset contém informações sobre diversos clientes da TelecomX, incluindo dados demográficos, serviços contratados, informações de cobrança e a variável alvo Churn (indicando se o cliente evadiu ou não).

Pré-processamento de Dados
As seguintes etapas de pré-processamento foram realizadas para preparar os dados para a modelagem:

Remoção de colunas irrelevantes (customerID).
Codificação de variáveis categóricas utilizando One-Hot Encoding.
Análise e tratamento do desequilíbrio de classes na variável Churn utilizando a técnica de Oversampling SMOTE no conjunto de treino.
Divisão do conjunto de dados em treino e teste.
Escalonamento das features numéricas utilizando StandardScaler.
Análise Exploratória (EDA)
A análise exploratória inicial incluiu:

Verificação da distribuição da variável alvo (Churn) e identificação de desequilíbrio de classes.
Visualização da matriz de correlação para entender as relações entre as variáveis.
Análise detalhada da relação entre variáveis chave como tenure (tempo de contrato) e Charges.Total (total gasto) com a evasão, utilizando boxplots.
Modelagem Preditiva
Diversos modelos de classificação foram treinados e avaliados para prever a evasão de clientes:

K-Nearest Neighbors (KNN)
Regressão Logística
Árvore de Decisão
Random Forest
Os modelos foram treinados no conjunto de treino balanceado e escalonado e avaliados no conjunto de teste escalonado. As métricas de avaliação incluíram Accuracy, Precision, Recall e F1-score.

O modelo de Regressão Logística Otimizado apresentou o melhor desempenho geral no conjunto de teste, com destaque para o F1-score e Recall, métricas importantes em problemas com classes desbalanceadas.

Métricas do Melhor Modelo (Regressão Logística Otimizada):
Accuracy: 0.7639
Precision: 0.5416
Recall: 0.7124
F1-score: 0.6154
AUC: 0.8259
Principais Fatores de Evasão
Com base na análise dos coeficientes da Regressão Logística, na importância das variáveis do Random Forest e nos insights da análise exploratória, os principais fatores que contribuem para a evasão de clientes foram identificados:

Tempo de Contrato (tenure): Clientes com menor tempo de permanência são mais propensos a evadir.
Tipo de Contrato: Contratos mensais (Contract_Month-to-month) estão fortemente associados à evasão, enquanto contratos de dois anos (Contract_Two year) estão associados à permanência.
Serviços de Internet: Ter serviço de fibra óptica (InternetService_Fiber optic) aumenta a probabilidade de evasão, enquanto não ter serviço de internet (InternetService_No) está associado à permanência.
Serviços Online Adicionais: A ausência de serviços como Segurança Online, Suporte Técnico, Backup e Proteção de Dispositivo aumenta a propensão à evasão.
Método de Pagamento: O uso de cheque eletrônico (PaymentMethod_Electronic check) é um forte indicador de evasão.
Gasto Total (Charges.Total) e Gasto Mensal (Charges.Monthly)/Contas Diárias (Contas_Diarias): Menor gasto total acumulado e maior gasto mensal estão associados à evasão.
Estratégias de Retenção Propostas
Com base nos fatores identificados, as seguintes estratégias de retenção são sugeridas:

Clientes com Baixo Tempo de Contrato: Programas de boas-vindas e fidelidade intensivos nos primeiros meses.
Clientes com Contratos Mensais: Incentivos para migrar para contratos de longo prazo.
Clientes de Fibra Óptica sem Serviços Adicionais: Ofertas de pacotes de segurança/suporte.
Clientes Utilizando Cheque Eletrônico: Incentivos para migrar para métodos de pagamento automáticos.
Clientes com Baixo Gasto Total/Alto Gasto Mensal: Análise de uso e ofertas personalizadas para otimizar planos.
Conclusão
A análise e modelagem preditiva foram bem-sucedidas na identificação dos principais fatores de evasão. O modelo de Regressão Logística otimizado demonstrou ser eficaz na previsão de evasão, fornecendo insights valiosos para a implementação de estratégias de retenção direcionadas pela TelecomX.
