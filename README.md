# Regressão Linear com Transformação de Box-Cox para Previsão de Consumo de Combustível

Este projeto tem como objetivo prever o consumo de combustível de automóveis com base em características técnicas como número de cilindros, volume do motor, potência, ano do modelo, peso, entre outras variáveis. Para isso, foi utilizado um modelo de regressão linear com transformação de Box-Cox para melhorar a normalidade dos dados e a performance do modelo.

## Tecnologias e Bibliotecas Utilizadas

- Python (Jupyter Notebook)
- Pandas
- NumPy
- Scikit-learn
- SciPy
- Matplotlib / Seaborn

## Arquivos

- `regressao_linear_boxcox.ipynb`: notebook principal com todo o passo a passo do projeto, desde a análise exploratória até a avaliação do modelo.

## Objetivos do Projeto

- Realizar análise exploratória de dados (EDA) para entender as variáveis que influenciam o consumo de combustível.
- Aplicar regressão linear com transformação Box-Cox na variável dependente, com o objetivo de melhorar os pressupostos do modelo.
- Avaliar o desempenho do modelo e interpretar os coeficientes.

## Conjunto de Dados

Os dados contêm características técnicas de automóveis, incluindo:
- `cylinders`: número de cilindros
- `displacement`: volume do motor (em polegadas cúbicas)
- `horsepower`: potência do motor
- `weight`: peso do carro
- `model year`: ano do modelo
- `acceleration`: tempo de aceleração
- `origin`: origem do carro (codificada)
- `mpg`: consumo de combustível (milhas por galão) — variável alvo

> ([Fonte dos dados](https://archive.ics.uci.edu/ml/datasets/auto+mpg))

## Etapas do Projeto

1. **Definição do problema de negócio**
2. **Entendimento e aquisição dos dados**
3. **Preparação dos dados**
4. **Análise exploratória dos dados**
5. **Modelagem**
6. **Validação do modelo**
7. **Interpretação dos resultados**

## Principais Resultados

**Base de dados**

- Variável dependente (y): Não seguia distribuição normal, exigiu tranformação box-cox
- Variáveis independentes numéricas: Variáveis numéricas não seguiam distribuição normal. Apesar da aplicação da transformação logarítmica, ainda não seguiam distribuição normal.
- Variáveis independentes categóricas: Aplicou-se agrupamento de categorias e dummização.

**Construção do modelo**

- Modelos testados: Testou-se os modelos com transformações apenas em X e com transformação em X e y (box-cox).
- Seleção de variáveis: Aplicou-se seleção de variáveis manualmente, excluindo variáveis com alta correlação entre si e, posteriormente, utilizando o método backwards com p-valor.
- O modelo com tranformação box-cox performou melhor.
- Apesar de visualmente os resíduos não aparentarem seguir um padrão, o teste de Breusch-Pagan apresenta heterocedasticidade. Em uma análise gráfica mais profunda, observa-se que a taxa de erro tende a aumentar à medida que o valor real aumenta.
- Como, após a seleção manual de variáveis com base em colinearidade, manteve-se apenas uma variável numérica independente, não observa-se problemas com multicolinearidade.
