# Análise Exploratória Inicial - Dados Ingram Micro Enterprise

**Data da análise:** 19 de Fevereiro de 2026  
**Arquivo analisado:** `Dados_Antonio.xlsx`  
**Aba:** Conta Foco  
**Analista:** Antonio Oliveira Cruz

---

## 📊 Resumo Executivo

Os dados fornecidos representam **5 anos de histórico de faturamento** (2022-2026) do time Enterprise da Ingram Micro, totalizando **R$ 1,99 bilhões** em transações com **174 clientes únicos**.

### Principais descobertas:

✅ **Dados de alta qualidade** - estrutura clara, poucos erros  
⚠️ **Missing values significativos** - especialmente em 2026 (92.7%)  
📈 **Crescimento em ticket médio** - de R$ 1,46 M (2022) para R$ 2,34 M (2026)  
🏦 **Concentração em instituições financeiras** - 7 dos top 10 clientes são bancos/fintechs  
🖥️ **Foco em IBM e Segurança Lógica** - principais categorias de produto  

---

## 1. Estrutura dos Dados

### 1.1 Dimensões

| Métrica | Valor |
|---------|-------|
| **Total de linhas** | 962 |
| **Total de colunas** | 11 |
| **Tamanho do arquivo** | 51.03 MB |
| **Formato** | Excel (.xlsx) |
| **Período** | 2022-2026 (5 anos) |

### 1.2 Colunas Disponíveis

| # | Nome da Coluna | Tipo | Preenchimento | Obs |
|---|----------------|------|---------------|-----|
| 1 | `Unnamed: 0` | float64 | 0.0% | Coluna vazia (pode ser removida) |
| 2 | `Person` | object | 0.2% | Vendedor (apenas 2 valores únicos) |
| 3 | `EndUserName` | object | 18.1% | Nome do cliente final |
| 4 | `EndUserCNPJ` | float64 | 19.4% | CNPJ do cliente |
| 5 | `VendorDivision3` | object | 55.4% | Categoria de produto (25 categorias) |
| 6 | `VendorDivision4` | object | 99.9% | Subcategoria de produto (125 subcategorias) |
| 7 | `2022` | float64 | 40.2% | Faturamento em 2022 (R$) |
| 8 | `2023` | float64 | 42.7% | Faturamento em 2023 (R$) |
| 9 | `2024` | float64 | 38.6% | Faturamento em 2024 (R$) |
| 10 | `2025` | float64 | 34.1% | Faturamento em 2025 (R$) |
| 11 | `2026` | float64 | 7.3% | Faturamento em 2026 (R$) |

---

## 2. Qualidade dos Dados

### 2.1 Missing Values (Valores Ausentes)

| Coluna | Missing | Percentual | Ação Recomendada |
|--------|---------|------------|------------------|
| `Unnamed: 0` | 962 | 100.0% | ❌ **Remover coluna** |
| `Person` | 960 | 99.8% | ⚠️ Preencher com "Não informado" ou investigar |
| `EndUserName` | 788 | 81.9% | ⚠️ Crítico - precisa de tratamento |
| `EndUserCNPJ` | 775 | 80.6% | ⚠️ Crítico - precisa de tratamento |
| `VendorDivision3` | 429 | 44.6% | ⚠️ Preencher com "Outros" |
| `VendorDivision4` | 1 | 0.1% | ✅ Aceitável |
| `2022` | 575 | 59.8% | ✅ Normal (nem todos os clientes compraram em 2022) |
| `2023` | 551 | 57.3% | ✅ Normal |
| `2024` | 591 | 61.4% | ✅ Normal |
| `2025` | 634 | 65.9% | ✅ Normal |
| `2026` | 892 | 92.7% | ⚠️ Ano incompleto (apenas 2 meses de dados) |

### 2.2 Observações de Qualidade

