#  Projeto de Busca em Labirinto com Chaves e Portas

##  Descrição do Projeto

Este projeto implementa e compara dois algoritmos de busca para solucionar um problema de resgate em labirinto com obstáculos, chaves e portas. O cenário consiste em um robô que deve encontrar o caminho até um paciente, podendo coletar chaves para abrir portas específicas.

**Problema:**
- O robô (R) precisa encontrar o paciente (P) no labirinto
- Existem paredes (#) que bloqueiam a passagem
- Chaves (K_X) permitem abrir portas correspondentes (D_X)
- O robô pode coletar múltiplas chaves durante o trajeto

**Algoritmos Implementados:**
1. **BFS (Busca em Largura)** - Garante o caminho ótimo (menor número de movimentos)
2. **A (A-estrela)** - Utiliza heurística de Manhattan para busca mais eficiente

O projeto inclui também um analisador estatístico que compara o desempenho de ambos os algoritmos em diferentes cenários.

##  Linguagem Utilizada

**Python 3.7+**

O projeto foi desenvolvido inteiramente em Python, utilizando programação orientada a objetos e tipagem estática com `typing`.

##  Bibliotecas Necessárias

### Bibliotecas Padrão (já inclusas no Python):
- `collections` - Para uso de deque (fila)
- `time` - Medição de tempo de execução
- `tracemalloc` - Monitoramento de uso de memória
- `heapq` - Implementação de fila de prioridade para A*
- `typing` - Anotações de tipo
- `math` - Operações matemáticas básicas

### Bibliotecas Opcionais (para geração de gráficos):
```bash
!pip install matplotlib
``` 

> **Nota:** O matplotlib é opcional e usado apenas para visualização gráfica dos resultados. O projeto funciona perfeitamente sem ele.

##  Instruções para Executar os Experimentos no Google Colab

### 1. Preparação do Ambiente

Primeiro, copie todo o código do projeto para uma célula do Colab ou faça o upload do arquivo .ipynb e execute todas as células, desde a primeira até a última. Após a execução, serão realizados 6 testes (um para cada labirinto). Em cada teste, é necessário pressionar a tecla Enter para prosseguir para o próximo.

##  Estrutura dos Arquivos

O projeto está contido em um único arquivo Python, organizado nos seguintes módulos:

---

### 🔹 Módulo 1: Definição do Estado e Labirinto

- **Estado** – Representa um estado da busca (posição, chaves coletadas, caminho)

- **Labirinto** – Gerencia o labirinto e suas operações:
  - Carregamento do mapa
  - Verificação de movimentos válidos
  - Coleta de chaves e abertura de portas
  - Heurística de Manhattan

---

### 🔹 Módulo 2: Algoritmo BFS

- **BFS** – Implementação da Busca em Largura
  - Fronteira usando `deque` (fila)
  - Conjunto de estados visitados
  - Métricas de desempenho (tempo, memória, nós expandidos)

---

### 🔹 Módulo 3: Algoritmo A*

- **AStar** – Implementação do A* com heurística Manhattan
  - Fronteira com `heapq` (fila de prioridade)
  - Dicionários `g_score` e `f_score`
  - Garantia de otimalidade

---

### 🔹 Módulo 4: Gerador de Cenários

- **GeradorCenarios** – Cria 6 cenários de teste:
  - Simples – Sem obstáculos  
  - Com Chave – Uma chave e uma porta  
  - Complexo – Múltiplas chaves e portas  
  - Sem Solução – Impossível de resolver  
  - Grande – Labirinto 15x15  
  - Desafiador – Testa qualidade da heurística  

---

### 🔹 Módulo 5: Analisador Comparativo

- **AnalisadorComparativo** – Compara resultados entre BFS e A*
  - Tabelas comparativas
  - Análise de ganhos percentuais
  - Análise de qualidade da solução
  - Avaliação da heurística
  - Relatório final detalhado

---

### 🔹 Módulo 6: Execução Principal

- **executar_no_colab()** – Função principal que:
  - Executa todos os cenários
  - Coleta estatísticas
  - Gera relatórios
  - Opcionalmente, gera gráficos com `matplotlib`
 
### 🔹 Pasta Resultados

  Nessa parta contém as imagens da tabela comparativa entre os algoritmos e os graficos de memória, tempo de execução, estados explorados e nós expandidos

 ##  Exemplo de Saída no Colab

```text
============================================================
EXECUTANDO BFS - 2. Com Chave A e Porta A
============================================================

LABIRINTO: 2. Com Chave A e Porta A
============================================================
R....
.# # #.
..K_A..
.# # #.
...D_AP

RESULTADOS DA BUSCA BFS
============================================================

 1. QUALIDADE DA SOLUÇÃO:
   ✓ Solução encontrada: SIM
   ✓ Tipo: ÓTIMA (BFS garante caminho mínimo)

 2. CUSTO DA SOLUÇÃO:
   Movimentos: 12

 3. ESTADOS EXPLORADOS:
   Nós gerados: 245
   Nós expandidos: 187
   
 4. TEMPO DE EXECUÇÃO:
   0.0234 segundos

 5. USO DE MEMÓRIA:
   Pico: 2.34 MB
```

##  Principais Características do Código

- **Orientação a Objetos:** Classes bem definidas para cada componente  
- **Métricas Detalhadas:** Medição de tempo, memória, nós gerados/expandidos  
- **Flexibilidade:** Fácil adicionar novos cenários ou heurísticas  
- **Documentação:** Docstrings explicativos em todas as classes e métodos  
- **Tipagem Estática:** Uso de `typing` para melhor legibilidade  
- **Visualização:** Opção de gerar gráficos comparativos (quando `matplotlib` está instalado)  

---

##  Possíveis Modificações

Para adaptar o código a outros problemas:

- **Nova Heurística:** Substitua `heuristica_manhattan()` na classe `Labirinto`  
- **Novos Movimentos:** Modifique `direcoes` na classe `Labirinto`  
- **Custos Diferentes:** Altere `custo` na função `transicao()`  
- **Novos Cenários:** Adicione métodos em `GeradorCenarios`  



