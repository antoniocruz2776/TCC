# RESUMO EXECUTIVO - TCC Antonio Cruz
## Sistema Preditivo de Renovações Enterprise B2B - Ingram Micro

**Data:** 19 de Fevereiro de 2026  
**Autor:** Antonio Oliveira Cruz  
**Instituição:** USP/SP - MBA Data Science e Analytics  
**Prazo de Entrega:** Dezembro/2026

---

## 📋 Status do Projeto

### ✅ Concluído (19/02/2026)

1. **Análise Exploratória Inicial dos Dados**
   - Arquivo analisado: `Dados_Antonio.xlsx` (51.03 MB)
   - Total de registros: 962
   - Período: 2022-2026 (5 anos)
   - Faturamento total: R$ 1,99 bilhões
   - Clientes únicos: 174
   - Categorias de produtos: 25
   - Subcategorias: 125

2. **Documentação Criada**
   - ✅ README.md completo (visão geral do projeto)
   - ✅ ANALISE_EXPLORATORIA_INICIAL.md (14.8 KB)
   - ✅ GUIA_INICIO_RAPIDO.md (8.2 KB)
   - ✅ requirements.txt (dependências Python)
   - ✅ RESUMO_EXECUTIVO.md (este arquivo)

3. **Estrutura do Repositório GitHub**
   - URL: https://github.com/antoniocruz2776/TCC.git
   - Estrutura de pastas definida
   - .gitignore configurado

### 🔄 Em Andamento

- **Próximo passo:** Criação dos notebooks de EDA e Feature Engineering

### ⏳ Pendente

- Notebooks Jupyter (7 notebooks)
- Scripts Python modulares
- Modelos de ML treinados
- Dashboard Power BI
- Templates de texto para TCC
- Material de defesa

---

## 🎯 Problema de Negócio

### Contexto
A Ingram Micro, no segmento Enterprise B2B, gerencia contratos de alto valor (tickets médios de R$ 1,4 milhão) de forma **manual** através de planilhas Excel, resultando em:

- **30% de renovações perdidas** (meta: reduzir para 10%)
- **30-40% de erro nas previsões** (meta: melhorar para 15-20%)
- **5-8% de conversão em upgrades** (meta: aumentar para 12-15%)
- **8 horas/semana de preparação manual** (meta: reduzir para 1 hora)

**Impacto financeiro:** Perda anual estimada de R$ 14-18 milhões.

### Solução Proposta
Sistema preditivo de Machine Learning com 5 módulos:

1. **Big Deals** - Identificar renovações nos próximos 90 dias
2. **Comportamento** - Classificar clientes em 5 perfis
3. **Upgrades** - Detectar oportunidades de migração tecnológica
4. **Projeção** - Prever compras futuras (12 meses)
5. **Priorização** - Scoring comercial (Valor × Probabilidade × Urgência)

---

## 📊 Análise dos Dados

### Qualidade Geral: ✅ ALTA

**Pontos Fortes:**
- ✅ Volume substancial (R$ 1,99 B em 5 anos)
- ✅ Estrutura clara e organizada
- ✅ Subcategorias 99.9% preenchidas
- ✅ Período adequado para séries temporais
- ✅ Base de clientes pulverizada (sem dependência crítica)

**Desafios Identificados:**
- ⚠️ Missing values altos em identificação de clientes (81.9%)
- ⚠️ Dados de vendedores insuficientes (99.8% missing)
- ⚠️ 2026 incompleto (apenas 7.3% preenchido)
- ⚠️ Formato wide (precisa transformação para long)

### Principais Estatísticas

#### Faturamento por Ano

| Ano | Total | Transações | Ticket Médio |
|-----|-------|------------|--------------|
| 2022 | R$ 567 M | 387 | R$ 1,46 M |
| 2023 | R$ 386 M | 411 | R$ 939 K |
| 2024 | R$ 421 M | 371 | R$ 1,13 M |
| 2025 | R$ 452 M | 328 | R$ 1,38 M |
| 2026 | R$ 164 M | 70 | R$ 2,34 M |

**Tendências:**
- 📈 Ticket médio crescente (+60% de 2023 para 2026)
- 📉 Volume de transações decrescente (-15% ao ano)
- 💡 Consolidação: menos transações, maiores valores

#### Top 5 Clientes

1. CAMARA INTERBANCARIA DE PAGAMENTOS - R$ 17,6 M
2. NU PAGAMENTOS SA - R$ 14,7 M
3. BANCO BRADESCO SA - R$ 14,3 M
4. BANCO ITAU S/A - R$ 10,3 M
5. PICPAY INSTITUIÇÃO DE PAGAMENTO SA - R$ 9,7 M

