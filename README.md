PySpark Analytics Portfolio 🚀

Este repositório contém uma coleção de análises de dados e processos de ETL (Extract, Transform, Load) desenvolvidos inteiramente com Apache Spark (PySpark) e Python.

O foco deste projeto é demonstrar a aplicação prática de transformações de dados, manipulação de diferentes formatos de ficheiros e modelagem relacional utilizando o processamento distribuído do Spark.

📁 Estrutura do Projeto

O repositório está dividido em diferentes Jupyter Notebooks, cada um focando num domínio de negócio específico e explorando diferentes desafios de Engenharia de Dados:

analytics-viagem.ipynb (Logística & Faturamento):

Processamento de dados de viagens, fretes e motoristas.

Foco no tratamento de ficheiros JSON aninhados e conversão rigorosa de tipos monetários (Decimal).

analytics-soccer.ipynb (Análise Esportiva - Brasileirão):

Cruzamento de dados entre clubes e estatísticas de partidas.

Foco em funções de janelamento (Window Functions) e cruzamento de tabelas dimensionais (Joins).

analytics-ultra-trail-races.ipynb (Eventos Esportivos):

Análise de dados de corridas de longa distância.

🛠️ Tecnologias e Conceitos Aplicados

Neste laboratório de análises, foram aplicados conceitos fundamentais para a construção de pipelines de dados eficientes:

Leitura e Ingestão de Dados

Formatos Variados: Leitura de ficheiros .csv (com inferência de schema e delimitadores) e .json estruturados de APIs (multiline=True).

Self-Describing Formats: Preparação e escrita de dados em formatos colunares otimizados para Big Data, como Parquet, ORC e Avro.

Transformações (Transform)

Achatamento de Dados (Flattening): Uso intensivo da função explode() para desmembrar arrays (listas) e expansão de estruturas (structs) usando coluna.* para transformar dicionários em colunas relacionais.

Gestão de Tipos: Cast rigoroso de variáveis financeiras utilizando DecimalType (evitando perdas de precisão do Float/Double) e tratamento avançado de strings de data ISO 8601 com to_date e date_format.

Limpeza de Strings: Remoção otimizada de caracteres e acentos utilizando a função nativa translate e uso de Expressões Regulares (regexp_replace) para padronização de campos de texto.

Otimização de Código: Aplicação de withColumns (plural) com dicionários para múltiplas transformações no mesmo passo do plano lógico.

Modelagem e Agregações Avançadas

Joins: Utilização das funções de cruzamento (on, how) para simular relações de chaves estrangeiras entre tabelas fato e dimensão (Ex: LEFT JOIN, INNER JOIN).

Window Functions: Criação de janelas de processamento (Window.partitionBy().orderBy()) para calcular totais acumulados, rankings e partições lógicas sem necessidade de reduzir o DataFrame com groupBy().