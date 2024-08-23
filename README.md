# Quantidade de ouro puro extraído do minério de ouro

## Descrição do Projeto
Neste projeto vou desenvolver um protótipo de um modelo de aprendizado de máquina para prever a quantidade de ouro puro extraído do minério de ouro.
O modelo ajudará a otimizar a produção e eliminar parâmetros não rentáveis.

## Ferramentas e Bibliotecas Utilizadas
- Python: Linguagem principal utilizada para a análise.
- Pandas: Biblioteca para manipulação e análise de dados.
- Sklearn: Biblioteca para construção de modelo de machine learning.
- Matplotlib.pyplot e Seaborn: Biblioteca para construção de gráficos
- Functools: aplicação de funções

## Descrição dos Dados
Para o projeto já temos os conjuntos de treino e teste seprados.

**Processo tecnológico**
- Rougher feed — matéria-prima
- Rougher additions (ou aditivos reagentes) — reagentes de flotação: Xantato, Sulfeto, Depressor
- Xanthate — promotor ou ativador da flotação
- Sulphate — sulfeto de sódio para este processo específico
- Depressant — silicato de sódio
- Rougher process — flotação
- Rougher tails — resíduos do produto
- Float banks — unidade de flotação
- Cleaner process — purificação
- Rougher Au — concentrado de ouro bruto
- Final Au — concentrado de ouro final

**Parâmetros das etapas**
- air amount — volume of air — volume de ar
- fluid levels
- feed size — tamanho de partícula alimentada
- feed rate

**Nomeação de características**
Veja como nomeia as características:

[stage].[parameter_type].[parameter_name]

Exemplo: rougher.input.feed_ag

**Valores possíveis para [stage]:**
- rougher — (Minério bruto) flotação
- primary_cleaner — purificação primária
- secondary_cleaner — purificação secundária
- final — características finais

**Valores possíveis para [parameter_type]:**
- input — parâmetros de matéria-prima
- output — parâmetros do produto
- state — parâmetros que caracterizam o estado atual do processamento
- calculation — características de cálculo

## Processo Tecnológico
![image](https://github.com/user-attachments/assets/69dd1eab-20cd-4a13-8467-d5a4b108b8f6)

## Condições
- Calcular a retirada de ouro
- Métrica de avaliação sMAPE (erro percentual absoluto médio simetrico).
  ![image](https://github.com/user-attachments/assets/1e8a87c8-786b-4ef6-b820-d37adf919427)


## Metodologia
**Análise Exploratória de Dados**
- Importar as bibliotecas necessárias
- Carregar e visualizar os dados

**Pré Processamento**
- Valores ausentes
- Valores duplicados

**Análise de Dados**
- Concentração final dos minérios em cada etapa do processo
- Comparando a distribuição de partículas entre os conjuntos de teste e treino
- Verificando dados discrepantes das concentrações nos processos
- 

**Preparação do conjunto para o modelo**
- Identificação das festures e target do modelo
- Divisão dos conjuntos em treino, teste e validação

**Construindo e testando modelos**
- Regressão Linear, Árvore de Decisão e Floresta Aleatória
  - Treino
  - Teste
  - Métricas de avaliação sMAPE
 
## Resultados
Primeiro fizemos o pré-processamento dos dados e deixamos eles prontos para serem trabalhados. Após isso fizemos uma avaliação do comportamento dos resultados durante as fases do procedimento. 
Usamos a validação cruzada para verificar qual o melhor modelo para nosso projeto e, com base no smape, foi a Regressão da Floresta Aleatória. Depois de decidir qual modelo deveríamos usar, aplicamos o conjunto no conjunto de teste e comparamos os resultados com a métrica que nos foi fornecida, o smape_final que utiliza o smape(rougher) e smape(final), poir isso decidi separar ambas predições. 
O no final encontramos que existe uma diferença de aproximandamente 14.5 entre o conjunto de predição e o de teste.

## Aprendizados
- Análise de dados: interpretação e extração de insights valiosos a partir de grandes volumes de dados.
- Preparação do conjunto para aplicações em Machine Learning: separação do conjunto original em teste e treino, além da seleção das features e target do modelo.
- Funções: construção e aplicação de funções para simplificar o código.
- Regras de negócios: aplicação de regras de negócio para resolução de problemas.
- Aplicação de modelos de Machine Learning: aplicação, seleção de hiperparâmetros, teste e avalição do modelo.
- Documentação de projetos: elaboração de documentação clara e detalhada para garantir que o projeto seja compreensível e replicável.
- Utilização de bibliotecas e ferramentas: aplicação prática de diversas bibliotecas e ferramentas do ecossistema Python.
- Tomada de decisões baseadas em dados: uso de insights derivados da análise de dados para orientar decisões estratégicas.