**Insight:** 70% dos top 10 clientes são do setor financeiro.

#### Top 5 Categorias de Produtos

1. Logical Security - 99 registros (18.6%)
2. IBM - 74 registros (13.9%)
3. Hardware Volume - 70 registros (13.1%)
4. Cloud - 57 registros (10.7%)
5. Dell Client - 33 registros (6.2%)

**Insight:** Foco em software empresarial e segurança.

---

## 🔬 Metodologia

### Algoritmos Selecionados

| Módulo | Tipo | Algoritmo Principal | Métrica |
|--------|------|---------------------|---------|
| 1 - Big Deals | Classificação | XGBoost | F1-Score |
| 2 - Comportamento | Multi-classe | XGBoost | Accuracy |
| 3 - Upgrades | Classificação | XGBoost | Precision |
| 4 - Projeção | Regressão | XGBoost + Prophet | MAPE |
| 5 - Scoring | Regressão | XGBoost | R² |

**Justificativa da escolha do XGBoost:**
- ✅ Estado da arte em dados tabulares
- ✅ Lida bem com missing values
- ✅ Interpretabilidade via SHAP
- ✅ Robusto a outliers
- ✅ Suporta paralelização

### Validação

**Estratégia:** Time-Series Split (sem cross-validation)

| Conjunto | Período | % | Uso |
|----------|---------|---|-----|
| Treino | 2022-2023 | 70% | Treinamento |
| Validação | 2024 | 15% | Tuning |
| Teste | 2025 | 15% | Avaliação final |
| Holdout | 2026 | — | Validação real |

**Justificativa:** Respeita a ordem temporal, evita data leakage.

---

## 📈 Resultados Esperados

### Métricas Técnicas

| Módulo | Métrica | Baseline | Meta | Melhor Cenário |
|--------|---------|----------|------|----------------|
| Big Deals | F1-Score | 0.60 | 0.80 | 0.85+ |
| Comportamento | Accuracy | 0.50 | 0.70 | 0.75+ |
| Upgrades | Precision | 0.40 | 0.65 | 0.70+ |
| Projeção | MAPE | 25% | 18% | 15% |
| Scoring | R² | 0.50 | 0.70 | 0.80+ |

### Impacto de Negócio

| Métrica | Atual | Meta | Ganho Anual |
|---------|-------|------|-------------|
| Taxa de renovação | 70% | 85-90% | +R$ 8-10 M |
| Conversão de upgrades | 5-8% | 12-15% | +R$ 4-6 M |
| Eficiência operacional | 8h/sem | 1h/sem | +R$ 2 M |
| **Total** | — | — | **+R$ 14-18 M/ano** |

### ROI

- **Investimento:** R$ 200.000
- **Retorno anual:** R$ 14 M
- **ROI:** 7.000%
- **Payback:** < 2 meses

---

## 📅 Cronograma (12 meses)

| Fase | Duração | Período | Status |
|------|---------|---------|--------|
| **1. Fundação** | 2 meses | Jan-Fev/26 | 🔄 10% |
| **2. Referencial** | 2 meses | Mar-Abr/26 | ⏳ |
| **3. Modelagem** | 3 meses | Mai-Jul/26 | ⏳ |
| **4. Dashboard** | 1 mês | Ago/26 | ⏳ |
| **5. Redação** | 2 meses | Set-Out/26 | ⏳ |
| **6. Finalização** | 1 mês | Nov/26 | ⏳ |
| **7. Defesa** | 1 mês | Dez/26 | ⏳ |

**Esforço total:** ~180 horas (~3-4 h/semana)

---

## 📝 Próximos Passos Imediatos

### Semana 1 (19-25 Fev 2026)
- [ ] Configurar ambiente Python local
- [ ] Clonar repositório GitHub
- [ ] Instalar dependências (requirements.txt)
- [ ] Executar script de análise inicial
- [ ] Validar qualidade dos dados

### Semana 2 (26 Fev - 3 Mar 2026)
- [ ] Criar notebook `01_EDA_Automatico.ipynb`
- [ ] Gerar 15+ gráficos exploratórios
- [ ] Documentar insights principais
- [ ] Identificar outliers e anomalias

### Semana 3-4 (4-17 Mar 2026)
- [ ] Criar notebook `02_Feature_Engineering.ipynb`
- [ ] Implementar features temporais
- [ ] Calcular RFM
- [ ] Gerar dataset para modelagem
- [ ] Salvar em `dados/processed/features_engineered.csv`

