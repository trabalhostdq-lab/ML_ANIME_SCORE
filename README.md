## Anime Popularity Prediction

##  Objetivo
Este projeto tem como objetivo prever a popularidade de anime com base em características estruturais e dados do material original.

---

##  Dados
- Fonte: API Jikan (MyAnimeList)
- Período: 2016 até 2025
- Tipos:
  - TV
  - Manga
  - Light Novel
  - Original

---

##  Processo

### 1. Coleta de Dados
- Uso da API Jikan
- Filtros aplicados:
  - Tipo: TV
  - Ano: 2016–2025

### 2. Tratamento
- Remoção de valores nulos
- Criação de variáveis auxiliares
- Tratamento de categorias

### 3. Feature Engineering
- One-Hot Encoding (gêneros, estúdio, source)
- Criação de:
  - `members_log`
  - `Engajamento_log`
  - `score_missing`

### 4. Modelagem
Modelos utilizados:
- Random Forest Regressor
- XGBoost Regressor

Comparações realizadas:
- Modelo COM dados do material original
- Modelo SEM dados do material original

### 5. Validação
- Train/Test Split
- Cross Validation (5 folds)
- Grid Search para otimização

---

##  Resultados

| Modelo | R² |
|------|----|
| RandomForest (com original) | ~0.64 |
| RandomForest (sem original) | ~0.56 |
| XGBoost (com original) | ~0.71 |
| XGBoost (sem original) | ~0.63 |

---

##  Principais Insights

- Dados do material original impactam fortemente a popularidade
- O modelo tende a usar "atalhos" como:
  - `MembrosOriginal`
  - `source_Original`
- Existe limitação de performance (~0.7 R²) com as features atuais
- Muitos estúdios de elite como CloverWorks, J.C.Staff, e TMS Entertainment não apresentaram diferenças significativas entre si, o que indica que eles competem em um nivel de popularidade semelhante

---

##  Próximos Passos

- Adicionar novas features:
  - Número de episódios
  - Duração
  - Season
  - Força do estúdio
- Reduzir dependência de variáveis dominantes
- Melhorar generalização

