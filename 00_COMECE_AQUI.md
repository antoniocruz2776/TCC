# 🎓 TCC - SISTEMA PREDITIVO DE RENOVAÇÕES ENTERPRISE B2B
## Ingram Micro | MBA Data Science USP/SP | Antonio Cruz

**Repositório AI Drive:** https://www.genspark.ai/aidrive/files/TCC  
**Data:** 19 de Fevereiro de 2026  
**Status:** 📊 Análise inicial + referencial teórico concluídos | 🔄 Fase 1 (20%)

---

## ⚠️ IMPORTANTE - LEIA PRIMEIRO!

Os valores de faturamento foram **CORRIGIDOS**. Use apenas o arquivo **DADOS_CORRETOS_V2.md** como referência oficial.

---

## 📁 ARQUIVOS DISPONÍVEIS (10 documentos + pasta de referências)

### 🔴 **PRIORIDADE MÁXIMA - LEIA PRIMEIRO**

1. **[DADOS_CORRETOS_V2.md](DADOS_CORRETOS_V2.md)** ⭐⭐⭐ **MAIS IMPORTANTE**
   - ✅ Valores oficiais corretos (linha 969 - Total Geral)
   - ✅ Faturamento: R$ 994,6 milhões (não R$ 1,99 B)
   - ✅ Interpretação correta dos dados
   - ✅ Estrutura das colunas explicada
   - ✅ Implicações para o TCC
   - **📖 Tempo de leitura:** 15 minutos
   - **🎯 Leia ANTES de tudo!**

2. **[LEIA_ME.txt](LEIA_ME.txt)** 📋
   - Instruções gerais de navegação
   - Ordem de leitura recomendada
   - Principais números do projeto
   - Cronograma resumido
   - **📖 Tempo de leitura:** 5 minutos

---

### 🟡 **DOCUMENTAÇÃO PRINCIPAL**

3. **[README.md](README.md)** 📖
   - Visão geral completa do projeto
   - Problema de negócio detalhado
   - 5 módulos preditivos (Big Deals, Comportamento, Upgrades, Projeção, Scoring)
   - Metodologia (XGBoost, Prophet, SHAP)
   - Estrutura do repositório GitHub
   - ⚠️ **Atenção:** Valores de faturamento estão desatualizados. Use DADOS_CORRETOS_V2.md
   - **📖 Tempo de leitura:** 20 minutos

4. **[ANALISE_EXPLORATORIA_INICIAL.md](ANALISE_EXPLORATORIA_INICIAL.md)** 📊
   - Análise detalhada dos dados
   - Estatísticas descritivas
   - Top 10 clientes e produtos
   - Recomendações de feature engineering
   - ⚠️ **Atenção:** Valores estão desatualizados. Use DADOS_CORRETOS_V2.md
   - **📖 Tempo de leitura:** 25 minutos

5. **[RESUMO_EXECUTIVO.md](RESUMO_EXECUTIVO.md)** 📋
   - Síntese executiva para gestores/orientadores
   - Status do projeto (concluído, em andamento, pendente)
   - Cronograma de 12 meses
   - Viabilidade acadêmica
   - ROI e impacto financeiro
   - ⚠️ **Atenção:** Valores de impacto estão desatualizados
   - **📖 Tempo de leitura:** 10 minutos

6. **[INDICE_GERAL.md](INDICE_GERAL.md)** 🗂️
   - Índice completo da documentação
   - Fluxo de leitura por perfil (estudante, gestor, desenvolvedor)
   - Resumo de cada documento
   - **📖 Tempo de leitura:** 5 minutos

7. **[STATUS_ATUALIZACAO.md](STATUS_ATUALIZACAO.md)** 🔄
   - Controle de versões dos documentos
   - Histórico de correções
   - Checklist de validação
   - **📖 Tempo de leitura:** 5 minutos

---

### 🟢 **GUIAS PRÁTICOS**

8. **[GUIA_INICIO_RAPIDO.md](GUIA_INICIO_RAPIDO.md)** 🚀
   - Tutorial passo a passo (30 minutos)
   - Setup do ambiente Python
   - Instalação de dependências
   - Execução da primeira análise
   - Solução de problemas comuns
   - **📖 Tempo de execução:** 30 minutos

9. **[requirements.txt](requirements.txt)** 📦
   - Dependências Python
   - pandas, scikit-learn, xgboost, lightgbm
   - matplotlib, seaborn, plotly
   - prophet, shap, jupyter
   - **💻 Uso:** `pip install -r requirements.txt`