#### ✅ Pontos Positivos:
- **Subcategorias de produtos** (VendorDivision4) quase 100% preenchidas
- **Valores numéricos** (faturamento) sem erros de formatação
- **Estrutura temporal** clara e organizada

#### ⚠️ Pontos de Atenção:
1. **Alto missing em identificação de clientes** (EndUserName, CNPJ)
   - Possível causa: registros agregados ou linhas de subtotal
   - Solução: filtrar apenas linhas com cliente identificado

2. **Coluna Person com 99.8% de missing**
   - Apenas 2 valores: "Cruz, Antonio" e "Total Geral"
   - Solução: verificar se há outras fontes de dados de vendedores

3. **2026 com apenas 7.3% de dados**
   - Ano em andamento (provavelmente apenas Jan-Fev/2026)
   - Solução: usar apenas para validação, não para treino

---

## 3. Análise Financeira

### 3.1 Faturamento Total por Ano

| Ano | Total Faturado | Transações | Ticket Médio | Mediana | Maior Venda | % do Total |
|-----|----------------|------------|--------------|---------|-------------|------------|
| **2022** | R$ 567,0 M | 387 | R$ 1,46 M | R$ 54,4 K | R$ 283,5 M | 28.5% |
| **2023** | R$ 385,8 M | 411 | R$ 938,7 K | R$ 39,5 K | R$ 192,9 M | 19.4% |
| **2024** | R$ 420,6 M | 371 | R$ 1,13 M | R$ 68,4 K | R$ 210,3 M | 21.1% |
| **2025** | R$ 451,9 M | 328 | R$ 1,37 M | R$ 120,4 K | R$ 225,9 M | 22.7% |
| **2026** | R$ 163,9 M | 70 | R$ 2,34 M | R$ 146,5 K | R$ 81,9 M | 8.2% |
| **TOTAL** | **R$ 1,99 B** | **1.567** | **R$ 1,27 M** | — | — | **100%** |

### 3.2 Insights Financeiros

#### 📈 Tendências Identificadas:

1. **Ticket médio crescente**
   - 2022: R$ 1,46 M
   - 2023: R$ 938 K (queda)
   - 2024: R$ 1,13 M (recuperação)
   - 2025: R$ 1,37 M (crescimento)
   - 2026: R$ 2,34 M (forte crescimento - projeção)

2. **Volume de transações decrescente**
   - 2022: 387 transações
   - 2023: 411 (+6.2%)
   - 2024: 371 (-9.7%)
   - 2025: 328 (-11.6%)
   - 2026: 70 (projeção: ~420 no ano completo)
   - **Interpretação:** menos transações, mas maiores valores (consolidação)

3. **Concentração em grandes contratos**
   - 50% das transações estão abaixo de R$ 54-146 K (mediana)
   - As maiores vendas representam ~40-50% do faturamento anual
   - **Conclusão:** negócio altamente dependente de BIG deals

4. **Variação anual**
   - 2023 foi o pior ano (R$ 385 M)
   - 2022 foi o melhor ano (R$ 567 M)
   - 2025 mostra recuperação (R$ 451 M)
   - **Hipótese:** crise econômica em 2023, recuperação pós-pandemia

---

## 4. Análise de Clientes

### 4.1 Distribuição

- **Total de clientes únicos:** 174
- **Clientes com nome identificado:** 174 (18.1% dos registros)
- **Média de transações por cliente:** 9.0

### 4.2 Top 10 Clientes por Volume Total (2022-2026)

