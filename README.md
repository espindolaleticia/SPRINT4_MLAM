# Challenge Sprint 4 — Modelagem Linear

## Integrantes
* Felipe Perdigão Macedo RM570990
* Felipe Mitsuo Takahashi Stephano — RM570692
* Laura Godoy Callegari — RM569181
* Letícia Araújo Espíndola — RM569308
* Mariana Dreset Carbollan — RM569207
* Milena de Aguiar Lopes Cardoso — RM570599

## Sobre o projeto

Este projeto foi desenvolvido para o Challenge Sprint 4 da disciplina de Modelagem Linear para Aprendizado de Máquina.

O objetivo foi utilizar técnicas de aprendizado de máquina para classificar a produção de energia renovável em três categorias:

* Low
* Medium
* High

Para isso, foi utilizado o dataset **Renewable Energy Production Dataset (2010–2020)** e um modelo de classificação linear.

## Dataset

O dataset possui informações relacionadas à produção de energia e às condições climáticas.

As principais variáveis utilizadas foram:

* `Temperature_C`
* `Wind_Speed_m_s`
* `Solar_Radiation_kWh_m2`
* `Rainfall_mm`
* `Efficiency_Ratio`
* `Lagged_Production_MWh`
* `Combined_Weather_Index`

A variável alvo foi `Energy_Class`.

As categorias foram convertidas para valores numéricos:

* Low = 0
* Medium = 1
* High = 2

As colunas `Region`, `Energy_Source` e `Season` não foram utilizadas na matriz de correlação por serem variáveis categóricas.

## Análise de correlação

Foi criada uma matriz de correlação utilizando as variáveis numéricas e a variável `Energy_Class` codificada.

A maior correlação encontrada com a variável alvo foi aproximadamente **0,21**, indicando uma relação linear relativamente fraca entre as variáveis individuais e a classe de energia.

Como não foram encontradas correlações muito altas entre as próprias variáveis, optamos por manter todas as features numéricas selecionadas.

## Modelo utilizado

Foi utilizado o modelo **Logistic Regression**, disponível na biblioteca Scikit-learn.

A Regressão Logística foi escolhida por ser um modelo de classificação linear. Seu funcionamento utiliza uma combinação linear das variáveis de entrada para definir as regiões de decisão entre as classes.

Antes do treinamento, as variáveis foram padronizadas utilizando o `StandardScaler`.

## Cenários avaliados

Foram realizados dois testes, mantendo o mesmo modelo e as mesmas condições de execução.

### Cenário 1

* 60% dos dados para treinamento
* 40% dos dados para teste

### Cenário 2

* 85% dos dados para treinamento
* 15% dos dados para teste

Em ambos os cenários foi utilizado `random_state = 42`.

## Avaliação

Para avaliar o modelo foram utilizadas as seguintes métricas:

* Accuracy
* Precision
* Recall
* Matriz de confusão

Os resultados ficaram próximos de **78% a 79% de acurácia** nos dois cenários.

O modelo apresentou um desempenho melhor na identificação da classe **High**, enquanto houve mais confusão entre as classes **Low** e **Medium**.

## Comparação dos cenários

O cenário com 60% de treinamento e 40% de teste possui uma quantidade maior de dados para avaliação, tornando a análise do desempenho mais estável.

Já o cenário com 85% de treinamento e 15% de teste disponibiliza mais dados para o modelo aprender, porém possui uma quantidade menor de exemplos para avaliação.

Mesmo com o aumento da quantidade de dados de treinamento, o desempenho dos dois cenários ficou bastante próximo. Isso indica que aumentar o conjunto de treinamento não trouxe uma melhora significativa para este modelo.

## Conclusão

A Regressão Logística apresentou um desempenho próximo de 78% a 79% nos dois cenários avaliados.

A análise também mostrou que as variáveis disponíveis possuem uma relação linear relativamente fraca com a variável `Energy_Class`. Por isso, o tamanho do conjunto de treinamento não foi o principal fator que limitou o desempenho do modelo.

De forma geral, o modelo conseguiu realizar a classificação das categorias de produção de energia, mas ainda apresentou dificuldades principalmente na diferenciação entre as classes Low e Medium.

## Arquivos do projeto

O repositório contém:

* Dataset utilizado no projeto
* Notebook com o código em Python
* Matriz de correlação
* Matrizes de confusão
* Métricas dos dois cenários
* Gráficos e resultados da análise

## Tecnologias utilizadas

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook / Google Colab
