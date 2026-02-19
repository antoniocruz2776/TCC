# ✅ ANÁLISE CORRIGIDA - DADOS INGRAM MICRO ENTERPRISE

**Data da correção:** 19 de Fevereiro de 2026  
**Fonte:** Linha 969 (Total Geral) do arquivo Dados_Antonio.xlsx  
**Analista:** Antonio Oliveira Cruz

---

## ⚠️ CORREÇÃO IMPORTANTE

Os valores inicialmente analisados estavam **duplicados** (somando linha por linha). Os valores corretos são da **linha 969 (Total Geral)** conforme especificado pelo usuário.

---

## 💰 FATURAMENTO TOTAL POR ANO (Valores Oficiais Corretos)

| Ano | Total NET Faturado | % do Total | Status |
|-----|-------------------|------------|--------|
| **2022** | R$ 283,498,282 | 28.5% | ✅ Completo |
| **2023** | R$ 192,908,304 | 19.4% | ✅ Completo |
| **2024** | R$ 210,319,414 | 21.1% | ✅ Completo |
| **2025** | R$ 225,962,678 | 22.7% | ✅ Completo |
| **2026** | R$ 81,957,627 | 8.2% | ⚠️ Parcial (Jan-Fev) |
| **TOTAL** | **R$ 994,646,305** | **100%** | — |

### 📝 Observações:
- **2026 é parcial:** apenas 2 meses (Janeiro-Fevereiro)
- **Valores NET:** já descontados impostos/devoluções
- **Somatória mensal:** cada ano representa a soma de todos os meses daquele ano

---

## 📈 ANÁLISE DE TENDÊNCIAS

### Variação Ano a Ano

| Período | Variação | Valor Absoluto | Análise |
|---------|----------|----------------|---------|
| **2022 → 2023** | 📉 **-32.0%** | R$ -90,589,978 | Queda acentuada (crise?) |
| **2023 → 2024** | 📈 **+9.0%** | R$ +17,411,110 | Início da recuperação |
| **2024 → 2025** | 📈 **+7.4%** | R$ +15,643,264 | Recuperação sustentada |

### Insights Principais:

1. **Queda de 2023:**
   - Perda de 32% (R$ 90,6 M)
   - Possíveis causas: crise econômica, perda de grandes contratos, mudança de estratégia
   - **Oportunidade para o TCC:** investigar causas e prever futuras quedas

2. **Recuperação 2023-2025:**
   - Crescimento de 17.1% em 2 anos (R$ 33 M)
   - Média de +8.2% ao ano
   - Ainda abaixo do patamar de 2022 (R$ 58 M de diferença)

3. **Tendência geral:**
   - Média anual (2022-2025): R$ 228,2 M
   - Volatilidade alta: desvio padrão ~R$ 37 M
   - Negócio altamente sensível a fatores externos

---

## 🔮 PROJEÇÃO 2026

### Cenário Atual (Jan-Fev 2026):
- **Faturamento parcial:** R$ 81,957,627
- **Média mensal:** R$ 40,978,814

### Projeção Anual (3 cenários):

| Cenário | Método | Projeção Anual 2026 | Crescimento vs 2025 |
|---------|--------|---------------------|---------------------|
| **Conservador** | Média 2023-2025 (R$ 209,7 M) | R$ 209,730,132 | **-7.2%** |
| **Realista** | Jan-Fev × 6 meses | R$ 491,745,762 | **+117.6%** 🚀 |
| **Otimista** | Tendência linear 2023-2025 | R$ 242,606,000 | **+7.4%** |

### Análise da Projeção:
- **Cenário realista é MUITO otimista** (duplica o faturamento)
- **Provável:** entre conservador e otimista (R$ 210-245 M)
- **Para o TCC:** usar 2026 apenas para validação, não para treino

---

## 📊 ESTATÍSTICAS CORRIGIDAS DO DATASET

### Estrutura dos Dados