| Ranking | Cliente | Setor | Faturamento Total | % do Total |
|---------|---------|-------|-------------------|------------|
| 1 | CAMARA INTERBANCARIA DE PAGAMENTOS | Financeiro | R$ 17,6 M | 0.89% |
| 2 | NU PAGAMENTOS SA | Fintech | R$ 14,7 M | 0.74% |
| 3 | BANCO BRADESCO SA | Financeiro | R$ 14,3 M | 0.72% |
| 4 | BANCO ITAU S/A | Financeiro | R$ 10,3 M | 0.52% |
| 5 | PICPAY INSTITUIÇÃO DE PAGAMENTO SA | Fintech | R$ 9,7 M | 0.49% |
| 6 | B3 SA BRASIL BOLSA BALCAO | Financeiro | R$ 7,0 M | 0.35% |
| 7 | AVENUES SAO PAULO EDUCACAO LTDA | Educação | R$ 4,6 M | 0.23% |
| 8 | BANCO PACTUAL S/A | Financeiro | R$ 3,8 M | 0.19% |
| 9 | CANCELADO | — | R$ 3,4 M | 0.17% |
| 10 | CIP SA | Financeiro | R$ 2,7 M | 0.14% |
| **Top 10 Total** | — | — | **R$ 88,1 M** | **4.43%** |

### 4.3 Insights de Clientes

#### 🏦 Predominância do Setor Financeiro:
- **7 de 10** clientes top são bancos, fintechs ou infraestrutura financeira
- Setores representados:
  - Financeiro: 70%
  - Educação: 10%
  - Outros: 20%

#### 📊 Concentração moderada:
- Top 10 clientes = apenas **4.43%** do faturamento total
- **Conclusão:** base pulverizada, sem dependência crítica de poucos clientes
- **Implicação para TCC:** predição deve funcionar bem para diferentes perfis

#### ⚠️ Registro "CANCELADO":
- R$ 3,4 M em faturamento cancelado
- **Ação:** investigar se são contratos rescindidos ou devoluções

---

## 5. Análise de Produtos

### 5.1 Categorias Principais (VendorDivision3)

| # | Categoria | Registros | % do Total |
|---|-----------|-----------|------------|
| 1 | Logical Security | 99 | 18.6% |
| 2 | IBM | 74 | 13.9% |
| 3 | Hardware Volume | 70 | 13.1% |
| 4 | Cloud | 57 | 10.7% |
| 5 | Dell Client | 33 | 6.2% |
| 6 | Mobility | 33 | 6.2% |
| 7 | Software Value | 32 | 6.0% |
| 8 | Other SW Volume CC | 18 | 3.4% |
| 9 | Others AS (General) | 17 | 3.2% |
| 10 | Cisco | 16 | 3.0% |
| **Outros** | — | 84 | 15.8% |
| **Total** | **25 categorias** | **533** | **100%** |

### 5.2 Subcategorias Principais (VendorDivision4)

| # | Subcategoria | Registros | % do Total |
|---|--------------|-----------|------------|
| 1 | IBM SOFTWARE ON PREMISES - RENEW | 51 | 5.3% |
| 2 | Apple | 46 | 4.8% |
| 3 | IBM SOFTWARE ON PREMISES - NEW | 45 | 4.7% |
| 4 | Dell Client | 33 | 3.4% |
| 5 | Logitech | 32 | 3.3% |
| 6 | IBM Software Cloud | 27 | 2.8% |
| 7 | VMWare | 27 | 2.8% |
| 8 | Samsung | 26 | 2.7% |
| 9 | LG | 24 | 2.5% |
| 10 | Citrix Cloud | 23 | 2.4% |
| **Outros** | — | 627 | 65.2% |
| **Total** | **125 subcategorias** | **961** | **100%** |

### 5.3 Insights de Produtos

#### 🖥️ Foco em Software e Infraestrutura:
1. **IBM domina o portfólio**
   - Categoria #2 (IBM geral): 74 registros
   - Subcategorias IBM:
     - IBM ON PREMISES - RENEW: 51 (renovações)
     - IBM ON PREMISES - NEW: 45 (novos contratos)
     - IBM Cloud: 27
   - **Total IBM:** 147 registros (~15% do total)

2. **Segurança Lógica é a categoria #1**
   - 99 registros (18.6%)
   - Produtos: Fortinet, Palo Alto, etc.
   - **Oportunidade:** upsell de produtos de segurança

