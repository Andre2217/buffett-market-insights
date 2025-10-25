# 🧠 Projeto Prático — Web Mining & Crawler Scraping

## Pipeline Analítico sobre o Portfólio da Berkshire Hathaway

---

### 📘 Tema
Análise das **movimentações de portfólio da Berkshire Hathaway** e do impacto das decisões de **Warren Buffett** no mercado financeiro.

O projeto desenvolve um pipeline completo de **coleta, transformação, carga e análise (ETL + EDA)** de dados obtidos via **Web Scraping** e **API**, permitindo explorar o comportamento dos investimentos da Berkshire e identificar tendências nas decisões de alocação de capital.

---

## 🎯 Objetivo Geral

Construir um **pipeline ETL analítico completo** que:

- Coleta dados de **três fontes distintas** (duas via scraping e uma via API);
- Realiza o **tratamento, limpeza e padronização** dos dados obtidos;
- Gera arquivos estruturados em formato **Parquet**, simulando um **banco analítico local**;
- Permite análises financeiras e textuais com **Python e Jupyter Notebook**.

---

## ⚙️ Tecnologias e Ferramentas Utilizadas

- **Linguagem:** Python 3.9+
- **Ambiente:** VSCode com Jupyter Notebook (`.ipynb`)
- **Principais bibliotecas:**
  - `requests`, `BeautifulSoup`, `selenium` — Web Scraping
  - `pandas`, `numpy`, `pyarrow` — manipulação e armazenamento de dados
  - `matplotlib`, `seaborn` — visualização de dados
  - `nltk`, `re`, `collections.Counter` — processamento de texto (análises de notícias)
  - `dotenv` — gerenciamento de variáveis sensíveis (API Keys)

- **Formato dos dados tratados:** `.parquet`  
- **Saídas geradas:** `.csv` (tabelas) e `.png` (gráficos)

---

## 🧩 Estrutura do Pipeline ETL

### 1. Coleta de Dados
- **1.1 Séries históricas de preços** via API (*Alpha Vantage*).  
- **1.2 Movimentações do portfólio da Berkshire Hathaway** via Web Scraping.  
- **1.3 Notícias e manchetes sobre Warren Buffett e empresas relacionadas** via Web Scraping.

### 2. Transformação
- Limpeza de dados, remoção de duplicidades, tratamento de colunas e padronização de formatos.

### 3. Carga
- Exportação dos dados tratados para arquivos `.parquet` na pasta `data_clean/`.

### 4. Análise
- Análises exploratórias e visuais realizadas no notebook `AnaliseDadosWarrenBuffett.ipynb`.

---

## 📊 Notebook de Análise de Dados

O notebook **`AnaliseDadosWarrenBuffett.ipynb`** contém as análises exploratórias realizadas a partir dos dados consolidados no pipeline ETL.  
Ele gera gráficos e tabelas salvos automaticamente em `outputs/outputsAnalise/`.

### Principais análises realizadas:
1. **Volume médio diário por empresa**  
2. **Evolução dos preços de fechamento ao longo do tempo**  
3. **Top 10 posições mais valiosas do portfólio**  
4. **Diferença percentual entre portfólio atual e anterior**  
5. **Distribuição das variações percentuais das posições**  
6. **Ações com maior frequência de mudanças**  
7. **Palavras mais frequentes nos títulos das notícias**  
8. **Quantidade de notícias por termo pesquisado**

### Saídas geradas automaticamente:
- 📈 Gráficos: `outputs/outputsAnalise/graficos/`  
- 📋 Tabelas: `outputs/outputsAnalise/tabelas/`  

Cada análise é documentada dentro do notebook com explicações e objetivos em markdown.

---

## 🧾 Arquivo `requirements.txt`

O arquivo **`requirements.txt`** lista todas as dependências do projeto, garantindo reprodutibilidade.  
Para instalar:

```bash
pip install -r requirements.txt
```

Exemplo de dependências incluídas:
`
pandas
numpy
matplotlib
seaborn
requests
beautifulsoup4
selenium
pyarrow
nltk
python-dotenv
`

## 🚀 Como Executar o Projeto

### 1. Clone o repositório:
   `git clone https://github.com/seu-usuario/seu-repositorio.git`
### 2. Configure sua chave da API Alpha Vantage:
Crie um arquivo .env na raiz do projeto e adicione:
  `ALPHA_VANTAGE_API_KEY=your_api_key_here`
### 3. Execute os notebooks na ordem:
  - `ColetaDadosWarrenBuffett.ipynb`
  - `AnaliseDadosWarrenBuffett.ipynb`

## 📂 Estrutura de Pastas
`
/project-root
│
├── data_raw/           # Dados brutos coletados
├── data_clean/         # Dados tratados e padronizados (.parquet)
├── logs/               # Registros de execução
├── outputs/
│   └── outputsAnalise/
│       ├── tabelas/    # Tabelas CSV das análises
│       └── graficos/   # Gráficos gerados (.png)
│
├── ColetaDadosWarrenBuffett.ipynb       # Pipeline de coleta e tratamento
├── AnaliseDadosWarrenBuffett.ipynb      # Notebook de análise exploratória
├── requirements.txt                     # Dependências do projeto
├── .gitignore
└── README.md
`
## ⚠️ Boas Práticas e Observações

  - 🔐 Nunca compartilhe chaves de API ou credenciais no código.

  - 🧹 Os diretórios logs/ e outputs/ estão no .gitignore para evitar arquivos locais no versionamento.

  - 🧠 O projeto foi desenvolvido com fins educacionais e analíticos, simulando um pipeline real de Web Mining.

## 💡 Possíveis Extensões Futuras

  - Integração com Power BI ou Tableau para dashboards interativos.

  - Implementação de análise de sentimento nas notícias usando NLP.

  - Inclusão de novas fontes de dados (ex: Yahoo Finance, CNBC, Bloomberg).

  - Construção de um pipeline automatizado com Airflow, Prefect ou Dagster.

  - Criação de um banco de dados SQL Server ou DuckDB para consultas analíticas.

  - Modelos de correlação entre movimentações de portfólio e desempenho das ações.

  - Análise temporal de notícias para identificar reação do mercado às decisões da Berkshire.

  - Painel web com Streamlit para visualização interativa dos resultados.

## 🏁 Conclusão

Este projeto demonstra o ciclo completo de um pipeline analítico em Python, desde a coleta automatizada de dados até a análise exploratória e visualização.
Ele serve como base sólida para estudos em engenharia de dados, web scraping, análise financeira e NLP — podendo ser facilmente expandido para aplicações reais de monitoramento de portfólio e notícias de mercado.
