# 📊 Predição de Inadimplência com Machine Learning

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-App-red?logo=streamlit&logoColor=white)
![LightGBM](https://img.shields.io/badge/Model-LightGBM-green)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-orange?logo=scikitlearn&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Container-blue?logo=docker&logoColor=white)
![Cloud](https://img.shields.io/badge/Deploy-Streamlit%20Cloud-brightgreen)
![License](https://img.shields.io/badge/License-MIT-yellow)
![GitHub repo size](https://img.shields.io/github/repo-size/RafaelGallo/deploy_case_ml_koin)
![GitHub last commit](https://img.shields.io/github/last-commit/RafaelGallo/deploy_case_ml_koin)
![GitHub stars](https://img.shields.io/github/stars/RafaelGallo/deploy_case_ml_koin?style=social)
![Status](https://img.shields.io/badge/Status-Em%20Produção-success)
![Maintainer](https://img.shields.io/badge/Maintainer-Rafael%20Gallo-blueviolet)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-purple?logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-Scientific-blue?logo=numpy&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-green)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-lightblue)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-orange?logo=scikitlearn&logoColor=white)
![LightGBM](https://img.shields.io/badge/LightGBM-Boosting-brightgreen)
![Imbalanced-Learn](https://img.shields.io/badge/Imbalanced--Learn-SMOTE-red)
![SQL](https://img.shields.io/badge/SQL-Database-blue?logo=postgresql&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-Database-lightgrey?logo=sqlite&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-App-red?logo=streamlit&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Container-blue?logo=docker&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-Version%20Control-black?logo=github&logoColor=white)

<p align="center">
  <img src="https://raw.githubusercontent.com/docker-library/docs/master/docker/logo.png" width="120"/>
  &nbsp;&nbsp;&nbsp;
  <img src="https://streamlit.io/images/brand/streamlit-logo-primary-colormark-darktext.png" width="160"/>
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/RafaelGallo/deploy_case_ml_koin/main/img/log0.jpg" width="800"/>
</p>

## Visão Geral

Este projeto implementa um sistema completo de **predição de inadimplência de clientes** utilizando Machine Learning.  
O pipeline contempla:

- ETL e tratamento de dados
- Análise exploratória
- Treinamento e tuning de modelos
- Avaliação com métricas (Accuracy, Recall, F1-score, ROC AUC)
- Deploy em aplicação web com Streamlit
- Conteinerização com Docker
- Disponibilização em nuvem (Streamlit Cloud)

A aplicação permite inserir dados de um cliente e obter a **probabilidade de inadimplência em tempo real**.

## Objetivo do Projeto

Construir um modelo capaz de estimar o risco de inadimplência de um cliente com base em variáveis socioeconômicas e comportamentais, auxiliando decisões de crédito.

## Arquitetura da Solução

```

ETL → Modelagem → Avaliação → Deploy (Streamlit) → Docker → Streamlit Cloud

```

Fluxo:
1. Base de dados tratada via script ETL
2. Modelo treinado com LightGBM
3. Modelo salvo em arquivo `.pkl`
4. Aplicação Streamlit carrega o modelo
5. Usuário insere dados
6. Sistema retorna probabilidade de inadimplência

## Modelo de Machine Learning

- Algoritmo principal: **LightGBM**
- Balanceamento de classes: **SMOTE (imbalanced-learn)**
- Métricas utilizadas:
  - Accuracy
  - Recall (classe inadimplente)
  - F1-score
  - ROC AUC
- Ajuste de threshold para melhor sensibilidade ao risco

## Tecnologias Utilizadas

- Python 3.10
- Pandas, NumPy
- Scikit-learn
- LightGBM
- Imbalanced-learn (SMOTE)
- Streamlit
- Docker
- SQLite (opcional para logs)
- GitHub
- Streamlit Community Cloud

## Aplicação em Produção

A aplicação está disponível em:

https://aplicacao-modelo-ml-credito.streamlit.app/

Funcionalidades:
- Entrada interativa dos dados do cliente
- Exibição da probabilidade de inadimplência
- Interpretação do risco (baixo, médio ou alto)
- Visualização dos dados informados
- Registro de histórico das previsões

## Demonstração da Aplicação

<p align="center">
  <img src="https://raw.githubusercontent.com/RafaelGallo/deploy_case_ml_koin/main/img/15_deploy.png" width="800"/>
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/RafaelGallo/deploy_case_ml_koin/main/img/16_deploy.png" width="800"/>
</p>

## Estrutura do Projeto

```

Case_tecnico_Koin/
│
├── app.py
├── requirements.txt
├── packages.txt
├── models/
│   └── modelo_turing/
│       └── modelo_tuned_lightgbm_kfold.pkl
├── data/
├── notebooks/
├── Dockerfile
├── README.md
└── .gitignore

````

## Como Executar Localmente

### 1. Clone o repositório
```bash
git clone https://github.com/seu_usuario/seu_repositorio.git
cd seu_repositorio
````

### 2. Crie ambiente virtual

```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate     # Windows
```

### 3. Instale dependências

```bash
pip install -r requirements.txt
```

### 4. Execute a aplicação

```bash
streamlit run app.py
```

Acesse:

```
http://localhost:8501
```

## Executar com Docker

### Build da imagem:

```bash
docker build -t case-koin-app .
```

### Rodar o container:

```bash
docker run -p 8501:8501 case-koin-app
```

Acesse:

```
http://localhost:8501
```

## Exemplo de Uso

1. Preencha os dados do cliente (idade, renda, score, histórico, etc.)
2. Clique em **Prever risco de inadimplência**
3. O sistema retorna:

   * Probabilidade (%)
   * Classificação do risco (baixo / médio / alto)

## Resultados

O modelo obteve desempenho satisfatório na base de validação, com foco em maximizar o Recall da classe inadimplente, reduzindo falsos negativos (clientes de risco classificados como bons).

## Boas Práticas Aplicadas

* Separação entre treino e inferência
* Versionamento do modelo
* Dockerização da aplicação
* Deploy em nuvem
* Interface amigável para usuário final
* Logging de previsões
* Organização em pipeline (ETL → ML → Deploy)

## Próximas Melhorias

* Explicabilidade do modelo (SHAP)
* Dashboard de monitoramento
* Armazenamento em banco SQL das previsões
* Autenticação de usuários
* API REST (FastAPI)
* Monitoramento de drift de dados

## Autor

Projeto desenvolvido por **Rafael Gallo**
Cientista de Dados

LinkedIn: (adicione seu link)
GitHub: [https://github.com/RafaelGallo](https://github.com/RafaelGallo)

## Licença

Este projeto está sob licença MIT. Consulte o arquivo LICENSE para mais detalhes.