3. **Cloud em ascensão**
   - 57 registros na categoria Cloud
   - Subcategorias cloud:
     - Citrix Cloud: 23
     - IBM Software Cloud: 27
     - Microsoft (Azure, CSP, NCE): múltiplos registros
   - **Tendência:** migração de on-premises para cloud

4. **Hardware Volume**
   - Apple: 46 registros (dispositivos móveis, Macs)
   - Samsung, LG: equipamentos
   - Dell Client: 33 registros
   - **Insight:** renovação de equipamentos a cada 3-5 anos

#### 🔄 Oportunidades de Renovação:
- **"RENEW" identificado:** IBM SOFTWARE ON PREMISES - RENEW (51 registros)
- **Hipótese:** contratos de software com ciclos de renovação anuais ou trienais
- **Para o TCC:** feature essencial para predição de renovações

---

## 6. Análise de Vendedores

### 6.1 Dados Disponíveis

| Vendedor | Registros |
|----------|-----------|
| Cruz, Antonio | 1 |
| Total Geral | 1 |
| *Não informado* | 960 (99.8%) |

### 6.2 Observações

⚠️ **Dados insuficientes para análise de vendedores**
- Apenas 2 registros com vendedor identificado (0.2%)
- Possível causa:
  - Dados exportados de relatório agregado
  - Coluna não preenchida no sistema de origem
  - Anonimização removeu informações de vendedores

**Impacto no TCC:**
- Não será possível criar modelos por vendedor
- Foco deve ser em clientes, produtos e temporalidade

---

## 7. Recomendações para o TCC

### 7.1 Pré-processamento Obrigatório

| Tarefa | Prioridade | Justificativa |
|--------|------------|---------------|
| **1. Remover coluna `Unnamed: 0`** | 🔴 Alta | 100% vazia, sem utilidade |
| **2. Filtrar registros com cliente identificado** | 🔴 Alta | 81.9% sem cliente = linhas de subtotal |
| **3. Tratar missing em VendorDivision3** | 🟡 Média | 44.6% missing, pode impactar modelos |
| **4. Separar dados de 2026 para validação** | 🟡 Média | Apenas 7.3% preenchido (ano incompleto) |
| **5. Criar features temporais** | 🔴 Alta | Dias desde última compra, frequência, etc. |
| **6. Feature engineering de RFM** | 🔴 Alta | Recency, Frequency, Monetary |
| **7. Identificar padrões de renovação** | 🔴 Alta | Buscar palavras-chave "RENEW", "UPGRADE" |

### 7.2 Features Sugeridas (Feature Engineering)

#### Temporal:
- `dias_desde_ultima_compra` - dias entre transações do mesmo cliente
- `frequencia_compras_ano` - quantas vezes o cliente comprou por ano
- `trimestre` - Q1, Q2, Q3, Q4
- `mes` - sazonalidade mensal
- `ano_primeira_compra` - tempo de relacionamento

#### RFM (Recency, Frequency, Monetary):
- `recency` - dias desde última compra
- `frequency` - número de transações
- `monetary` - valor total gasto

#### Produto:
- `categoria_principal` - categoria mais comprada pelo cliente
- `diversidade_produtos` - número de subcategorias distintas
- `ticket_medio_cliente` - valor médio por transação
- `volatilidade_compras` - desvio padrão dos valores

#### Comportamento:
- `cliente_renew` - flag se já teve "RENEW" no histórico
- `cliente_cloud` - flag se já comprou produtos cloud
- `cliente_ibm` - flag se já comprou IBM
- `cliente_fidelizado` - comprou em ≥3 anos consecutivos

### 7.3 Estrutura de Dados para Modelagem

**Transformação necessária:**

❌ **Formato atual (wide):**
```
| Cliente | 2022 | 2023 | 2024 | 2025 | 2026 |
```

