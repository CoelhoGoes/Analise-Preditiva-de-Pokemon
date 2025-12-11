# 🎮 Análise Preditiva de Atributos e Raridade de Pokémon

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

## 📋 Sobre o Projeto

Este projeto acadêmico realiza uma **análise preditiva completa** sobre dados de Pokémon, utilizando técnicas de Machine Learning para resolver dois problemas principais:

1. **Regressão**: Prever a **Taxa de Captura (Catch Rate)** de um Pokémon com base em seus atributos de combate
2. **Classificação Multiclasse**: Identificar o **Grupo de Raridade** de um Pokémon (Legendary, Starter, Mythical, Paradox, Pseudo-Legendary, Ultra Beast)

O projeto demonstra a aplicação prática de técnicas estatísticas e algoritmos de Machine Learning em um dataset real, seguindo metodologias científicas rigorosas de análise de dados.

---

## 🎯 Problema e Solução

### Problema

- **Desafio 1**: Como prever a dificuldade de captura de um Pokémon baseado apenas em seus stats?
- **Desafio 2**: É possível classificar automaticamente um Pokémon em seu grupo de raridade usando apenas atributos numéricos?

### Solução Implementada

Desenvolvimento de modelos preditivos utilizando:

- **Regressão Linear (OLS)** e **Regressão Polinomial** para prever valores contínuos
- **Random Forest Classifier** com balanceamento de classes para classificação multiclasse
- **Análise estatística completa**: VIF, testes de normalidade, ANOVA, diagnóstico de resíduos
- **AutoML com PyCaret** para otimização automática de hiperparâmetros

---

## 📊 Fonte dos Dados

