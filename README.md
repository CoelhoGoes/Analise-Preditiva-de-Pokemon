# Análise Preditiva: Pokémon Catch Rate & Classificação de Lendários

Projeto de Modelagem Estatística e Machine Learning para prever a dificuldade de captura de Pokémons e classificar se um Pokémon é Lendário com base em seus status base. Este projeto utiliza técnicas de Regressão (OLS, Polinomial) e Classificação (Naive Bayes, Regressão Logística) com Python, Scikit-learn, Statsmodels e PyCaret.

**Dataset utilizado:** [Pokémon Database (Kaggle)](https://www.kaggle.com/datasets/mrdew25/pokemon-database)

---

## 🎯 Objetivos do Projeto

O projeto visa responder a duas perguntas de negócio principais utilizando dados históricos de Pokémons:

1.  **Regressão (Target: `CatchRate`):** É possível prever a taxa de captura (dificuldade de capturar) de um Pokémon baseando-se apenas em seus atributos físicos e de combate (HP, Attack, Speed, etc.)?
2.  **Classificação (Target: `is_legendary`):** Conseguimos identificar se um Pokémon é Lendário ou Comum apenas observando seus status base?

## 🛠️ Ferramentas e Bibliotecas

* **Linguagem:** Python 3.x
* **Manipulação de Dados:** Pandas, Numpy
* **Visualização:** Matplotlib, Seaborn
* **Estatística e Inferência:** Statsmodels (OLS, Testes de Normalidade, VIF)
* **Machine Learning:** Scikit-learn (GridSearch, Metrics, Preprocessing)
* **AutoML:** PyCaret (Comparação e Tuning de modelos)

## 📊 Metodologia

1.  **Análise Exploratória (EDA):** Limpeza de dados, tratamento de nulos, engenharia de features (criação da flag `is_legendary`) e análise de correlação.
2.  **Modelagem de Regressão:**
    * Implementação de OLS (Ordinary Least Squares) via `statsmodels` para interpretação dos coeficientes.
    * Diagnóstico de resíduos: Testes de normalidade (Shapiro-Wilk), Homocedasticidade e Multicolinearidade (VIF).
    * Teste de não-linearidade com Regressão Polinomial.
3.  **Modelagem de Classificação:**
    * Definição de Baseline com Naive Bayes.
    * Otimização de Regressão Logística via `GridSearchCV`.
    * Tratamento de desbalanceamento de classes (Lendários são minoria).
4.  **AutoML (Otimização):** Uso do `PyCaret` para comparar diversos algoritmos e validar a performance dos modelos manuais.

## 🚀 Como Executar

1.  Clone este repositório.
2.  Instale as dependências:
    ```bash
    pip install pandas numpy seaborn statsmodels scikit-learn pycaret matplotlib
    ```
3.  Certifique-se de que o arquivo `Pokemon Database.csv` está na raiz do diretório.
4.  Execute o notebook `teste.ipynb` (ou o arquivo `.py` correspondente) em um ambiente Jupyter ou VS Code.

## 📈 Resultados Principais

* **Regressão:** O modelo estatístico confirmou que status mais altos (especialmente HP e Speed) reduzem significativamente a taxa de captura. O modelo polinomial superou o linear, indicando uma relação complexa entre poder e dificuldade de captura.
* **Classificação:** A Regressão Logística otimizada obteve um excelente desempenho na identificação de Lendários, superando o baseline e mantendo um bom equilíbrio entre Precision e Recall.

---
*Projeto desenvolvido para a disciplina de Modelagem Estatística / Machine Learning.*