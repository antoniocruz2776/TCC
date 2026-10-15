# Sistema Preditivo de Renovações Enterprise B2B - Ingram Micro
## TCC - MBA em Data Science e Analytics | USP/SP | 2º Semestre 2025

![Status](https://img.shields.io/badge/status-em_desenvolvimento-yellow)
![Python](https://img.shields.io/badge/Python-3.8+-blue)
![License](https://img.shields.io/badge/license-MIT-green)

---

## 📋 Sumário

1. [Visão Geral](#visão-geral)
2. [Problema de Negócio](#problema-de-negócio)
3. [Objetivos](#objetivos)
4. [Dados do Projeto](#dados-do-projeto)
5. [Metodologia](#metodologia)
6. [Estrutura do Repositório](#estrutura-do-repositório)
7. [Instalação e Configuração](#instalação-e-configuração)
8. [Resultados Esperados](#resultados-esperados)
9. [Cronograma](#cronograma)
10. [Autor](#autor)

---

## 🎯 Visão Geral

Este projeto de TCC tem como foco desenvolver um **sistema preditivo baseado em Machine Learning** para automatizar e otimizar o processo de gestão de contratos Enterprise B2B na Ingram Micro, especificamente para o time Enterprise.

O sistema utiliza **5 anos de dados históricos** (2022-2026) contendo:
- **962 registros** de transações
- **174 clientes únicos** (grandes contas Enterprise)
- **R$ 1,99 bilhões** em faturamento total
- **25 categorias** de produtos
- **125 subcategorias** de produtos

---

## 🔴 Problema de Negócio

### Contexto

A Ingram Micro, no segmento Enterprise B2B, gerencia contratos de alto valor (tickets médios de R$ 1,4 milhão) com ciclos longos de renovação, upgrades tecnológicos e vendas consultivas. Atualmente, todo o processo de acompanhamento é **manual**, realizado através de planilhas Excel, o que gera:

### Dores Críticas

| Problema | Impacto Atual | Meta |
|----------|---------------|------|
| 🔴 **Renovações perdidas** | ~30% de contratos não renovados | Reduzir para 10% |
| 🔴 **Erro de forecast** | 30-40% de desvio nas previsões | Melhorar para 15-20% |
| 🔴 **Oportunidades de upgrade não capturadas** | 5-8% de conversão | Aumentar para 12-15% |
| 🔴 **Abordagem comercial genérica** | 6-8% de taxa de conversão | Aumentar para 12-15% |
| 🔴 **Tempo de preparação** | 8 horas/semana | Reduzir para 1 hora/semana |

### Impacto Financeiro Estimado

**Perda anual por ineficiências:** R$ 14-18 milhões
- Renovações perdidas: R$ 8-10 M
- Upgrades não capturados: R$ 4-6 M
- Ineficiência operacional: R$ 2 M

---

## 🎯 Objetivos

### Objetivo Geral

Desenvolver um modelo de Machine Learning que **automatize a identificação de BIG deals, preveja renovações, detecte oportunidades de upgrades tecnológicos e priorize abordagens comerciais** para contratos Enterprise B2B.

### Objetivos Específicos

1. **Mapeamento de BIG Deals (Módulo 1)**
   - Identificar contratos de renovação nos próximos 90 dias
   - Classificar por risco (Alto, Médio, Baixo)
   - Gerar alertas automáticos para contratos críticos

2. **Análise de Comportamento de Renovação (Módulo 2)**
   - Classificar clientes em 5 perfis comportamentais:
     - 🟢 Expander (crescimento constante)
     - 🔵 Maintainer (renovação fiel)
     - 🟡 Optimizer (busca melhor custo)
     - 🟠 Intermittent (compras esporádicas)
     - 🔴 Risk (risco de churn)
   - Prever taxa de renovação por perfil

3. **Detecção de Oportunidades de Upgrade (Módulo 3)**
   - Identificar produtos legados (EOL)
   - Estimar probabilidade de migração
   - Sugerir produtos substitutos

4. **Projeção de Compras Futuras (Módulo 4)**
   - Prever necessidades de hardware por ciclo de vida
   - Antecipar expansões de infraestrutura
   - Projetar faturamento por produto/categoria/região

5. **Priorização Comercial Sniper (Módulo 5)**
   - Scoring de contas: Valor × Probabilidade × Urgência
   - Gerar lista Top 20 semanal
   - Dashboard executivo para gestores

---

## 📊 Dados do Projeto

### Fonte dos Dados

**Arquivo:** `Dados_Antonio.xlsx`
- **Origem:** Sistema de faturamento Ingram Micro
- **Período:** 2022-2026 (5 anos)
- **Status:** Dados reais, anonimizados conforme LGPD

### Estrutura dos Dados

| Coluna | Tipo | Preenchimento | Descrição |
|--------|------|---------------|-----------|
| `Person` | string | 0.2% | Vendedor responsável |
| `EndUserName` | string | 18.1% | Nome do cliente (End User) |
| `EndUserCNPJ` | numeric | 19.4% | CNPJ do cliente |
| `VendorDivision3` | string | 55.4% | Categoria de produto (25 categorias) |
| `VendorDivision4` | string | 99.9% | Subcategoria de produto (125 subcategorias) |
| `2022` | numeric | 40.2% | Faturamento em 2022 (R$) |
| `2023` | numeric | 42.7% | Faturamento em 2023 (R$) |
| `2024` | numeric | 38.6% | Faturamento em 2024 (R$) |
| `2025` | numeric | 34.1% | Faturamento em 2025 (R$) |
| `2026` | numeric | 7.3% | Faturamento em 2026 (R$) |

### Estatísticas Descritivas

#### Faturamento por Ano

| Ano | Total Faturado | Transações | Ticket Médio | Mediana | Maior Venda |
|-----|----------------|------------|--------------|---------|-------------|
| **2022** | R$ 567,0 M | 387 | R$ 1,46 M | R$ 54,4 K | R$ 283,5 M |
| **2023** | R$ 385,8 M | 411 | R$ 938,7 K | R$ 39,5 K | R$ 192,9 M |
| **2024** | R$ 420,6 M | 371 | R$ 1,13 M | R$ 68,4 K | R$ 210,3 M |
| **2025** | R$ 451,9 M | 328 | R$ 1,37 M | R$ 120,4 K | R$ 225,9 M |
| **2026** | R$ 163,9 M | 70 | R$ 2,34 M | R$ 146,5 K | R$ 81,9 M |
| **TOTAL** | **R$ 1,99 B** | **1.567** | **R$ 1,27 M** | — | — |

#### Top 10 Clientes por Volume Total

| # | Cliente | Faturamento Total |
|---|---------|-------------------|
| 1 | CAMARA INTERBANCARIA DE PAGAMENTOS | R$ 17,6 M |
| 2 | NU PAGAMENTOS SA | R$ 14,7 M |
| 3 | BANCO BRADESCO SA | R$ 14,3 M |
| 4 | BANCO ITAU S/A | R$ 10,3 M |
| 5 | PICPAY INSTITUIÇÃO DE PAGAMENTO SA | R$ 9,7 M |
| 6 | B3 SA BRASIL BOLSA BALCAO | R$ 7,0 M |
| 7 | AVENUES SAO PAULO EDUCACAO LTDA | R$ 4,6 M |
| 8 | BANCO PACTUAL S/A | R$ 3,8 M |
| 9 | CANCELADO | R$ 3,4 M |
| 10 | CIP SA | R$ 2,7 M |

#### Top 5 Categorias de Produtos

1. **Logical Security** - 99 registros
2. **IBM** - 74 registros
3. **Hardware Volume** - 70 registros
4. **Cloud** - 57 registros
5. **Dell Client** - 33 registros

#### Top 5 Subcategorias de Produtos

1. **IBM SOFTWARE ON PREMISES - RENEW** - 51 registros
2. **Apple** - 46 registros
3. **IBM SOFTWARE ON PREMISES - NEW** - 45 registros
4. **Dell Client** - 33 registros
5. **Logitech** - 32 registros

---

## 🔬 Metodologia

### 1. Preparação dos Dados

**Etapas:**
- ✅ Coleta e validação dos dados (concluído)
- 🔄 Limpeza e tratamento de missing values
- 🔄 Feature engineering:
  - Criar variáveis temporais (dias até renovação, tempo desde última compra)
  - Calcular métricas RFM (Recency, Frequency, Monetary)
  - Extrair padrões sazonais
  - Criar flags de comportamento (churn, upgrade, expansão)

### 2. Análise Exploratória (EDA)

**Notebooks:**
- `01_EDA_Automatico.ipynb` - Análise exploratória completa
  - Distribuição de vendas por ano
  - Análise de sazonalidade
  - Identificação de outliers
  - Correlações entre variáveis
  - Visualizações (15+ gráficos)

### 3. Modelagem Preditiva

**Abordagem:** Ensemble de modelos supervisionados

| Módulo | Tipo de Problema | Algoritmos | Métrica Principal |
|--------|------------------|------------|-------------------|
| 1 - Big Deals | Classificação (Risco) | XGBoost, Random Forest | F1-Score |
| 2 - Comportamento | Classificação Multi-classe | XGBoost, LightGBM | Accuracy, F1 |
| 3 - Upgrades | Classificação Binária | Logistic Regression, XGBoost | Precision |
| 4 - Projeção | Regressão (Time Series) | XGBoost, Prophet, LSTM | MAPE, MAE |
| 5 - Priorização | Scoring (Regressão) | XGBoost | RMSE, R² |

**Notebooks:**
- `02_Feature_Engineering.ipynb`
- `03_Modelagem_Modulo1_BigDeals.ipynb`
- `04_Modelagem_Modulo2_Comportamento.ipynb`
- `05_Modelagem_Modulo3_Upgrades.ipynb`
- `06_Modelagem_Modulo4_Projecao.ipynb`
- `07_Modelagem_Modulo5_Priorizacao.ipynb`

### 4. Validação

**Estratégia:** Time-Series Split
- **Treino:** 2022-2023 (70%)
- **Validação:** 2024 (15%)
- **Teste:** 2025-2026 (15%)

**Cross-validation:** Não será aplicado (dados temporais)

**Métricas de Avaliação:**
- Classificação: Accuracy, Precision, Recall, F1-Score, AUC-ROC
- Regressão: MAE, RMSE, MAPE, R²

### 5. Dashboard Executivo

**Ferramenta:** Power BI

**Páginas:**
1. **Visão Executiva** - KPIs gerais, faturamento acumulado, pipeline
2. **Módulo 1** - Contratos em risco de não renovação
3. **Módulo 2** - Perfis comportamentais dos clientes
4. **Módulo 3** - Oportunidades de upgrade
5. **Módulo 4** - Projeção de vendas por produto/categoria/região
6. **Módulo 5** - Ranking de priorização comercial (Top 20)

**Integração:**
```bash
python scripts/exportar_powerbi.py
```

---

## 📁 Estrutura do Repositório

```
TCC_Predicao_Renovacoes/
│
├── README.md                          # Este arquivo
├── LICENSE                            # Licença MIT
├── .gitignore                         # Arquivos ignorados pelo Git
│
├── dados/                             # ⚠️ NÃO VERSIONADO (Git ignore)
│   ├── raw/                           # Dados brutos originais
│   │   └── Dados_Antonio.xlsx
│   ├── processed/                     # Dados processados/limpos
│   │   ├── contratos_limpo.csv
│   │   ├── clientes_agregado.csv
│   │   └── features_engineered.csv
│   └── predictions/                   # Saídas dos modelos
│       ├── modulo1_big_deals.csv
│       ├── modulo2_comportamento.csv
│       ├── modulo3_upgrades.csv
│       ├── modulo4_projecao.csv
│       └── modulo5_scoring.csv
│
├── notebooks/                         # Notebooks Jupyter/Colab
│   ├── 01_EDA_Automatico.ipynb
│   ├── 02_Feature_Engineering.ipynb
│   ├── 03_Modelagem_Modulo1_BigDeals.ipynb
│   ├── 04_Modelagem_Modulo2_Comportamento.ipynb
│   ├── 05_Modelagem_Modulo3_Upgrades.ipynb
│   ├── 06_Modelagem_Modulo4_Projecao.ipynb
│   └── 07_Modelagem_Modulo5_Priorizacao.ipynb
│
├── src/                               # Código-fonte modularizado
│   ├── __init__.py
│   ├── data/
│   │   ├── __init__.py
│   │   ├── load_data.py               # Carregamento de dados
│   │   ├── preprocessing.py           # Limpeza e tratamento
│   │   └── feature_engineering.py     # Criação de features
│   ├── models/
│   │   ├── __init__.py
│   │   ├── modulo1_big_deals.py
│   │   ├── modulo2_comportamento.py
│   │   ├── modulo3_upgrades.py
│   │   ├── modulo4_projecao.py
│   │   └── modulo5_scoring.py
│   ├── utils/
│   │   ├── __init__.py
│   │   ├── config.py                  # Configurações globais
│   │   ├── metrics.py                 # Cálculo de métricas
│   │   └── visualizations.py          # Funções de plotagem
│   └── dashboard/
│       └── exportar_powerbi.py        # Script de exportação
│
├── modelos/                           # Modelos treinados (pickle)
│   ├── xgb_big_deals.pkl
│   ├── xgb_comportamento.pkl
│   ├── xgb_upgrades.pkl
│   ├── xgb_projecao.pkl
│   └── xgb_scoring.pkl
│
├── dashboard/                         # Dashboard Power BI
│   ├── Dashboard_Ingram_Enterprise.pbix
│   └── screenshots/                   # Capturas de tela
│
├── templates_texto/                   # Templates para escrita do TCC
│   ├── Capitulo_1_Introducao.docx
│   ├── Capitulo_2_Referencial_Teorico.docx
│   ├── Capitulo_3_Metodologia.docx
│   ├── Capitulo_4_Resultados.docx
│   └── Capitulo_5_Conclusao.docx
│
├── defesa/                            # Materiais para defesa
│   ├── Slides_Defesa.pptx
│   ├── Script_Apresentacao.docx
│   └── Perguntas_Banca_30.docx        # 30 perguntas + respostas
│
├── referencias/                       # Referências bibliográficas
│   ├── Bibliografia_ABNT.bib
│   └── Artigos_PDF/
│
├── scripts/                           # Scripts utilitários
│   ├── install_dependencies.sh        # Instalação de dependências
│   ├── anonimizar_dados.py            # Anonimização (LGPD)
│   ├── exportar_powerbi.py            # Exportação para Power BI
│   ├── gerar_relatorio.py             # Relatório executivo PDF
│   └── requirements.txt               # Dependências Python
│
└── docs/                              # Documentação adicional
    ├── 00_GUIA_INICIO_RAPIDO.md       # Guia de início rápido
    ├── Cronograma_12_Meses.xlsx       # Cronograma detalhado
    └── Analise_Inicial.json           # Estatísticas dos dados
```

---

## ⚙️ Instalação e Configuração

### Pré-requisitos

- Python 3.8+
- Git
- Power BI Desktop (para visualização do dashboard)
- Jupyter Notebook ou Google Colab

### Passo 1: Clonar o Repositório

```bash
git clone https://github.com/antoniocruz2776/TCC.git
cd TCC
```

### Passo 2: Criar Ambiente Virtual

```bash
# Linux/Mac
python3 -m venv venv
source venv/bin/activate

# Windows
python -m venv venv
venv\Scripts\activate
```

### Passo 3: Instalar Dependências

```bash
pip install -r scripts/requirements.txt
```

**Principais bibliotecas:**
- pandas >= 1.3.0
- numpy >= 1.21.0
- scikit-learn >= 1.0.0
- xgboost >= 1.5.0
- lightgbm >= 3.3.0
- matplotlib >= 3.4.0
- seaborn >= 0.11.0
- prophet >= 1.0
- shap >= 0.40.0
- openpyxl >= 3.0.0

### Passo 4: Configurar Dados

**⚠️ IMPORTANTE:** Os dados brutos **NÃO estão versionados** no Git por motivos de confidencialidade.

1. Coloque o arquivo `Dados_Antonio.xlsx` em `dados/raw/`
2. (Opcional) Execute a anonimização:

```bash
python scripts/anonimizar_dados.py
```

### Passo 5: Executar Notebooks

**Ordem de execução:**

```bash
# 1. Análise Exploratória
jupyter notebook notebooks/01_EDA_Automatico.ipynb

# 2. Feature Engineering
jupyter notebook notebooks/02_Feature_Engineering.ipynb

# 3. Modelagem (executar em sequência)
jupyter notebook notebooks/03_Modelagem_Modulo1_BigDeals.ipynb
jupyter notebook notebooks/04_Modelagem_Modulo2_Comportamento.ipynb
jupyter notebook notebooks/05_Modelagem_Modulo3_Upgrades.ipynb
jupyter notebook notebooks/06_Modelagem_Modulo4_Projecao.ipynb
jupyter notebook notebooks/07_Modelagem_Modulo5_Priorizacao.ipynb
```

### Passo 6: Gerar Dashboard

```bash
python scripts/exportar_powerbi.py
```

Abra o arquivo `dashboard/Dashboard_Ingram_Enterprise.pbix` no Power BI Desktop.

---

## 📈 Resultados Esperados

### Métricas Técnicas (Modelos)

| Módulo | Métrica | Baseline | Meta | Melhor Cenário |
|--------|---------|----------|------|----------------|
| **1 - Big Deals** | F1-Score | 0.60 | 0.80 | 0.85+ |
| **2 - Comportamento** | Accuracy | 0.50 | 0.70 | 0.75+ |
| **3 - Upgrades** | Precision | 0.40 | 0.65 | 0.70+ |
| **4 - Projeção** | MAPE | 25% | 18% | 15% |
| **5 - Scoring** | R² | 0.50 | 0.70 | 0.80+ |

### Impacto de Negócio

| Métrica | Atual | Meta | Ganho |
|---------|-------|------|-------|
| **Taxa de renovação** | 70% | 85-90% | +15-20 pp |
| **Erro de forecast** | 40% | 15-20% | -20-25 pp |
| **Conversão de upgrades** | 5-8% | 12-15% | +7 pp |
| **Tempo de preparação** | 8 h/semana | 1 h/semana | -87.5% |
| **Receita incremental** | — | R$ 8-12 M/ano | +2-3% |

### ROI Estimado

**Investimento:**
- Desenvolvimento: R$ 150.000 (6 meses)
- Infraestrutura: R$ 30.000
- Treinamento: R$ 20.000
- **Total:** R$ 200.000

**Retorno anual:** R$ 10-14 M (redução de perdas + ganho de eficiência)

**ROI:** 5.000-7.000% no primeiro ano

**Payback:** < 2 meses

---

## 📅 Cronograma (12 meses)

| Fase | Duração | Período | Entregas |
|------|---------|---------|----------|
| **1. Fundação** | 2 meses | Jan-Fev/2026 | EDA, Feature Engineering, Notebooks 01-02 |
| **2. Referencial Teórico** | 2 meses | Mar-Abr/2026 | Capítulo 2 (15-20 páginas), Fichamentos |
| **3. Modelagem Avançada** | 3 meses | Mai-Jul/2026 | Modelos 1-5, Tuning, Notebooks 03-07 |
| **4. Dashboard** | 1 mês | Ago/2026 | Power BI, Integração, Exportação |
| **5. Redação** | 2 meses | Set-Out/2026 | Capítulos 1, 3, 4, 5 |
| **6. Finalização** | 1 mês | Nov/2026 | Revisão, Formatação ABNT, PDF |
| **7. Defesa** | 1 mês | Dez/2026 | Slides, Ensaio, Defesa |

**Total:** 12 meses | **Esforço estimado:** ~180 horas | **Média:** 3-4 h/semana

---

## 👤 Autor

**Antonio Oliveira Cruz**
- 📧 Email: antonio_oliveira76@hotmail.com
- 💼 LinkedIn: [linkedin.com/in/antoniocruz2776](https://www.linkedin.com/in/antoniocruz2776)
- 🐙 GitHub: [github.com/antoniocruz2776](https://github.com/antoniocruz2776)
- 🏢 Empresa: Ingram Micro Brasil
- 🎓 Curso: MBA em Data Science e Analytics | USP/SP | 2º Semestre 2025
- 📅 Prazo de entrega: Dezembro/2026

---

## 📜 Licença

Este projeto está licenciado sob a **Licença MIT** - veja o arquivo [LICENSE](LICENSE) para detalhes.

**Uso acadêmico livre com atribuição obrigatória.**

---

## 🙏 Agradecimentos

- Orientador: [Nome do orientador] (a definir)
- Ingram Micro Brasil (fornecimento dos dados)
- USP/SP - Programa de MBA em Data Science e Analytics
- Comunidade open-source (scikit-learn, XGBoost, pandas, etc.)

---

## 📞 Contato e Suporte

Para dúvidas, sugestões ou colaborações:
- Abra uma [issue](https://github.com/antoniocruz2776/TCC/issues) no GitHub
- Envie email para antonio_oliveira76@hotmail.com

---

**Última atualização:** 19 de Fevereiro de 2026

**Status do projeto:** 🟡 Fase 1 - Fundação (Em andamento)
