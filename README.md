# Sistema Preditivo de Renovações Enterprise B2B - Ingram Micro
## TCC - MBA Data Science e Analytics | USP/SP | 2º Semestre 2025

**Status:** 🟡 Fase 1 - Fundação (10%) | **Faturamento Total:** R$ 994,6 milhões

---

## 📊 RESUMO EXECUTIVO

**Dados do Projeto (Valores Oficiais - Linha 969):**
- 💰 **Faturamento:** R$ 994,646,305 (2022-2026)
- 📊 **Registros:** 961 transações (cliente × produto × ano)
- 👥 **Clientes:** 174 únicos (Enterprise B2B)
- 📦 **Produtos:** 25 categorias, 125 subcategorias
- 📅 **Período:** 4 anos completos + 2 meses (2026 parcial)

**Faturamento por Ano:**
- 2022: R$ 283,5 M (28.5%) ✅
- 2023: R$ 192,9 M (19.4%) 📉 -32%
- 2024: R$ 210,3 M (21.1%) 📈 +9%
- 2025: R$ 226,0 M (22.7%) 📈 +7.4%
- 2026: R$ 82,0 M (8.2%) ⚠️ Parcial

---

## 🔴 PROBLEMA DE NEGÓCIO

**Contexto:** Gestão manual de contratos Enterprise B2B (tickets médios R$ 228 M/ano)

**Dores Críticas:**
- 30% renovações perdidas → Meta: 10%
- 30-40% erro de forecast → Meta: 15-20%
- 5-8% conversão upgrades → Meta: 12-15%
- 8h/semana preparação → Meta: 1h/semana

**Perda Anual:** R$ 8-12 milhões

---

## 🎯 SOLUÇÃO PROPOSTA

Sistema ML com 5 módulos:
1. **Big Deals** - Identificar renovações em risco
2. **Comportamento** - Classificar 5 perfis de clientes
3. **Upgrades** - Detectar oportunidades tecnológicas
4. **Projeção** - Prever compras futuras (12 meses)
5. **Priorização** - Scoring comercial automático

**Tecnologias:** XGBoost, Prophet, SHAP, Power BI

---

## 📊 ESTRUTURA DOS DADOS

**Colunas Principais:**
- B8: Nome vendedor (Cruz, Antonio)
- EndUserName: Cliente final
- EndUserCNPJ: CNPJ cliente
- VendorDivision3: Categoria produto (25 tipos)
- VendorDivision4: Subcategoria produto (125 tipos)
- 2022-2026: Valores NET anuais (soma mensal)

**Top 5 Clientes:**
1. Câmara Interbancária - R$ 17,6 M
2. Nu Pagamentos - R$ 14,7 M
3. Banco Bradesco - R$ 14,3 M
4. Banco Itaú - R$ 10,3 M
5. PicPay - R$ 9,7 M

**Top 5 Categorias:**
1. Logical Security (18.6%)
2. IBM (13.9%)
3. Hardware Volume (13.1%)
4. Cloud (10.7%)
5. Dell Client (6.2%)

---

## 🔬 METODOLOGIA

**Feature Engineering:**
- RFM (Recency, Frequency, Monetary)
- Features temporais (anos_como_cliente, churn_flag)
- Flags de comportamento (renovação, upgrade, expansão)

**Validação:** Time-Series Split
- Treino: 2022-2023 (70%)
- Validação: 2024 (15%)
- Teste: 2025 (15%)
- Holdout: 2026 (validação real)

**Modelos:** XGBoost (principal), LightGBM, Prophet

---

## 📈 RESULTADOS ESPERADOS

**Impacto de Negócio:**
- Taxa renovação: 70% → 85-90%
- Erro forecast: 40% → 15-20%
- Conversão upgrades: 5-8% → 12-15%
- Tempo preparação: 8h → 1h/semana
- **Ganho anual: R$ 8-12 M**

**ROI:**
- Investimento: R$ 200 K
- Retorno anual: R$ 8-12 M
- **ROI: 4.000-6.000%**
- **Payback: < 3 meses**

---

## 📅 CRONOGRAMA (12 MESES)

| Fase | Período | Status |
|------|---------|--------|
| 1. Fundação | Jan-Fev/26 | 🔄 10% |
| 2. Referencial | Mar-Abr/26 | ⏳ |
| 3. Modelagem | Mai-Jul/26 | ⏳ |
| 4. Dashboard | Ago/26 | ⏳ |
| 5. Redação | Set-Out/26 | ⏳ |
| 6. Finalização | Nov/26 | ⏳ |
| 7. Defesa | Dez/26 | ⏳ |

**Esforço:** ~180h (~3-4h/semana)

---

## ⚙️ INSTALAÇÃO RÁPIDA

```bash
# 1. Clonar repositório
git clone https://github.com/antoniocruz2776/TCC.git
cd TCC

# 2. Criar ambiente virtual
python3 -m venv venv
source venv/bin/activate

# 3. Instalar dependências
pip install -r scripts/requirements.txt

# 4. Colocar dados em dados/raw/
# Dados_Antonio.xlsx

# 5. Executar notebooks
jupyter notebook notebooks/01_EDA_Automatico.ipynb
```

---

## 📁 ESTRUTURA DO REPOSITÓRIO

```
TCC/
├── dados/             # Dados (não versionado)
├── notebooks/         # 7 notebooks Jupyter
├── src/               # Código modular Python
├── modelos/           # Modelos treinados (.pkl)
├── dashboard/         # Power BI
├── templates_texto/   # Templates TCC
├── defesa/            # Material defesa
└── docs/              # Documentação completa
```

---

## 👤 AUTOR

**Antonio Oliveira Cruz**
- 📧 antonio_oliveira76@hotmail.com
- 💼 linkedin.com/in/antoniocruz2776
- 🐙 github.com/antoniocruz2776
- 🏢 Ingram Micro Brasil
- 🎓 MBA Data Science USP/SP
- 📅 Entrega: Dez/2026

---

## 🔗 LINKS IMPORTANTES

- 📁 **Documentação:** https://www.genspark.ai/aidrive/files/TCC
- 🐙 **GitHub:** https://github.com/antoniocruz2776/TCC.git
- 📖 **Leia primeiro:** 00_COMECE_AQUI.md
- ✅ **Valores oficiais:** DADOS_CORRETOS_V2.md

---

**Última atualização:** 19/02/2026  
**Versão:** 2.0 (valores corrigidos)  
**Fonte oficial:** Linha 969 - Total Geral  
**Licença:** MIT
