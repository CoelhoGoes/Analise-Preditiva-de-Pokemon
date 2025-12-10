# 📊 Análise Preditiva de Pokémon: Catch Rate & Agrupamento

![Python](https://img.shields.io/badge/Python-3.x-blue?style=for-the-badge&logo=python)
![Status](https://img.shields.io/badge/Status-Concluído-green?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)

Este projeto aplica técnicas avançadas de **Estatística** e **Machine Learning** para analisar dados de Pokémon. O objetivo é prever a dificuldade de captura (`CatchRate`) e classificar os Pokémon em seus respectivos grupos (Lendários, Míticos, Iniciais, etc.) com base em seus atributos de combate.

---

## 🗂️ Estrutura do Repositório

A organização do projeto segue a seguinte estrutura:

```text
📁 Pokemon-Analytics/
│
├── 📓 análise pokemon.ipynb       # Notebook de EDA (Limpeza, Visualização e Testes Estatísticos)
├── 📓 modelagem.ipynb             # Notebook de Machine Learning (Regressão, Classificação e AutoML)
├── 📄 requirements.txt            # Lista de dependências para reprodução do ambiente
├── 💾 Pokemon Database.csv        # Dataset original (Fonte: Kaggle)
├── 💾 pokemon_dataset_cleaned.csv # Dataset processado e limpo
├── 📝 logs.log                    # Logs de execução do PyCaret
└── 📜 README.md                   # Documentação do projeto
🎯 Objetivos do Projeto
Regressão (Target: CatchRate): Prever a taxa de captura de um Pokémon utilizando seus status base (HP, Attack, Speed, etc.). Investigar se a relação entre poder e captura é linear ou não-linear.

Classificação Multiclasse (Target: Group): Identificar corretamente a categoria do Pokémon (Legendary, Starter, Ultra Beast, Paradox, etc.) com base em seus atributos numéricos.

🛠️ Ferramentas Utilizadas
Linguagem: Python 3

Manipulação de Dados: Pandas, Numpy

Visualização: Seaborn, Matplotlib

Estatística: Scipy (Testes de Hipótese), Statsmodels (OLS, Diagnóstico de Resíduos)

Machine Learning: Scikit-learn (Pipelines, GridSearch, Random Forest)

AutoML: PyCaret (Seleção e Tuning automático de modelos)

📊 Metodologia Aplicada
O projeto foi dividido em duas grandes etapas:

1. Análise Exploratória (EDA)
Limpeza rigorosa de dados (tratamento de formas regionais e nulos).

Análise univariada e bivariada (histogramas, boxplots, correlações).

Testes Estatísticos: Aplicação de ANOVA para validar diferenças significativas de status entre os grupos de Pokémon.

2. Modelagem Preditiva
Regressão:

Baseline com OLS (Ordinary Least Squares) e interpretação de coeficientes/p-valores.

Diagnóstico de resíduos (Normalidade e Homocedasticidade).

Comparação com Regressão Polinomial para capturar complexidade.

Classificação:

Implementação de Random Forest Classifier com balanceamento de classes.

Otimização de hiperparâmetros via GridSearchCV (Scikit-Learn).

Avaliação com métricas robustas (F1-Score, Precision, Recall por classe).

AutoML:

Uso do PyCaret para validar a performance dos modelos manuais através de comparação massiva de algoritmos.

🚀 Instalação e Execução
Para reproduzir este projeto localmente, siga os passos abaixo:

Clone o repositório:

Bash

git clone [https://github.com/seu-usuario/seu-repo.git](https://github.com/seu-usuario/seu-repo.git)
cd seu-repo
Instale as dependências: Certifique-se de ter o Python instalado e execute:

Bash

pip install -r requirements.txt
Execute os Notebooks: Abra os arquivos no Jupyter Notebook ou VS Code na seguinte ordem:

análise pokemon.ipynb (Gera o dataset limpo)

modelagem.ipynb (Treina os modelos)

📈 Resultados Principais
Regressão: O modelo linear explicou a relação entre status e taxa de captura de forma satisfatória. A Regressão Polinomial não apresentou ganhos significativos, indicando que a complexidade adicional não era necessária (Navalha de Ockham).

Classificação: O modelo Random Forest otimizado foi capaz de distinguir com alta precisão grupos complexos como Legendaries e Starters, superando modelos lineares simples. A otimização via GridSearch refinou a capacidade de generalização do modelo.

📝 Licença e Créditos
Este projeto está licenciado sob a licença MIT - sinta-se à vontade para usar e modificar.

Fonte dos Dados: O dataset original foi obtido no Kaggle: Pokémon Database.

Projeto desenvolvido para a disciplina de Modelagem Estatística / Machine Learning.
