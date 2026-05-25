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

## 🔄 Pipeline Executado

```
Etapa 1  →  Instalação das bibliotecas
Etapa 2  →  Importações
Etapa 3  →  Carregamento dos dados (sklearn — sem download)
Etapa 4  →  Exploração (EDA): shape, describe, nulos, distribuição
Etapa 5  →  Visualizações EDA: distribuição de classes + mapa de correlação
Etapa 6  →  Limpeza: duplicatas e valores nulos
Etapa 7  →  Separação X (features) e y (alvo)
Etapa 8  →  Divisão: 60% Treino | 20% Validação | 20% Teste
Etapa 9  →  Treinamento XGBClassifier
Etapa 10 →  Avaliação no conjunto de Validação
Etapa 11 →  Avaliação no conjunto de Teste
Etapa 12 →  Matriz de Confusão (absoluta e percentual)
Etapa 13 →  Importância das Features (13 propriedades químicas)
Etapa 14 →  Resumo final
```

---

## 📦 Bibliotecas

| Biblioteca | Uso |
|---|---|
| `pandas` | Manipulação dos dados |
| `numpy` | Operações numéricas |
| `matplotlib` | Geração de gráficos |
| `seaborn` | Visualizações estatísticas |
| `scikit-learn` | Dataset, divisão e métricas |
| `xgboost` | Modelo de classificação |

---

## 📊 Resultados Esperados

```
Acurácia Validação : ~96–100%
Acurácia Teste     : ~96–100%

Classes classificadas:
  class_0 → tipo 0 de vinho
  class_1 → tipo 1 de vinho
  class_2 → tipo 2 de vinho
```

---

## 📬 Contato

**Paulo Gabriel Alves Dos Santos**
