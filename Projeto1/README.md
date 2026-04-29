# 🏥 Projeto de Busca em Labirinto com Chaves e Portas

## 📝 Descrição do Projeto

Este projeto implementa e compara dois algoritmos de busca para solucionar um problema de resgate em labirinto com obstáculos, chaves e portas. O cenário consiste em um robô que deve encontrar o caminho até um paciente, podendo coletar chaves para abrir portas específicas.

**Problema:**
- O robô (R) precisa encontrar o paciente (P) no labirinto
- Existem paredes (#) que bloqueiam a passagem
- Chaves (K_X) permitem abrir portas correspondentes (D_X)
- O robô pode coletar múltiplas chaves durante o trajeto

**Algoritmos Implementados:**
1. **BFS (Busca em Largura)** - Garante o caminho ótimo (menor número de movimentos)
2. **A* (A-estrela)** - Utiliza heurística de Manhattan para busca mais eficiente

O projeto inclui também um analisador estatístico que compara o desempenho de ambos os algoritmos em diferentes cenários.

## 🛠️ Linguagem Utilizada

**Python 3.7+**

O projeto foi desenvolvido inteiramente em Python, utilizando programação orientada a objetos e tipagem estática com `typing`.

## 📚 Bibliotecas Necessárias

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
´´´


