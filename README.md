```markdown
# Projeto Fecomércio: Hub do Comércio

## Introdução
O **Projeto Fecomércio** visa desenvolver um ambiente centralizado para coleta, processamento e visualização de dados com o objetivo de auxiliar na tomada de decisões estratégicas no setor comercial de Pernambuco. Este projeto utiliza tecnologias de Big Data e dashboards interativos para consolidar dados de diversas fontes, incluindo IBGE, Banco Central e Comexstat, oferecendo insights valiosos para empresas do setor.

## Objetivo
Criar um repositório centralizado que integre dados heterogêneos e permita análises detalhadas para aumentar a competitividade do setor comercial pernambucano. O projeto é parte do desenvolvimento do MVP 1.0 do **Hub do Comércio**, que oferece funcionalidades de análise e consultoria baseadas em dados consolidados.

---

## Tabela de Conteúdos
1. [Funcionalidades](#funcionalidades)
2. [Arquitetura do Projeto](#arquitetura-do-projeto)
3. [Dados Utilizados](#dados-utilizados)
   - IBGE
   - Banco Central
   - Comexstat
4. [Processo ETL](#processo-etl)
5. [Visualizações e Dashboards](#visualizações-e-dashboards)
6. [Instalação e Configuração](#instalação-e-configuração)
7. [Requisitos](#requisitos)
8. [Contribuidores](#contribuidores)
9. [Licença](#licença)

---

## Funcionalidades
- **Coleta e Integração de Dados**: Dados de fontes externas, como IBGE, Banco Central e Comexstat.
- **Armazenamento Centralizado**: Repositório no MongoDB (Atlas).
- **Visualizações Interativas**: Dashboards desenvolvidos no Power BI.
- **Consultoria Baseada em Dados**: Relatórios e insights para tomadas de decisão.

---

## Arquitetura do Projeto

### Estrutura de Diretórios
```
PROJETO-FECOMERCIO/
├── src/
│   ├── apis/
│   │   ├── banco_central/
│   │   │   ├── boletim_focus/
│   │   │   │   ├── exp_mercado_anuais.ipynb
│   │   │   │   ├── exp_mercado_mensais.ipynb
│   │   │   │   ├── exp_mercado_trimestrais.ipynb
│   │   │   ├── cambio/
│   │   │   │   ├── dolar_em_determinada_data.ipynb
│   │   │   │   ├── dolar_por_periodo.ipynb
│   │   │   ├── meios_pagamentos/
│   │   │   │   ├── estoque_e_transacoes_cartoes.ipynb
│   │   │   │   ├── meios_pagamentos_mensais.ipynb
│   │   │   │   ├── meios_pagamentos_trimestrais.ipynb
│   │   │   ├── pix/
│   │   │   │   ├── estatisticas_transacoes_pix.ipynb
│   │   │   │   ├── transacao_pix_municipio.ipynb
│   │   ├── comexstat/
│   │   │   ├── comextat.ipynb
│   │   │   ├── exportacao_cidades_comextat.ipynb
│   │   │   ├── exportacao_estados_comextat.ipynb
│   │   │   ├── importacao_cidades_comextat.ipynb
│   │   │   ├── importacao_estados_comextat.ipynb
│   │   ├── ibge/
│   │       ├── desemprego.ipynb
│   │       ├── inpc.ipynb
│   │       ├── pesquisa_mensal_servicos.ipynb
│   │       ├── pesquisa_industrial_mensal.ipynb
│   │       ├── pesquisa_mensal_comercio.ipynb
├── assets/
│   ├── prints_process/
│   │   ├── 1st_model_dash.png
│   │   ├── 2nd_model_dash.png
│   │   ├── bd_details.png
│   │   ├── data_details.png
│   │   ├── mongo_atlassql.png
│   │   ├── mongo_details.png
│   ├── visualizations/
│   │   ├── overview_final_dash.png
│   │   ├── pim_final_dash.png
│   │   ├── pms_final_dash.png
│   ├── dashboards/
│       ├── ProjetoFecomercio.pbix
│   ├── data/
│       ├── exportacao_cidades_comextat.csv
│       ├── exportacao_estados_comextat.csv
│       ├── importacao_cidades_comextat.csv
│       ├── importacao_estados_comextat.csv
│       ├── pesquisa_industrial.csv
│       ├── pesquisa_servicos.csv
├── docs/
│   ├── Projeto DS.pdf
│   ├── Projeto Fecomércio.pdf
│   ├── Temas da Apresentação.pdf
├── processing/
│       ├── csv_data_process.ipynb
│       ├── pms_pim_services.ipynb
.gitattributes
README.md
```

### Tecnologias
- **Linguagem**: Python
- **Banco de Dados**: MongoDB (Atlas)
- **Visualização**: Power BI
- **APIs Utilizadas**: IBGE, Banco Central, Comexstat

---

## Dados Utilizados

### IBGE
1. **Pesquisa Mensal de Serviços (8163)**:
   - Variáveis: Número índice, acumulado ano, mês, ano, categorias (todas).
2. **Pesquisa Industrial Mensal (8885)**:
   - Variáveis: Número índice, acumulado ano, mês, ano, categorias (todas).
3. **INPC**:
   - Variáveis: Grupo, subgrupo, item, subitem, variação anual, acumulado ano, mês, ano.
4. **Desemprego**:
   - Dados compartilhados.

### Banco Central
- **API Câmbio**:
  - Cotação do dólar em uma data específica e por período.
- **API PIX**:
  - Estoque de chaves, transações por município e estatísticas de transações.
- **API Meios de Pagamentos**:
  - Estoque e transações de cartões, dados mensais e trimestrais.
- **API Boletim Focus**:
  - Expectativas de mercado mensais, trimestrais e anuais.

### Comexstat
- Importação e exportação (municípios e estados):
  - Variáveis: Período, localidade, fluxo (importação/exportação), métricas.

---

## Processo ETL

### 1. **Extract (Extrair)**
- Dados extraídos das APIs:
  - IBGE, Banco Central e Comexstat.
- Scripts dedicados em Python para cada API.

### 2. **Transform (Transformar)**
- Processos realizados:
  - Limpeza, formatação, agregação e conversão de tipos.
  - Integração e normalização dos dados para carregamento.

### 3. **Load (Carregar)**
- Dados carregados no banco MongoDB (Atlas).
- Scripts automatizados para realizar a carga.

### 4. **Visualização**
- Dados do MongoDB conectados ao Power BI.
- Dashboards desenvolvidos com análises detalhadas.

---

## Visualizações e Dashboards

### Dashboards Desenvolvidos
- **Arquivo Power BI**: `ProjetoFecomercio.pbix`
- **Visualizações**:
  - `overview_final_dash.png`
  - `pim_final_dash.png`
  - `pms_final_dash.png`

### Exemplos de Análises
- Evolução mensal e acumulada de serviços e indústria.
- Fluxos de exportação e importação por estado e município.
- Indicadores econômicos como câmbio e PIX.

---

## Instalação e Configuração

### Requisitos
1. **Python 3.9+**
2. **Bibliotecas Python**:
   - `pandas`, `requests`, `pymongo`, `matplotlib`
3. **Banco de Dados**:
   - MongoDB (Atlas)
4. **Ferramenta de Visualização**:
   - Power BI

### Passos
1. Clone o repositório:
   ```bash
   git clone <repo_url>
   ```
2. Instale as dependências:
   ```bash
   pip install -r requirements.txt
   ```
3. Execute os scripts de ETL na pasta `src/processing/`.

---

## Requisitos
- Python
- MongoDB Atlas
- Power BI para análise e visualização.

---

## Contribuidores
- Equipe Fecomércio

---

## Licença
Este projeto é licenciado sob a licença MIT. Consulte o arquivo `LICENSE` para mais informações.
```
