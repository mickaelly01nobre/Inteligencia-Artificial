
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

**Instalação das Dependências:**
Execute o seguinte comando para instalar as bibliotecas necessárias (o notebook já inclui um comando `!pip install` para a biblioteca `imbalanced-learn`):

```bash
pip install numpy pandas matplotlib seaborn scikit-learn imbalanced-learn
´´´