---

## 🎓 Viabilidade Acadêmica

### ✅ ALTAMENTE VIÁVEL

**Justificativas:**

1. **Dados suficientes e de qualidade**
   - 962 registros × 5 anos = base robusta
   - R$ 1,99 B em transações reais
   - 174 clientes para validação

2. **Problema real e relevante**
   - Impacto financeiro mensurável (R$ 14-18 M/ano)
   - Aplicação direta em grande empresa
   - Generalização para outros segmentos B2B

3. **Complexidade adequada para MBA**
   - 5 módulos preditivos distintos
   - Múltiplos algoritmos (XGBoost, Prophet, LSTM)
   - Interpretabilidade com SHAP
   - Dashboard executivo em Power BI

4. **Referencial teórico sólido**
   - Data Science em negócios
   - ML para previsão de vendas
   - Gestão de contratos B2B
   - ROI de projetos de IA

5. **Entregáveis completos**
   - Código open-source (GitHub)
   - Dataset anonimizado
   - Dashboard interativo
   - Relatório executivo
   - Apresentação de defesa

---

## 🔗 Links e Recursos

### Repositório GitHub
- **URL:** https://github.com/antoniocruz2776/TCC.git
- **Branch principal:** `main`
- **Licença:** MIT

### Documentação
- 📖 [README.md](README.md) - Visão geral completa
- 📊 [ANALISE_EXPLORATORIA_INICIAL.md](ANALISE_EXPLORATORIA_INICIAL.md) - Análise detalhada
- 🚀 [GUIA_INICIO_RAPIDO.md](GUIA_INICIO_RAPIDO.md) - Setup em 30 minutos

### Contato
- 📧 Email: antonio_oliveira76@hotmail.com
- 💼 LinkedIn: linkedin.com/in/antoniocruz2776
- 🐙 GitHub: github.com/antoniocruz2776

---

## ⚠️ Riscos e Mitigações

| Risco | Probabilidade | Impacto | Mitigação |
|-------|---------------|---------|-----------|
| Dados insuficientes para um módulo | Baixa | Alto | Reduzir escopo para 3-4 módulos |
| Desempenho dos modelos abaixo da meta | Média | Médio | Ensembles, feature engineering avançado |
| Atraso no cronograma | Média | Médio | Buffer de 2 semanas na fase de redação |
| Problemas técnicos (hardware) | Baixa | Baixo | Usar Google Colab com GPU gratuita |
| Orientador não disponível | Baixa | Médio | Solicitar orientador alternativo |

---

## ✅ Checklist de Entregáveis

### Documentação Atual (19/02/2026)
- [x] README.md completo
- [x] ANALISE_EXPLORATORIA_INICIAL.md
- [x] GUIA_INICIO_RAPIDO.md
- [x] requirements.txt
- [x] RESUMO_EXECUTIVO.md

### A Fazer
- [ ] 7 notebooks Jupyter
- [ ] Código-fonte modular (src/)
- [ ] 5 modelos treinados (.pkl)
- [ ] Dashboard Power BI (.pbix)
- [ ] 5 capítulos do TCC (Word)
- [ ] Slides de defesa (PowerPoint)
- [ ] 30 perguntas da banca + respostas
- [ ] Relatório executivo (PDF)

---

## 🎯 Conclusão

### Avaliação Geral: ✅ PROJETO VIÁVEL E PROMISSOR

**Pontos de Destaque:**
1. ✅ Dados reais e de alta qualidade (R$ 1,99 B)
2. ✅ Problema de negócio claro e mensurável
3. ✅ Impacto financeiro significativo (R$ 14-18 M/ano)
4. ✅ Metodologia robusta (XGBoost, Prophet, SHAP)
5. ✅ Escopo adequado para MBA (5 módulos)
6. ✅ Documentação completa e organizada
7. ✅ Cronograma realista (12 meses, 3-4 h/semana)

**Recomendação:** PROSSEGUIR COM O PROJETO.

**Próxima ação:** Executar Fase 1 (Fundação) nas próximas 2 semanas.

---

**Documento gerado em:** 19 de Fevereiro de 2026  
**Última atualização:** 19/02/2026  
**Status:** Fase 1 - Fundação (10% concluído)  
**Próxima revisão:** 3 de Março de 2026 (após EDA)

---

**Autor:** Antonio Oliveira Cruz  
**Orientador:** [A definir]  
**Instituição:** USP/SP - MBA Data Science e Analytics  
**Prazo:** Dezembro/2026