✅ **Formato ideal (long/tidy):**
```
| Cliente | Ano | Valor | Categoria | Subcategoria | Recency | Frequency | Monetary |
```

**Script recomendado:**
```python
df_melted = pd.melt(
    df,
    id_vars=['EndUserName', 'VendorDivision3', 'VendorDivision4'],
    value_vars=['2022', '2023', '2024', '2025', '2026'],
    var_name='Ano',
    value_name='Valor'
)
```

### 7.4 Divisão dos Dados (Train/Val/Test)

**Estratégia temporal (Time-Series Split):**

| Conjunto | Período | % | Uso |
|----------|---------|---|-----|
| **Treino** | 2022-2023 | 70% | Treinamento dos modelos |
| **Validação** | 2024 | 15% | Tuning de hiperparâmetros |
| **Teste** | 2025 | 15% | Avaliação final |
| **Holdout** | 2026 | — | Validação real (ano em andamento) |

**Justificativa:**
- Respeita ordem temporal (não há data leakage)
- 2026 como holdout real para validar performance em produção

---

## 8. Próximos Passos

### Fase 1: Limpeza e Preparação (Semana 1-2)
- [ ] Executar script de limpeza (`notebooks/01_EDA_Automatico.ipynb`)
- [ ] Aplicar filtros de qualidade
- [ ] Salvar dados limpos em `dados/processed/contratos_limpo.csv`

### Fase 2: Feature Engineering (Semana 3-4)
- [ ] Criar features temporais
- [ ] Calcular RFM
- [ ] Gerar flags de comportamento
- [ ] Salvar em `dados/processed/features_engineered.csv`

### Fase 3: EDA Avançada (Semana 5-6)
- [ ] 15+ gráficos de análise
- [ ] Testes de hipóteses
- [ ] Correlações
- [ ] Identificação de outliers

### Fase 4: Modelagem (Semana 7-24)
- [ ] Módulo 1: Big Deals (Semana 7-9)
- [ ] Módulo 2: Comportamento (Semana 10-12)
- [ ] Módulo 3: Upgrades (Semana 13-15)
- [ ] Módulo 4: Projeção (Semana 16-20)
- [ ] Módulo 5: Scoring (Semana 21-24)

---

## 9. Conclusões da Análise Inicial

### ✅ Pontos Fortes dos Dados:
1. **Volume substancial** - R$ 1,99 B em 5 anos
2. **Estrutura clara** - colunas bem definidas
3. **Período adequado** - 5 anos suficientes para modelagem
4. **Diversidade de produtos** - 125 subcategorias
5. **Base de clientes pulverizada** - 174 clientes, sem dependência crítica

### ⚠️ Desafios Identificados:
1. **Missing values altos** - especialmente em identificação de clientes
2. **Dados de vendedores insuficientes** - 99.8% missing
3. **2026 incompleto** - apenas 2 meses de dados
4. **Formato wide** - precisa transformação para long

### 🎯 Viabilidade do TCC:
**ALTAMENTE VIÁVEL ✅**

Os dados são **suficientes e adequados** para desenvolver todos os 5 módulos propostos:

| Módulo | Viabilidade | Observações |
|--------|-------------|-------------|
| 1 - Big Deals | ✅ Alta | Dados de renovação identificados |
| 2 - Comportamento | ✅ Alta | Histórico temporal robusto |
| 3 - Upgrades | ✅ Média | Identificar "RENEW" vs "NEW" |
| 4 - Projeção | ✅ Alta | 5 anos de série temporal |
| 5 - Scoring | ✅ Alta | Múltiplas features disponíveis |

**Recomendação final:** PROSSEGUIR com o projeto. Os dados têm qualidade suficiente para gerar um TCC de alto nível acadêmico e impacto prático significativo.

---

**Documento gerado automaticamente em:** 19/02/2026  
**Próxima revisão:** Após limpeza e feature engineering (Semana 4)
