# Projeto Prático — Web Mining & Crawler Scraping

## Pipeline de Web Scraping para Banco Analítico Financeiro

---

### 📘 Tema
Movimentações da **Berkshire Hathaway** e o impacto das decisões de **Warren Buffett** no mercado financeiro.

O projeto desenvolve um pipeline de **coleta, transformação e carga (ETL)** para análise das movimentações de portfólio da Berkshire Hathaway, observando como essas decisões influenciam o comportamento do mercado. Warren Buffett é reconhecido mundialmente por suas decisões de investimento, tornando o estudo dessas movimentações altamente relevante para análise financeira.

---

## 🧠 Objetivo Geral

Construir um **pipeline ETL completo** que:

- Coleta dados de **três fontes distintas** (duas via scraping e uma via API);
- Realiza o tratamento e padronização dos dados obtidos;
- Gera arquivos estruturados no formato **Parquet**, simulando um **banco analítico local**;
- Permite exploração futura em **SQL** e **dashboards analíticos**.

---

## ⚙️ Ferramentas e Tecnologias Utilizadas

- **Linguagem:** Python 3.9+
- **Ambiente de desenvolvimento:** VSCode com Jupyter Notebook (`.ipynb`)
- **Bibliotecas principais:**
  - `requests` e `BeautifulSoup` — Web Scraping
  - `selenium` — scraping dinâmico (quando necessário)
  - `pandas` e `pyarrow` — manipulação e exportação de dados
  - `datetime` e `os` — controle de execução e organização de arquivos
- **Formato de saída dos dados:** `.parquet`

---

## 🧩 Estrutura Geral do Pipeline ETL

1. **Coleta de Dados**
   - **1.1 Séries históricas via API** (*Alpha Vantage*);
   - **1.2 Movimentações da Berkshire Hathaway** (Web Scraping);
   - **1.3 Notícias sobre Warren Buffett e empresas relacionadas** (Web Scraping).

2. **Transformação de Dados**
   - Limpeza, padronização, deduplicação e ajustes de tipos.

3. **Carga de Dados**
   - Exportação dos resultados tratados para arquivos `.parquet`.

---

## 📝 Como Executar

1. Clone o repositório:
```bash
git clone https://github.com/seu-usuario/seu-repositorio.git
```

2. Configure sua API Key (Alpha Vantage) no arquivo .env:
   ALPHA_VANTAGE_API_KEY=your_api_key_here

3. Execute os notebooks

## 📂 Estrutura de Pastas
```bash
/project-root
│
├── data/           # Arquivos brutos e processados (.parquet)
├── notebooks/      # Jupyter notebooks de análise e testes
├── src/            # Scripts e módulos Python
├── logs/           # Logs de execução (ignorado pelo git)
├── .gitignore      # Arquivos/pastas a serem ignorados
└── README.md
```

##⚠️ Observações Importantes
- *Chaves API* nunca devem ser commitadas. Use ```.env``` para manter seguras.
- *Logs e arquivos temporários* estão incluídos no ```.gitignore```.
- Este projeto é um exercício prático de Web Mining e ETL, ideal para aprendizado e análise exploratória.

##💡 Possíveis Extensões Futuras
- Integração com dashboards em *Power BI* ou *Tableau*.
- Automatização completa com *Airflow* ou *Prefect*.
- Adição de mais fontes de notícias financeiras e análise de sentimento.