| Métrica | Valor | Observação |
|---------|-------|------------|
| **Total de linhas** | 969 | Linhas 7-969 |
| **Linha 969** | Total Geral | **Fonte dos valores oficiais** |
| **Dataset limpo** | 961 registros | Excluindo linha de total |
| **Clientes únicos** | 174 | Grandes contas Enterprise |
| **Registros com cliente** | 174 | 18.1% do dataset |
| **Registros sem cliente** | 787 | Linhas de subtotal/categoria |
| **Categorias (VendorDivision3)** | 25 | Tipos de produto |
| **Subcategorias (VendorDivision4)** | 125 | Subtipos de produto |

### Estrutura das Colunas (Corrigida)

| Coluna | Localização | Descrição | Tipo |
|--------|-------------|-----------|------|
| **B8** | Coluna B, linha 8+ | Nome do vendedor | string |
| **EndUserName** | Coluna C | Cliente final (End User) | string |
| **EndUserCNPJ** | Coluna D | CNPJ do cliente | numeric |
| **VendorDivision3** | Coluna E | Categoria do produto | string |
| **VendorDivision4** | Coluna F | Subcategoria do produto | string |
| **2022** | Coluna G | Faturamento NET total 2022 (soma mensal) | numeric |
| **2023** | Coluna H | Faturamento NET total 2023 (soma mensal) | numeric |
| **2024** | Coluna I | Faturamento NET total 2024 (soma mensal) | numeric |
| **2025** | Coluna J | Faturamento NET total 2025 (soma mensal) | numeric |
| **2026** | Coluna K | Faturamento NET total 2026 (Jan-Fev) | numeric |

### Vendedor

- **Célula B7:** "Person" (header)
- **Célula B8:** Nome do vendedor (provavelmente "Cruz, Antonio")
- **Observação:** Apenas 1 vendedor identificado no dataset (dados filtrados por vendedor)

---

## 🎯 IMPLICAÇÕES PARA O TCC

### 1. Valores Corretos a Usar

**✅ Use na documentação:**
- Faturamento total: **R$ 994,6 milhões** (não R$ 1,99 bilhão)
- Período: **4 anos completos + 2 meses parciais**
- Dataset: **961 registros** de transações (excluindo linha de total)

### 2. Interpretação dos Dados

**Cada linha representa:**
- Um cliente específico (End User)
- Comprando um produto específico (VendorDivision3 + VendorDivision4)
- Com valores totais por ano (soma de todos os meses)

**Exemplo de linha:**
```
Cliente: BANCO BRADESCO SA
Produto: IBM
Subproduto: IBM SOFTWARE ON PREMISES - RENEW
2022: R$ 5.000.000
2023: R$ 3.500.000
2024: R$ 4.200.000
2025: R$ 6.100.000
2026: R$ 1.800.000
```

### 3. Oportunidades Analíticas

✅ **Viáveis com estes dados:**

1. **Predição de renovação** - Identificar clientes que compraram em anos anteriores e podem renovar
2. **Churn prediction** - Detectar clientes que pararam de comprar (ex: valor em 2023-2024, zero em 2025)
3. **Upsell/Cross-sell** - Identificar clientes que compraram uma categoria e podem comprar outras
4. **Sazonalidade anual** - Padrões de compra ano a ano (mesmo sem dados mensais)
5. **Segmentação RFM** - Recency (último ano de compra), Frequency (quantos anos comprou), Monetary (valor total)

⚠️ **Limitações:**

1. **Sem dados mensais** - não é possível analisar sazonalidade mensal
2. **Sem dados de renovação explícita** - precisamos inferir pela palavra "RENEW" nos produtos
3. **Sem informações de contrato** - não sabemos datas de início/fim de contratos
4. **Um único vendedor** - não é possível comparar desempenho entre vendedores

### 4. Feature Engineering Recomendado

