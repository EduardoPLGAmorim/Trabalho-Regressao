# O Abismo Estrutural da Saúde: Preditores da Expectativa de Vida entre Nações

## Sobre o projeto

Este projeto investiga os principais fatores associados à **expectativa de vida ao nascer** entre diferentes países, utilizando técnicas de **análise exploratória de dados e regressão linear múltipla**.

O estudo busca compreender como indicadores de saúde, mortalidade, educação, renda e desenvolvimento estão relacionados à longevidade das populações, além de avaliar a capacidade de um modelo de regressão linear em explicar e estimar a expectativa de vida.

## Objetivos

- Identificar os principais fatores associados à expectativa de vida;
- Explorar relações entre indicadores de saúde, mortalidade e condições socioeconômicas;
- Avaliar a presença de valores ausentes e multicolinearidade;
- Construir um modelo de regressão linear múltipla;
- Selecionar variáveis utilizando o critério **AIC**;
- Avaliar a qualidade do ajuste e a capacidade preditiva do modelo;
- Diagnosticar possíveis violações das suposições do modelo.

## Dados

O conjunto de dados contém informações sobre **193 países**, originalmente abrangendo o período de **2000 a 2015**, compiladas a partir de informações da **Organização Mundial da Saúde (OMS)** e do **Banco Mundial**.

A variável resposta analisada é:

- **`Life.expectancy`** — expectativa de vida ao nascer, medida em anos.

Entre os indicadores considerados estão:

- Mortalidade adulta;
- Mortalidade infantil;
- Incidência de HIV/AIDS;
- Cobertura vacinal;
- PIB per capita;
- Escolaridade média;
- Índice de composição de recursos de renda;
- Indicadores de desnutrição;
- Status de desenvolvimento do país.

Devido à cobertura incompleta de algumas variáveis em 2015, a análise foi restringida ao período de **2000 a 2014**.

## Metodologia

A análise foi desenvolvida em quatro etapas principais:

### 1. Análise exploratória

Foram investigados:

- Distribuição da expectativa de vida;
- Valores ausentes;
- Relações entre preditores e variável resposta;
- Correlações entre variáveis;
- Possíveis problemas de multicolinearidade.

Variáveis com elevada proporção de valores ausentes foram excluídas do conjunto de preditores candidatos.

### 2. Transformação dos dados

Variáveis com distribuições altamente assimétricas foram transformadas para melhorar sua relação com a variável resposta, incluindo transformações logarítmicas da incidência de **HIV/AIDS** e do **PIB per capita**.

### 3. Construção e seleção do modelo

Foi inicialmente considerado um conjunto amplo de variáveis candidatas.

A seleção foi realizada utilizando o **AIC (Akaike Information Criterion)** por meio de um procedimento **stepwise bidirecional**, buscando equilibrar qualidade de ajuste e parcimônia.

### 4. Avaliação e diagnóstico

O modelo foi avaliado por meio de:

- Coeficiente de determinação;
- Intervalos de confiança dos coeficientes;
- Comparação entre valores observados e preditos;
- Análise dos resíduos;
- Teste de Breusch-Pagan;
- Teste de Shapiro-Wilk;
- Distância de Cook e identificação de observações influentes.

## Principais resultados

O modelo final apresentou **R² ajustado de aproximadamente 0,865**, indicando que cerca de **86,5% da variabilidade observada na expectativa de vida** é explicada pelo conjunto de preditores considerados.

Entre os fatores que apresentaram associações relevantes com a expectativa de vida estão:

- **Mortalidade adulta:** associação negativa;
- **Incidência de HIV/AIDS:** associação negativa;
- **Escolaridade média:** associação positiva;
- **Cobertura vacinal contra difteria:** associação positiva;
- **Indicadores de renda e desenvolvimento:** associação positiva;
- **Status de desenvolvimento:** países em desenvolvimento apresentaram menor expectativa de vida após o controle pelos demais fatores.

Os resultados destacam a relação entre **condições de saúde, educação e desenvolvimento socioeconômico** e a longevidade das populações.

## Diagnóstico e limitações

Os diagnósticos do modelo indicaram:

- Presença de **heterocedasticidade**;
- Desvios da hipótese de normalidade dos resíduos;
- Existência de observações influentes;
- Possível dependência entre observações de um mesmo país ao longo dos anos.

Além disso, por se tratar de um estudo observacional, as associações identificadas **não devem ser interpretadas como relações causais**.

## Tecnologias utilizadas

- **R**
- **tidyverse**
- **tidymodels**
- **ggplot2**
- **ggcorrplot**
- **knitr**
- **kableExtra**
- **MASS**
- **lmtest**
- **nortest**

## Arquivos 

| Arquivo                    | Descrição                                               |
| -------------------------- | ------------------------------------------------------- |
| `TF.Rmd`                   | Código em R e desenvolvimento da análise                |
| `TF.pdf`                   | Relatório final com metodologia, resultados e discussão |
| `Life Expectancy Data.csv` | Base de dados utilizada no estudo                       |
| `referencia.bib`           | Referências bibliográficas utilizadas                   |
| `README.md`                | Documentação e apresentação do projeto                  |

## Fonte dos dados

Arjarshi, Kumar. *Life Expectancy (WHO)*. Kaggle, 2018.

Os dados foram compilados a partir de informações da **Organização Mundial da Saúde (OMS)** e do **Banco Mundial**.

## Autores

- **Eduardo Penna Lima Guedes de Amorim**
- **Matheus Pierri de Oliveira**
- **Wan Tai Cheuk**