**Dataset**: [The Complete Pokemon Dataset - Kaggle](https://www.kaggle.com/datasets/rounakbanik/pokemon)

- **Fonte**: Dataset público disponibilizado por Rounaki Banik no Kaggle
- **Tamanho**: 1.199 registros de Pokémon (após limpeza)
- **Features**: 27 atributos incluindo stats de combate, tipos, habilidades, grupos de raridade
- **Período**: Pokémon das gerações 1 a 9

**Citação**:

```text
Banik, R. (2023). The Complete Pokemon Dataset. Kaggle. 
https://www.kaggle.com/datasets/rounakbanik/pokemon
```

---

## 🔬 Metodologia

### 1. **Limpeza e Pré-processamento** (`limpeza.ipynb`)

- Remoção de aspas extras em colunas textuais
- Tratamento de valores nulos (imputação e remoção estratégica)
- Padronização de nomes de colunas
- Criação do arquivo limpo: `pokemon_dataset_cleaned.csv`

### 2. **Feature Engineering**

- Seleção de features numéricas: `HP`, `Attack`, `Defense`, `SpAtk`, `SpDef`, `Speed`, `Height`, `Weight`
- Codificação de variáveis categóricas com `LabelEncoder`
- Normalização com `StandardScaler`
- Cálculo de `Base Stat Total (BST)` para análises adicionais

### 3. **Análise Exploratória de Dados (EDA)** (`analise.ipynb`)

- Estatísticas descritivas por grupo de raridade
- Visualizações: distribuições, boxplots, heatmaps de correlação
- Testes estatísticos: ANOVA, Teste T, Teste de Normalidade (Shapiro-Wilk)
- Identificação de padrões e outliers

### 4. **Modelagem de Regressão** (`modelagem.ipynb`)

- **Ordinary Least Squares (OLS)**: Modelo baseline com análise completa
  - Diagnóstico de multicolinearidade (VIF)
  - Análise de resíduos (homocedasticidade e normalidade)
  - Métricas: MAE, RMSE, R²
- **Regressão Polinomial (grau 2)**: Captura de relações não-lineares
- **Comparação de modelos**: Seleção do melhor desempenho

### 5. **Modelagem de Classificação Multiclasse** (`modelagem.ipynb`)

- **Random Forest Classifier**:
  - 200 árvores de decisão
  - Balanceamento automático de classes (`class_weight='balanced'`)
  - Divisão estratificada (80% treino, 20% teste)
- **Avaliação**:
  - Classification Report por grupo
  - Matriz de Confusão visual
  - Análise de Feature Importance

### 6. **Otimização com AutoML**

- **PyCaret**: Comparação automática de 15+ algoritmos
- Tuning de hiperparâmetros com Grid Search
- Seleção do modelo com melhor F1-Score

---

## 📈 Resultados Chave

### Regressão (Prever Catch Rate)

- **R² (OLS)**: `[PLACEHOLDER - Adicionar valor após execução]`
- **R² (Polinomial)**: `[PLACEHOLDER - Adicionar valor após execução]`
- **RMSE**: `[PLACEHOLDER - Adicionar valor após execução]`
- **Interpretação**: Modelos explicam aproximadamente XX% da variação na dificuldade de captura

### Classificação Multiclasse (Prever Group)

- **Acurácia (Random Forest)**: `[PLACEHOLDER - Adicionar valor após execução]`
- **F1-Score Macro**: `[PLACEHOLDER - Adicionar valor após execução]`
- **Melhor modelo PyCaret**: `[PLACEHOLDER - Adicionar nome do modelo]`

**Insights**:

- Stats mais importantes: `[PLACEHOLDER - Ex: Attack, BST, Speed]`
- Grupos mais difíceis de classificar: `[PLACEHOLDER - Ex: Mythical vs Legendary]`

---

## 📁 Estrutura do Repositório

```text
Analise-Preditiva-de-Pokemon/
│
├── 📓 limpeza.ipynb              # Notebook de limpeza e pré-processamento
├── 📓 análise.ipynb      # Notebook de análise exploratória completa
├── 📓 modelagem.ipynb            # Notebook de modelagem preditiva
│
├── 📊 Pokemon Database.csv       # Dataset original (bruto)
├── 📊 pokemon_dataset_cleaned.csv # Dataset limpo (pronto para modelagem)
│
├── 📄 README.md                  # Documentação do projeto (este arquivo)
├── 📄 requirements.txt           # Dependências do projeto
├── 📄 .gitignore                 # Arquivos ignorados pelo Git
│
└── 📁 .git/                      # Controle de versão Git
```

---

## 🚀 Como Executar

### Pré-requisitos

- Python 3.8 ou superior
- pip (gerenciador de pacotes Python)
- Git (opcional, para clonar o repositório)

### Passo 1: Clonar o Repositório

```bash
git clone https://github.com/CoelhoGoes/Analise-Preditiva-de-Pokemon.git
cd Analise-Preditiva-de-Pokemon
```

### Passo 2: Criar Ambiente Virtual (Recomendado)

```bash
# Windows
python -m venv venv
venv\Scripts\activate

# Linux/Mac
python3 -m venv venv
source venv/bin/activate
```

### Passo 3: Instalar Dependências

```bash
pip install -r requirements.txt
```

### Passo 4: Iniciar Jupyter Notebook

```bash
jupyter notebook
```

### Passo 5: Executar os Notebooks na Ordem

1. **`limpeza.ipynb`**: Gera o arquivo `pokemon_dataset_cleaned.csv`
2. **`modelagem.ipynb`**: Análise exploratória detalhada e Modelos preditivos

> **Nota**: Execute as células sequencialmente (Shift + Enter) para reproduzir os resultados.

---

## 🛠️ Tecnologias Utilizadas

- **Linguagem**: Python 3.8+
- **Manipulação de Dados**: pandas, numpy
- **Visualização**: matplotlib, seaborn
- **Machine Learning**: scikit-learn, statsmodels, scipy
- **AutoML**: PyCaret
- **Ambiente**: Jupyter Notebook

---

## 📚 Referências e Recursos

1. **Dataset Original**: [The Complete Pokemon Dataset - Kaggle](https://www.kaggle.com/datasets/rounakbanik/pokemon)
2. **Documentação Scikit-Learn**: [https://scikit-learn.org/](https://scikit-learn.org/)
3. **Documentação PyCaret**: [https://pycaret.org/](https://pycaret.org/)
4. **Statsmodels Documentation**: [https://www.statsmodels.org/](https://www.statsmodels.org/)

---

## 📝 Licença

Este projeto foi desenvolvido para fins **acadêmicos e educacionais**.

- **Dataset**: Disponibilizado sob licença pública no Kaggle
- **Código**: Livre para uso educacional com atribuição adequada

---

## 👥 Autores

### Gabriel Góes

- GitHub: [@CoelhoGoes](https://github.com/CoelhoGoes)

### Cauê Barroso

- GitHub: [@cauebarroso](https://github.com/cauebarroso)

**Instituição**: [Centro Universitário do Pará(Cesupa)]  
**Curso**: [Bacharelado em Ciência da Computação]  
**Disciplina**: [Modelagem Estatística]  
**Ano**: 2025

---