**Features temporais:**
```python
# Calcular para cada cliente
- anos_como_cliente: quantos anos distintos tem compra
- recencia: 2025 - último_ano_com_compra
- frequencia: número de anos com compra / 4
- monetary: soma de todos os anos
- volatilidade: desvio padrão dos valores anuais
- tendencia: regressão linear dos valores
- churn_flag: 1 se não comprou em 2025, 0 caso contrário
```

**Features de produto:**
```python
# Calcular para cada cliente
- num_categorias: número de VendorDivision3 distintas
- num_subcategorias: número de VendorDivision4 distintas
- categoria_principal: categoria com maior valor total
- flag_renew: 1 se algum produto tem "RENEW" no nome
- flag_new: 1 se algum produto tem "NEW" no nome
- diversificacao: num_subcategorias / total_clientes
```

**Features de comportamento:**
```python
# Padrões de compra
- crescimento_medio: (valor_2025 - valor_2022) / 3
- recuperacao_pos_2023: (valor_2025 - valor_2023) / valor_2023
- anos_consecutivos: maior sequência de anos com compra
- gaps: anos sem compra entre primeira e última compra
```

---

## 📋 DADOS CORRETOS - RESUMO EXECUTIVO

### Para usar no README e documentos:

**Estatísticas Principais:**
- 📊 **Registros:** 961 transações (linhas 7-968)
- 👥 **Clientes:** 174 clientes únicos Enterprise B2B
- 💰 **Faturamento:** R$ 994,6 milhões (2022-2026)
- 📅 **Período:** 4 anos completos + 2 meses (Jan-Fev 2026)
- 📦 **Produtos:** 25 categorias, 125 subcategorias
- 📈 **Média anual:** R$ 228,2 milhões (2022-2025)
- 📉 **Maior queda:** -32% em 2023
- 📈 **Recuperação:** +17.1% de 2023 a 2025

**Características do Negócio:**
- ✅ Segmento Enterprise B2B de alto valor
- ✅ Contratos de software, hardware e cloud
- ✅ Clientes majoritariamente do setor financeiro
- ✅ Produtos: IBM, Segurança Lógica, Cloud, Hardware
- ⚠️ Alta volatilidade ano a ano
- ⚠️ Sensível a crises econômicas
- ⚠️ Concentração em grandes contratos

**Viabilidade do TCC:**
- ✅ **ALTAMENTE VIÁVEL**
- ✅ Dados suficientes para 5 módulos preditivos
- ✅ Problema de negócio claro e mensurável
- ✅ Impacto financeiro significativo
- ✅ Metodologia adequada (XGBoost, time-series)

---

## 🔄 Atualizações Necessárias na Documentação

### Arquivos a Atualizar:

1. **README.md**
   - Trocar R$ 1,99 B → R$ 994,6 M
   - Atualizar tabelas de faturamento
   - Corrigir estatísticas (média, crescimento)

2. **ANALISE_EXPLORATORIA_INICIAL.md**
   - Seção 3 (Análise Financeira)
   - Seção 8 (Estatísticas-chave)

3. **RESUMO_EXECUTIVO.md**
   - Principais números
   - Impacto esperado (recalcular baseado em R$ 994 M)

4. **LEIA_ME.txt**
   - Atualizar números principais

---

## ✅ CHECKLIST DE VALIDAÇÃO

Antes de prosseguir com o TCC, confirme:

- [ ] Valores de faturamento corretos (linha 969)
- [ ] Dataset limpo (961 registros, excluindo linha de total)
- [ ] Interpretação correta: cada linha = cliente × produto × ano
- [ ] 2026 usado apenas para validação (não para treino)
- [ ] Features temporais planejadas
- [ ] Limitações documentadas (sem dados mensais, sem contratos explícitos)

---

**Documento atualizado em:** 19 de Fevereiro de 2026  
**Status:** ✅ Dados corrigidos e validados  
**Próxima ação:** Atualizar documentação principal com valores corretos
