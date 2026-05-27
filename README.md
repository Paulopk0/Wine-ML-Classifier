# 🍷 Esteira de Machine Learning — Wine Recognition

| Campo | Detalhe |
|---|---|
| **Aluno** | Paulo Gabriel Alves Dos Santos |
| **Professor** | Leonardo Villani |
| **Prazo** | 27 de maio de 2026 |
| **Disciplina** | Inteligência Artificial |
| **Algoritmo** | XGBoost Classifier |
| **Dataset** | Wine Recognition — UCI / sklearn |

---

## 📋 Sobre o Projeto

Esteira completa de Machine Learning para **classificar tipos de vinho** com base em 13 propriedades químicas (álcool, ácido málico, cinzas, etc.).

| Info | Detalhe |
|---|---|
| **Amostras** | 178 |
| **Features** | 13 (propriedades químicas) |
| **Classes** | 3 — `class_0`, `class_1`, `class_2` |
| **Acurácia esperada** | ~96–100% |

---

## 🗂️ Estrutura do Projeto

```
wine_paulo_gabriel/
├── notebook_wine_paulo_gabriel.ipynb   ← notebook principal
└── README.md                           ← este arquivo
```

> Os arquivos gerados ao executar o notebook:
> - `eda_wine.png` — gráfico de exploração dos dados
> - `matriz_confusao_wine.png` — matriz de confusão (absoluta e %)
> - `feature_importance_wine.png` — importância das 13 features

---

## ▶️ Como Rodar

### Opção 1 — Google Colab (recomendado, sem instalar nada)

```
1. Acesse https://colab.research.google.com/
2. Clique em "Arquivo" → "Fazer upload de notebook"
3. Selecione: notebook_wine_paulo_gabriel.ipynb
4. Clique em "Ambiente de execução" → "Executar tudo"  (Ctrl+F9)
5. Aguarde ~1 minuto
6. Os gráficos aparecem inline e são salvos automaticamente
```

### Opção 2 — Execução local (Jupyter / VS Code)

**Pré-requisitos:**
```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost jupyter
```

**Rodar:**
```bash
# Na pasta do projeto:
jupyter notebook notebook_wine_paulo_gabriel.ipynb

# Dentro do Jupyter:
# Clique em "Kernel" → "Restart & Run All"
```

---

## 🔄 Pipeline Executado e Requisitos Atendidos

Abaixo está o detalhamento técnico de cada etapa da esteira de Machine Learning executada no vídeo, descrevendo exatamente como cada requisito prático do trabalho foi implementado:

### 📊 1. Estatísticas Descritivas (Requisito 2)
*   **Seção no Notebook:** `## 3. Exploração dos Dados (EDA)`
*   **O que foi feito:** Apresentação sistemática do formato do dataset (`df.shape`), verificação de tipos de dados, contagem de nulos (`df.isnull().sum()`), proporção de amostras por classe e tabelas de estatísticas descritivas gerais via `df.describe()`.
*   **Gráfico Gerado:** `eda_wine.png` contendo a distribuição visual das classes e o mapa de calor de correlação entre as 13 propriedades químicas.

### ✂️ 2. Transformação em Colunas (Requisito 3)
*   **Seção no Notebook:** `## 4. TRANSFORMAÇÃO EM COLUNAS`
*   **O que foi feito:** Aplicação da normalização **MinMaxScaler** na feature `alcohol` para a escala $0-1$.
*   **Justificativa:** O teor alcoólico possui escalas numéricas diferentes de outros compostos. A normalização garante que todas as variáveis fiquem na mesma escala, melhorando a estabilidade do aprendizado.

### 🧹 3. Transformação em Linhas (Requisito 4)
*   **Seção no Notebook:** `## 5. TRANSFORMAÇÃO EM LINHAS`
*   **O que foi feito:** Detecção e remoção de outliers na coluna `total_phenols` através do método estatístico do **IQR (Interquartile Range)**.
*   **Justificativa:** A exclusão de pontos discrepantes remove ruídos atípicos do dataset, evitando que as árvores de decisão do modelo sofram de overfitting em dados ruidosos.