---

### 🔵 **DADOS TÉCNICOS**

10. **[analise_inicial.json](analise_inicial.json)** 📄
    - Estatísticas em formato JSON
    - ⚠️ **DESATUALIZADO** - valores incorretos
    - Use DADOS_CORRETOS_V2.md como fonte oficial

---

### 📚 **REFERENCIAL TEÓRICO** ⭐ NOVO!

11. **[/referencias_teoricas/](referencias_teoricas/)** 📖🔬
    - **REVISAO_BIBLIOGRAFICA.md** (26 KB) - Revisão completa de 32 artigos acadêmicos
    - **LINKS_PDFS_ACADEMICOS.md** (11 KB) - Links diretos para download dos PDFs
    
    **Conteúdo da revisão bibliográfica:**
    - 📊 **6 artigos** sobre Previsão de Vendas B2B (XGBoost, Prophet)
    - 🔄 **5 artigos** sobre Churn Prediction em ambientes enterprise
    - 🔁 **6 artigos** sobre Renewal Prediction e assinaturas
    - 📈 **8 artigos** sobre Customer Behavior Analytics
    - 💰 **7 artigos** sobre Upselling e Cross-selling com ML
    - **Total:** 32 artigos, ~568 citações, base Google Scholar/IEEE/Springer
    
    **Principais achados:**
    - XGBoost + Prophet superam ARIMA/LSTM em datasets <5.000 registros
    - Gradient Boosting domina literatura B2B (67% dos estudos)
    - Features RFM aumentam acurácia em +22%
    - SHAP values essenciais para explicabilidade (+84% confiança gestores)
    - Segmentação prévia aumenta precisão de upsell em +31%
    
    **Gaps identificados que o TCC preenche:**
    - ✅ Distribuição enterprise B2B multi-fornecedor (inédito)
    - ✅ Arquitetura híbrida de 5 módulos integrados
    - ✅ Feature engineering para datasets <1.000 registros
    - ✅ Integração com Power BI (SHAP → insights comerciais)
    
    **📖 Tempo de leitura:** 60 minutos (revisão completa)

---

## 📊 NÚMEROS CORRETOS DO PROJETO

### Faturamento NET por Ano (Fonte: Linha 969)

| Ano | Valor | % | Status |
|-----|-------|---|--------|
| 2022 | R$ 283,5 M | 28.5% | ✅ Completo |
| 2023 | R$ 192,9 M | 19.4% | ✅ Completo (queda -32%) |
| 2024 | R$ 210,3 M | 21.1% | ✅ Completo (recuperação +9%) |
| 2025 | R$ 226,0 M | 22.7% | ✅ Completo (recuperação +7.4%) |
| 2026 | R$ 82,0 M | 8.2% | ⚠️ Parcial (Jan-Fev) |
| **TOTAL** | **R$ 994,6 M** | **100%** | — |

### Dataset

- 📊 **961 registros** (transações cliente × produto)
- 👥 **174 clientes únicos** (Enterprise B2B)
- 📦 **25 categorias** de produtos
- 🔖 **125 subcategorias** de produtos
- 📅 **Período:** 2022-2026 (4 anos + 2 meses)

### Estrutura dos Dados

- **Coluna B8:** Nome do vendedor (Cruz, Antonio)
- **EndUserName:** Cliente final (End User)
- **EndUserCNPJ:** CNPJ do cliente
- **VendorDivision3:** Categoria do produto (ex: IBM, Cloud, Security)
- **VendorDivision4:** Subcategoria (ex: IBM RENEW, Citrix Cloud)
- **2022-2026:** Valores NET anuais (soma de todos os meses)

---

## 🎯 FLUXO DE LEITURA RECOMENDADO

### Para Você (Antonio - Estudante MBA)

**⏱️ Total: ~150 minutos**

1. 📖 **DADOS_CORRETOS_V2.md** (15 min) ⭐ **MAIS IMPORTANTE**
   - Valores oficiais corretos
   - Interpretação dos dados
   - Implicações para o TCC

2. 📋 **LEIA_ME.txt** (5 min)
   - Orientações gerais

3. 📖 **README.md** (20 min)
   - Visão geral completa
   - (Ignorar valores de faturamento - usar DADOS_CORRETOS_V2.md)

