# Comparação de Performance: Algoritmos de Dijkstra

## Objetivos do Projeto

Este projeto tem como objetivo comparar a performance de três versões do algoritmo de Dijkstra em grafos aleatórios:

1. **Dijkstra clássico** (O(V²))  
2. **Dijkstra com Min-Heap** (O(E log V))  
3. **Função de referência do NetworkX** 

A análise inclui tempo de execução e impacto ambiental (CO₂) para diferentes tamanhos de grafos, possibilitando uma avaliação prática da eficiência dos algoritmos.

---

## Configuração Experimental

### Tamanhos dos Grafos Testados

| Número de Nós | Observações |
|---------------|-------------|
| 100           | Testado |
| 500           | Testado |
| 1_000         | Testado |
| 5_000         | Testado |
| 10_000        | Testado |
| 50_000        | Testado |
| 100_000       | Não testado por limitações de hardware |

### Geração dos Grafos

- Grafos aleatórios do tipo `nx.gnp_random_graph(n, p=0.01)`
- Pesos inteiros aleatórios entre 1 e 10
- 5 nós aleatórios por grafo
- 15–20 repetições por configuração
- Sementes fixas para reprodutibilidade

### Métricas Coletadas

| Métrica                | Ferramenta |
|------------------------|------------|
| Tempo de execução (s)   | Python `time` |
| Emissão de CO₂ (g)      | CodeCarbon |

---

## 📂 Estrutura do Projeto

```bash
unity2/
│
├─ grafos/ # Grafos gerados e armazenados
├─ notebooks/ # Notebooks com implementações e análises
├─ tabelas/ # Tabelas com os resultados (CSV)
├─ graficos/ # Gráficos de performance e CO₂
└─ README.md

```

## 📊 Métricas e Estatística

Nesta etapa, você vai transformar os dados brutos coletados (tempos e emissões de CO₂ de cada execução) em informações estatisticamente interpretáveis.  
O objetivo é comparar o desempenho dos algoritmos a partir das médias e desvios-padrão das execuções.

Para cada par (**tamanho do grafo**, **algoritmo**), calcule:

| Métrica        | Símbolo       | Descrição |
|----------------|---------------|-----------|
| Média          | $\bar{x}$   | Tempo médio das execuções |
| Desvio-padrão  | $s$         | Mede a variação dos resultados em torno da média |

Para cada algoritmo e tamanho de grafo, plote:

- **Eixo X:** número de nós do grafo  
- **Eixo Y:** tempo médio  
- Uma linha para cada algoritmo  
- Barras verticais indicando a variação (\(s\))  


## 🏁 Resultados Esperados – Tempo de Execução

Após a execução completa dos algoritmos, espera-se observar diferenças claras no desempenho conforme o número de nós cresce.

---

### 1️⃣ Dijkstra Clássico (O(V² + E))  

![Dijkstra Clássico](graficos/dijkstra_classico.png)  
*Figura: Tempo médio de execução do Dijkstra Clássico para diferentes tamanhos de grafos.*

---

### 2️⃣ Dijkstra com Min-Heap (O(V + E) * log V)  

![Dijkstra Min-Heap](graficos/dijkstra_min_heap.png)  
*Figura: Tempo médio de execução do Dijkstra com Min-Heap para diferentes tamanhos de grafos.*

---

### 3️⃣ NetworkX  

![NetworkX](graficos/networkx.png)  
*Figura: Tempo médio de execução da função de referência do NetworkX para diferentes tamanhos de grafos.*

---

