
# Detecção de Falhas em Processos Industriais (Dataset SECOM)

Este projeto tem como objetivo desenvolver e comparar modelos preditivos para a detecção antecipada de falhas em processos industriais, utilizando dados de sensores do dataset público SECOM (Semiconductor Manufacturing). O problema é tratado como uma tarefa de classificação binária, onde o modelo deve classificar cada amostra como "condição normal de operação" (Classe 0) ou "falha iminente ou já ocorrida" (Classe 1).

## Descrição do Projeto

Este projeto explora a aplicação de técnicas de aprendizado de máquina para a manufatura de semicondutores, adaptando o contexto para a pirrometalurgia. A solução proposta compara o desempenho de dois modelos de classificação supervisionada:

* **Random Forest:** Um ensemble de árvores de decisão, conhecido por sua robustez e capacidade de lidar com dados tabulares.
* **Support Vector Machine (SVM):** Um modelo que busca uma fronteira de separação ótima entre as classes, utilizando o kernel RBF para capturar relações não-lineares.

O pipeline do projeto inclui desde o download e pré-processamento dos dados até a avaliação detalhada dos modelos, com foco em métricas de desempenho e análise de *overfitting*.

## Linguagem Utilizada

* Python 3

## Bibliotecas Necessárias

As bibliotecas utilizadas neste projeto estão listadas abaixo. A maioria delas é padrão em ambientes de ciência de dados. Para instalar as principais dependências, você pode usar o `pip`.

**Principais Bibliotecas:**
* `numpy`
* `pandas`
* `matplotlib`
* `seaborn`
* `scikit-learn` (sklearn)
* `imbalanced-learn` (para SMOTE)
* urllib (para download dos dados)
* time (para medição de tempo de execução)
* warnings (para gerenciamento de avisos)

**Instalação das Dependências:**
Execute o seguinte comando para instalar as bibliotecas necessárias (o notebook já inclui um comando `!pip install` para a biblioteca `imbalanced-learn`):

```bash
pip install numpy pandas matplotlib seaborn scikit-learn imbalanced-learn
```

## Como Executar os Experimentos

O projeto foi desenvolvido e testado no ambiente **Google Colab**, o que simplifica a execução, pois o ambiente já vem com a maioria das bibliotecas pré-instaladas.

### 1. Abrir o Notebook no Colab

Faça o upload do arquivo `projeto2.ipynb` para o Google Colab ou abra-o diretamente de um repositório do GitHub.

### 2. Executar as Células

- Execute as células sequencialmente. Cada módulo do notebook é responsável por uma etapa do pipeline.
- O notebook é auto-contido e, ao ser executado, fará o download automático do dataset SECOM do repositório da UCI.

### 3. Interpretação dos Resultados

Ao final da execução, o notebook gerará gráficos de comparação (Matriz de Confusão, Curvas ROC) e imprimirá uma tabela com as métricas de desempenho (Recall, Precision, F1-Score, AUC-ROC) para cada modelo.

## Estrutura dos Arquivos

O projeto é composto por um único arquivo Jupyter Notebook (`.ipynb`), que contém todo o código e documentação. A estrutura do notebook é organizada em módulos para facilitar a compreensão:

- **Módulo 1: Instalação e Importação de Bibliotecas**  
  Configuração do ambiente e importação de todas as bibliotecas necessárias.

- **Módulo 2: Download e Carregamento do Dataset**  
  Baixa os dados do SECOM da UCI e cria rótulos sintéticos para a variável alvo (falha/normal).

- **Módulo 3: Pré-processamento dos Dados**  
  Seleciona os primeiros 96 sensores, remove colunas com alta taxa de dados faltantes (>40%) e imputa os valores restantes usando o algoritmo KNN Imputer.

- **Módulo 4: Feature Engineering - Janelas Temporais**  
  Extrai características estatísticas (média, desvio padrão, tendência, etc.) a partir de janelas temporais de 30 timesteps, criando features mais significativas para os modelos.

- **Módulo 5: Divisão Treino/Teste e Padronização**  
  Divide os dados em conjuntos de treino e teste (80%/20%) de forma temporal e padroniza as features com `StandardScaler`.

- **Módulo 6: Balanceamento de Classes com SMOTE**  
  Aplica a técnica SMOTE para lidar com o severo desbalanceamento das classes no conjunto de treino.

- **Módulo 7: Modelo 1 - Random Forest**  
  Treina e otimiza um modelo Random Forest com regularização forte, utilizando Grid Search e validação cruzada.

- **Módulo 8: Modelo 2 - SVM**  
  Treina e otimiza um modelo SVM com Kernel RBF e regularização forte, utilizando PCA e subamostragem para reduzir a dimensionalidade e custo computacional.

- **Módulo 9: Visualização e Comparação dos Resultados**  
  Gera matrizes de confusão, curvas ROC e gráficos de barras para comparar o desempenho dos dois modelos, além de uma análise final e recomendações.

  ## Base de Dados

- **Nome:** SECOM (Semiconductor Manufacturing Process)
- **Fonte:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/179/secom)
- **Características:**
  - **Total de Amostras:** 1567
  - **Total de Sensores:** 590
  - **Proporção de Falhas:** Aproximadamente 2% (criada sinteticamente para este projeto).

O notebook, em seu **Módulo 2**, baixa automaticamente os dados do arquivo `secom.data` da UCI e gera os rótulos sintéticos para a classe de falha com base na literatura.