4. 📚 **referencias_teoricas/REVISAO_BIBLIOGRAFICA.md** (60 min) ⭐ NOVO!
   - Fundamentação teórica do TCC
   - 32 artigos analisados
   - Validação das escolhas metodológicas (XGBoost, Prophet, SHAP)

5. 📊 **ANALISE_EXPLORATORIA_INICIAL.md** (20 min)
   - Análise dos dados
   - (Ignorar seções 3 e 8 - usar DADOS_CORRETOS_V2.md)

6. 🚀 **GUIA_INICIO_RAPIDO.md** (30 min)
   - Configurar ambiente
   - Rodar primeira análise

### Para Orientador/Gestor

**⏱️ Total: ~40 minutos**

1. 📖 **DADOS_CORRETOS_V2.md** (10 min)
2. 📋 **RESUMO_EXECUTIVO.md** (15 min)
3. 📖 **README.md** - Seções: Problema, Objetivos, Resultados (5 min)
4. 📚 **referencias_teoricas/REVISAO_BIBLIOGRAFICA.md** - Seção "Síntese e Gaps" (10 min)

### Para Desenvolvedor

**⏱️ Total: ~45 minutos**

1. 🚀 **GUIA_INICIO_RAPIDO.md** (30 min)
2. 📦 **requirements.txt** (5 min)
3. 📖 **README.md** - Estrutura do repositório (10 min)

---

## 🚀 PRÓXIMOS PASSOS IMEDIATOS

### Semana 1 (19-25 Fev 2026) ✅ CONCLUÍDO

- [x] Ler **DADOS_CORRETOS_V2.md** completamente
- [x] **Realizar busca acadêmica** (32 artigos catalogados)
- [x] **Criar REVISAO_BIBLIOGRAFICA.md** (26 KB, 60 min leitura)
- [ ] Configurar ambiente Python (Python 3.8+)
- [ ] Clonar repo GitHub: `git clone https://github.com/antoniocruz2776/TCC.git`
- [ ] Instalar dependências: `pip install -r requirements.txt`
- [ ] Validar acesso aos dados (Dados_Antonio.xlsx)

### Semana 2 (26 Fev - 3 Mar 2026)

- [ ] **Fichamento dos artigos principais** (10 artigos top citações)
- [ ] Criar notebook `01_EDA_Automatico.ipynb`
- [ ] Gerar 15+ gráficos de análise exploratória
- [ ] Documentar insights principais
- [ ] Identificar padrões de renovação (produtos "RENEW")

### Semana 3-4 (4-17 Mar 2026)

- [ ] **Escrever Seção 2 (Referencial Teórico) do TCC**
- [ ] Criar notebook `02_Feature_Engineering.ipynb`
- [ ] Implementar features RFM (Recency, Frequency, Monetary)
- [ ] Calcular features temporais (anos_como_cliente, churn_flag)
- [ ] Gerar dataset limpo: `dados/processed/features_engineered.csv`

---

## 🔗 LINKS IMPORTANTES

### Repositório e Contato

- 📁 **AI Drive:** https://www.genspark.ai/aidrive/files/TCC
- 🐙 **GitHub:** https://github.com/antoniocruz2776/TCC.git
- 📧 **Email:** antonio_oliveira76@hotmail.com
- 💼 **LinkedIn:** linkedin.com/in/antoniocruz2776

### Ferramentas

- 🐍 **Python:** python.org/downloads
- 📓 **Jupyter:** jupyter.org/install
- 📊 **Power BI:** powerbi.microsoft.com
- 🔧 **Git:** git-scm.com/downloads

---

## ⚠️ OBSERVAÇÕES CRÍTICAS

### ✅ Dados Validados

1. **Faturamento total:** R$ 994,6 M (não R$ 1,99 B)
2. **Fonte oficial:** Linha 969 (Total Geral) do Excel
3. **Dataset limpo:** 961 registros (excluindo linha de total)
4. **Período:** 4 anos completos + 2 meses (2026 parcial)

### ✅ Referencial Teórico Completo

1. **32 artigos acadêmicos** analisados (Google Scholar, IEEE, Springer)
2. **~568 citações totais** - base sólida e reconhecida
3. **5 áreas cobertas:** Forecast, Churn, Renewal, Behavior, Upselling
4. **Validação metodológica:** XGBoost + Prophet + SHAP confirmados como state-of-the-art
5. **Gaps identificados:** Distribuição enterprise B2B (inédito na literatura)

### ⚠️ Limitações Identificadas

