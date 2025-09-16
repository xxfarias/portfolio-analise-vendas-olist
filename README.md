# Análise de Vendas e Segmentação de Clientes para E-commerce (Dataset Olist)

## Visão Geral do Projeto

Este projeto apresenta uma análise de dados completa de ponta a ponta, utilizando um [dataset público da Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) com mais de 100.000 pedidos. O objetivo é transformar dados brutos em insights estratégicos e acionáveis, culminando em um dashboard interativo que poderia ser usado pela diretoria para a tomada de decisão.

A análise foca em entender a performance de vendas e logística, o comportamento do consumidor e, principalmente, em identificar oportunidades para aumentar a fidelização de clientes através da segmentação com a metodologia RFM.

---

### 🎥 Demonstração em Vídeo do Dashboard

Para uma experiência interativa e guiada pelos principais insights, assista a esta curta demonstração em vídeo do dashboard.

**[➡️ Assista à Demonstração do Dashboard no YouTube](link-video-a-ser-publicado)**

---

## 🛠️ Ferramentas Utilizadas

* **Linguagens:** SQL, Python, DAX (Power BI)
* **Banco de Dados / DWH:** Google BigQuery
* **Bibliotecas Python:** Pandas (Manipulação de Dados), Seaborn & Matplotlib (Visualização de Dados)
* **Ferramentas de BI:** Microsoft Power BI (ETL com Power Query, Modelagem de Dados e Visualização)
* **Ambiente de Desenvolvimento:** Google Colab
* **Versionamento:** Git & GitHub

---

## 📂 Estrutura do Repositório

* **`analise_olist_completa.ipynb`:** O notebook do Colab contendo todo o processo de análise em Python, desde a exploração inicial até a segmentação RFM final.
* **`olist_dados_processados.csv`:** O arquivo de dados principal, já limpo e processado, utilizado pelo notebook para garantir a reprodutibilidade da análise.
* **`dados_rfm_clientes.csv`:** Um arquivo de dados secundário, exportado após a análise RFM, que é utilizado na segunda página do dashboard.
* **`/imagens` (pasta opcional):** Contém as imagens dos gráficos gerados no Python, utilizadas nesta documentação.

---

## 🚀 Fases da Análise

O projeto foi estruturado em quatro fases principais:

### Fase 1: Extração e Análise Exploratória (SQL)

A exploração inicial foi realizada no Google BigQuery para entender a estrutura, volume e integridade dos dados brutos. Foram respondidas perguntas de negócio fundamentais sobre o volume de pedidos, status, período de tempo coberto e métodos de pagamento preferidos.

### Fase 2: Análise Aprofundada e Segmentação (Python)

Utilizando Python, a análise foi aprofundada para entender o "porquê" por trás dos números.
* **Análise de Preços:** Através de estatísticas descritivas, histogramas e boxplots, foi identificada uma forte assimetria na distribuição de preços, provando que a **mediana** é uma métrica mais confiável que a média para o "preço típico".
* **Análise Logística:** Foi criada a feature `tempo_entrega_dias` e sua análise revelou a presença de outliers (entregas extremamente longas), levantando a hipótese de que desafios logísticos se concentram em regiões específicas.
* **Análise Geográfica:** A análise consolidada por estado e região confirmou a dominância do Sudeste em volume de vendas, mas revelou um **Ticket Médio superior em outras regiões**, sugerindo diferentes comportamentos de compra.
* **Segmentação de Clientes (RFM):** O ponto alto da análise. Clientes foram segmentados com base na sua Recência, Frequência e Valor Monetário, revelando o maior desafio estratégico do negócio: **a baixíssima taxa de retenção de clientes (>98% de clientes de uma única compra)**.

### Fase 3: Visualização e Dashboard (Power BI)

Os dados processados e enriquecidos foram levados ao Power BI para a criação de uma ferramenta de decisão visual e interativa.
* **ETL e Modelagem:** O Power Query foi utilizado para o tratamento final dos dados (renomeação, tipos de dados, filtros). Foi criado um modelo de dados relacional (esquema estrela) para garantir a integridade dos cálculos.
* **Medidas DAX:** Foram criadas medidas DAX robustas para os KPIs principais (Receita, Pedidos, Ticket Médio, etc.), garantindo que os cálculos fossem corretos e consistentes em todo o dashboard.
* **Páginas do Relatório:**
    * **Visão Geral:** Apresenta os KPIs principais e visuais sobre a performance temporal e geográfica do negócio.
    * **Análise de Clientes (RFM):** Permite a exploração interativa de cada segmento de cliente, mostrando seu tamanho, valor e características.

---

## 🎯 Conclusão e Recomendações Estratégicas

1.  **O Negócio é Sazonal e Geograficamente Dependente:** A análise confirmou a importância da Black Friday (Novembro) para o faturamento e a dominância do Sudeste. Recomenda-se uma **estratégia de marketing e logística dupla**: foco em **frequência** no Sudeste e em aumentar o **valor do carrinho** nas demais regiões.

2.  **O Maior Desafio é a Retenção de Clientes:** A análise RFM provou que o modelo de negócio é altamente eficaz na aquisição, mas ineficaz na fidelização. Recomenda-se a implementação de um **plano de ação de marketing focado em incentivar a segunda compra** dos "Novos Clientes", que representam quase 50% da base.

---

## 🔮 Próximos Passos

Este projeto estabeleceu uma base sólida. As próximas etapas para aprofundar a análise seriam:
* **Análise Logística Aprofundada:** Correlacionar o tempo de entrega com as notas de avaliação (`review_score`).
* **Análise de Sentimentos (NLP):** Utilizar NLP nos comentários das avaliações para entender as razões qualitativas da satisfação (ou insatisfação) do cliente.
* **Modelagem Preditiva (Machine Learning):** Construir um modelo de previsão de churn para atuar proativamente na retenção de clientes.