### 🗂️ 4. Divisão em 3 Subconjuntos (Requisito 5)
*   **Seção no Notebook:** `## 7. Divisão em Treino / Validação / Teste`
*   **O que foi feito:** Divisão estratificada das amostras em **60% para Treinamento**, **20% para Validação** (ajustes) e **20% para Testes** (avaliação cega). A estratificação garante que as proporções das três classes sejam mantidas em todas as partições.

### 🤖 5. Treinamento e Avaliação do Modelo (Requisito 6)
*   **Seção no Notebook:** `## 8. Treinamento do Modelo XGBoost`
*   **O que foi feito:** Treinamento do classificador de alto desempenho **XGBoost** (`XGBClassifier`) configurado com acompanhamento em tempo real das perdas de treino e validação (`eval_set`).

### 📈 6. Matriz de Confusão e Acurácia (Requisito 7)
*   **Seção no Notebook:** `## 9. Avaliação do Modelo`
*   **O que foi feito:** Exibição do relatório de classificação (`classification_report`) e geração do gráfico duplo `matriz_confusao_wine.png` (valores absolutos e percentuais de acerto).
*   **Resultado:** Acurácia final de **96% a 100%** nos conjuntos de validação e teste, comprovando o excelente aprendizado do classificador.

### 🔮 7. Predição do Modelo Implantado (Requisito 8)
*   **Seção no Notebook:** `## 11. PREDIÇÃO DO MODELO IMPLANTADO`
*   **O que foi feito:** Simulação de um ambiente real de produção. O modelo recebe novos registros do conjunto de teste que nunca tinha visto e prediz a classe exata com probabilidade (confiança) de acerto superior a 90%.

---

## 🖼️ Visualizações e Gráficos Gerados

Os gráficos abaixo são gerados na mesma pasta do projeto ao rodar o notebook e servem como auditoria visual dos resultados:

### Análise Exploratória (Distribuição de Classes & Correlação)
![Exploração de Dados](eda_wine.png)

### Matriz de Confusão do Modelo (Métricas)
![Matriz de Confusão](matriz_confusao_wine.png)

### Importância das Propriedades Químicas na Decisão
![Importância das Features](feature_importance_wine.png)

---

## 📦 Bibliotecas Utilizadas

| Biblioteca | Uso no Pipeline |
|---|---|
| `pandas` | Manipulação e limpeza dos dados |
| `numpy` | Operações matemáticas matriciais |
| `matplotlib` | Criação e exportação de gráficos de alta resolução |
| `seaborn` | Visualizações estatísticas avançadas (matriz de correlação e confusão) |
| `scikit-learn` | Divisão estratificada (`train_test_split`), scaler (`MinMaxScaler`) e métricas |
| `xgboost` | Algoritmo principal de classificação (`XGBClassifier`) |

---

## 🏁 Checklist de Requisitos Entregues

Ao final da execução da esteira, o notebook imprime um relatório atestando a conclusão de todos os requisitos do projeto:

*   [x] **1. Dataset Relevante Escolhido** (Wine Recognition UCI)
*   [x] **2. Estatísticas Descritivas e EDA Concluídas**
*   [x] **3. Transformação em Colunas Aplicada** (Normalização MinMax de `alcohol`)
*   [x] **4. Transformação em Linhas Aplicada** (Remoção de Outliers via IQR de `total_phenols`)
*   [x] **5. Divisão em 3 Subconjuntos** (60% Treino / 20% Validação / 20% Teste)
*   [x] **6. Treinamento e Avaliação do Modelo Concluídos**
*   [x] **7. Matriz de Confusão e Acurácia Exportadas**
*   [x] **8. Simulação de Predição de Produção Executada com Sucesso**

---