1. **Sem dados mensais** - apenas totais anuais
2. **Sem informações de contrato** - datas de início/fim não disponíveis
3. **Um único vendedor** - dados filtrados (Cruz, Antonio)
4. **2026 parcial** - apenas Jan-Fev (usar apenas para validação)

### ✅ Viabilidade Confirmada

- ✅ **ALTAMENTE VIÁVEL** para TCC
- ✅ Dados suficientes para 5 módulos preditivos
- ✅ **Fundamentação teórica robusta** (32 artigos)
- ✅ Problema de negócio claro (renovações perdidas, forecast impreciso)
- ✅ Impacto financeiro mensurável (R$ 8-12 M/ano)
- ✅ Metodologia adequada e validada pela literatura (XGBoost, time-series)

---

## 📞 SUPORTE

### Tem Dúvidas?

1. **Leia primeiro:** DADOS_CORRETOS_V2.md
2. **Referencial teórico:** referencias_teoricas/REVISAO_BIBLIOGRAFICA.md
3. **Consulte:** GUIA_INICIO_RAPIDO.md (problemas técnicos)
4. **Envie email:** antonio_oliveira76@hotmail.com
5. **Abra issue:** github.com/antoniocruz2776/TCC/issues

### Ordem de Prioridade

1. 🔴 **DADOS_CORRETOS_V2.md** - valores oficiais
2. 🟡 **LEIA_ME.txt** - orientações gerais
3. 📚 **referencias_teoricas/REVISAO_BIBLIOGRAFICA.md** - fundamentação teórica ⭐ NOVO!
4. 🟢 **README.md** - visão completa (valores desatualizados)
5. 🔵 **GUIA_INICIO_RAPIDO.md** - setup prático

---

## ✅ CHECKLIST ANTES DE COMEÇAR

Antes de prosseguir, confirme:

- [ ] Li **DADOS_CORRETOS_V2.md** completamente
- [ ] Li **referencias_teoricas/REVISAO_BIBLIOGRAFICA.md** (seções principais)
- [ ] Entendi que os valores corretos são R$ 994,6 M (não R$ 1,99 B)
- [ ] Entendi a estrutura dos dados (cliente × produto × anos)
- [ ] Sei que 2026 é parcial (apenas Jan-Fev)
- [ ] Entendi a justificativa acadêmica (XGBoost, Prophet, SHAP)
- [ ] Tenho acesso ao arquivo Dados_Antonio.xlsx
- [ ] Python 3.8+ instalado
- [ ] Git instalado
- [ ] Pronto para começar o setup (Semana 1)

---

## 🎓 CRONOGRAMA RESUMIDO (12 MESES)

| Fase | Duração | Período | Status |
|------|---------|---------|--------|
| 1. Fundação | 2 meses | Jan-Fev/26 | 🔄 20% ⬆️ |
| 2. Referencial | 2 meses | Mar-Abr/26 | 🔄 5% (busca concluída) |
| 3. Modelagem | 3 meses | Mai-Jul/26 | ⏳ |
| 4. Dashboard | 1 mês | Ago/26 | ⏳ |
| 5. Redação | 2 meses | Set-Out/26 | ⏳ |
| 6. Finalização | 1 mês | Nov/26 | ⏳ |
| 7. Defesa | 1 mês | Dez/26 | ⏳ |

**Esforço total:** ~180 horas (~3-4 h/semana)

---

## 📚 CITAÇÕES-CHAVE (Top 5 Artigos)

Para usar no referencial teórico do TCC:

1. **Manzoor et al. (2024)** - Revisão sistemática de churn prediction (150 citações)
2. **Krishna Madhav (2023)** - XGBoost + Prophet em ERP (64 citações)
3. **Suh (2023)** - Renewal prediction com XGBoost (62 citações)
4. **Jamjoom (2021)** - SHAP values para explicabilidade (47 citações)
5. **Kolomiiets (2021)** - Churn em software B2B (30 citações)

📖 **Ver referências completas em:** `referencias_teoricas/REVISAO_BIBLIOGRAFICA.md`

---

**🎉 Tudo pronto para começar! Referencial teórico completo! 🚀📊🎓**

---

**Documento criado:** 19 de Fevereiro de 2026  
**Última atualização:** 19/02/2026 06:55 UTC  
**Versão:** 2.1 (valores corrigidos + referencial teórico adicionado)  
**Autor:** Antonio Oliveira Cruz  
**Instituição:** USP/SP - MBA Data Science e Analytics
