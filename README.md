# CASE_DATA_MASTER_2024-25
This project is part of the DATAMASTER certification from Santander Brasil. It focuses on building a churn prediction model using data from a Music Streaming Company. The goal is to analyze customer behavior and predict churn, helping the company improve customer retention.

- Link para a base de dados: https://www.kaggle.com/datasets/gcenachi/case-data-master-2024

1. Qual o contexto da problemática? O que queremos resolver?
  - Uma empresa de streaming de música adota uma abordagem reativa para reter clientes que não renovam a assinatura, oferecendo 3 meses gratuitos. No entanto, identificou-se que essa abordagem pode ser menos eficaz do que uma ação proativa, que antecipa o comportamento dos clientes. O objetivo é criar um modelo preditivo para identificar clientes com alta probabilidade de churn (cancelamento) nos próximos 3 meses após a data de observação. A definição de churn utilizada considera clientes que: 
      - Possuem uma assinatura ativa no período de análise (data da safra);
      - Não renovaram ou não estão mais ativos nos 3 meses subsequentes.
  - O problema abordado, portanto, é o CHURN, com o foco em antecipar e evitar a saída de clientes.

2. Quais DADOS temos para trabalhar na solução?
  - Foi disponibilizado 3 tabelas: 
      - Members: Dados demográficos e informações de cadastro dos clientes, como idade, gênero, data de registro e meio pelo qual se registraram.
      - Transactions: Informações sobre planos, pagamentos, cancelamentos e renovações de assinaturas, incluindo preços e datas de vencimento.
      - User Logs: Dados comportamentais e de uso, como o número de músicas ouvidas (por diferentes durações) e o total de segundos ouvidos.

3. Como chegar na solução e quais métodos/tecnologias podem apoiar e quais não podem? (justificação dos usos, questões de negócio, performance, processamento computacional, recursos e implantação em uma hipotética produtização)
  - Dada a escala dos dados, pensando na escalabilidade, performance, produtização e organização, optou-se por ferramentas capazes de lidar com processamento distribuido. Foi feita a ingestão dos dados dentro de um data lake criado no Google Drive, com a estrutura organizada em camadas Raw, Bronze, Silver e Gold, permitindo ingestão e transformações sistemáticas dos dados. Para isso, será usado o PySpark e suas bibliotecas e o Google Colab que se conecta com o Drive para realização do EDA, ETL e treinamento dos modelos.

4. Ótica de negócios: Ganhos $$
  - Após o estudo finalizado, deve-se levar em consideração que 50% dos clientes identificados como Churn no periodo analisado foram retidos e permaneceram ativos pelos proximos 12 meses. Desses 12 meses, entende-se pelo enunciado que, 3 meses serão os da ação de meses gratuitos, e os outros 9 serão pagos pelo cliente. Com isso, é possivel calcular o Retorno sobre o Investimento (ROI), que é dado por:

  $$ 
  \text{ROI} = \frac{\text{Ganho Gerado Pela Ação} - \text{Custo da ação}}{\text{Custo da ação}} 
  $$

  - Assim através das colunas de valores dos planos de assinatura dos clientes, da para calcular o custo deles nos 3 meses gratuitos fornecidos (Custo da Ação) e o ganho dos outros 9 meses que ele irá pagar (Ganho Gerado Pela Ação). Esses resultados permitirão medir o impacto financeiro e a viabilidade da estratégia.

5. Segmentação dos clientes com uma abordagem não supervisionada
  - Após definido os churns e não churns, segmenta-los usando modelos de clusterização a fim de aprofundar a compreensão das características dos clientes  

# para considerar no desenvolvimento:

![FLUXO DOS DADOS](https://github.com/user-attachments/assets/ef11b7df-a4ef-417b-bc64-f2f30cd495f6)

1- EDA
- hipoteses voltadas ao problema e para a modelagem
- implicações das análises
- usar o EDA para tomada de decisões

2- Dataprep + feature engeneering + feature selection
- criação do publico-alvo, target, análise de volumetrias, missing, outliers, etc.
- construção de novas features / transformação de features
- feature selection adequado, variaveis significativas para o problema

3- Modelagem
- Estrutura do modelo utilizado, funcionamento, hiperparametros, vantagens e fraquezas
- Modelagem e pipe line adequados ao problema? eu entendo isso?
- Compreendo os impactos ao utilizar outras tecnicas de modelagem e pipeline construidos?

4- Validação
- Validação adequada? (Leakage, overfit, underfit, tamanho da amostra)
- Formas de validação exploradas? (cross-validation, train test split, out of sample, out of time, etc)
- Como as alterações do problema impactam na validação escolhida?

5- Definição e avaliação dos resultados
- Métricas de avaliação adequadas? (MAE, RMSE, Recall, AUC, Silhueta, etc)
- Como outras métricas impactariam os resultados do case?
- Como mudanças na estrutura do problema impactariam diferentes métricas?

6- Qualidade do código
- Organização e boas praticas do codigo (nomes intuitivos, comentários, ordenamento intuitivo)
- Codigo padronizado? (classes, funções e variaveis com nomes padronizados, clean code, pep8, etc?)
- Código visa a implementação? (modularização, tempo de processamento, versionamento etc?)

7- Soft Skills
- Sucinto e dentro do tempo indicado
- Clareza nas explicações
- Apresentação estruturada (começo, meio e fim)
