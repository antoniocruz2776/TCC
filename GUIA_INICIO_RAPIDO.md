# 🚀 Guia de Início Rápido - TCC Antonio Cruz

**Tempo estimado:** 30 minutos  
**Objetivo:** Configurar o ambiente e executar a primeira análise

---

## ✅ Checklist de Início

Antes de começar, certifique-se de ter:

- [ ] Python 3.8+ instalado
- [ ] Git instalado
- [ ] Arquivo `Dados_Antonio.xlsx` (51 MB)
- [ ] Conta no GitHub configurada
- [ ] 10 GB de espaço livre em disco

---

## 📥 Passo 1: Clonar o Repositório (2 min)

```bash
# Clone o repositório
git clone https://github.com/antoniocruz2776/TCC.git

# Entre no diretório
cd TCC

# Verifique a estrutura
ls -la
```

**O que você deve ver:**
```
TCC/
├── README.md
├── dados/
├── notebooks/
├── src/
├── scripts/
└── ...
```

---

## 🐍 Passo 2: Configurar Ambiente Python (5 min)

### Linux/Mac:

```bash
# Crie ambiente virtual
python3 -m venv venv

# Ative o ambiente
source venv/bin/activate

# Verifique a versão do Python
python --version  # Deve ser 3.8+
```

### Windows:

```bash
# Crie ambiente virtual
python -m venv venv

# Ative o ambiente
venv\Scripts\activate

# Verifique a versão
python --version
```

**✅ Sucesso:** Seu prompt deve mostrar `(venv)` no início.

---

## 📦 Passo 3: Instalar Dependências (3 min)

```bash
# Instale as bibliotecas necessárias
pip install --upgrade pip
pip install -r scripts/requirements.txt

# Verifique instalação
python -c "import pandas, numpy, sklearn, xgboost; print('✅ Instalação OK!')"
```

**Principais bibliotecas instaladas:**
- pandas 1.5.3
- numpy 1.24.0
- scikit-learn 1.2.0
- xgboost 1.7.0
- matplotlib 3.6.0
- seaborn 0.12.0

---

## 📂 Passo 4: Preparar os Dados (2 min)

```bash
# Crie a estrutura de pastas
mkdir -p dados/raw
mkdir -p dados/processed
mkdir -p dados/predictions

# Copie o arquivo de dados
# (Substitua /caminho/para/seu/arquivo pelo caminho real)
cp /caminho/para/Dados_Antonio.xlsx dados/raw/

# Verifique se o arquivo está no lugar
ls -lh dados/raw/
```

**⚠️ IMPORTANTE:** 
- O arquivo `Dados_Antonio.xlsx` **NÃO** está no Git (por segurança)
- Você deve colocá-lo manualmente em `dados/raw/`
- Tamanho esperado: ~51 MB

---

## 🔍 Passo 5: Executar Análise Inicial (10 min)

### Opção A: Usando Jupyter Notebook

```bash
# Inicie o Jupyter
jupyter notebook

# Abra o notebook
# notebooks/01_EDA_Automatico.ipynb

# Execute todas as células: Cell > Run All
```

### Opção B: Usando Google Colab

1. Acesse [colab.research.google.com](https://colab.research.google.com)
2. Faça upload do notebook `notebooks/01_EDA_Automatico.ipynb`
3. Faça upload do arquivo `Dados_Antonio.xlsx`
4. Execute todas as células

### Opção C: Script Python direto

```bash
# Execute o script de análise
python scripts/analise_inicial.py

# Verifique os resultados
cat dados/processed/analise_inicial.json
```

---

## 📊 Passo 6: Visualizar Resultados (5 min)

Após executar a análise, você terá:

### Arquivos gerados:

```bash
dados/processed/
├── analise_inicial.json          # Estatísticas em JSON
├── contratos_limpo.csv           # Dados limpos
└── graficos/                     # 15+ gráficos
    ├── 01_evolucao_vendas.png
    ├── 02_top10_clientes.png
    ├── 03_distribuicao_produtos.png
    └── ...
```

### Visualizar estatísticas:

```bash
# Abra o arquivo JSON
cat dados/processed/analise_inicial.json
```

**Exemplo de saída:**
```json
{
  "registros_totais": "962",
  "clientes_unicos": "174",
  "periodo": "2022-2026 (5 anos)",
  "valor_total_periodo": "1989292607.85",
  "categorias_produto": "25",
  "subcategorias_produto": "125"
}
```

---

## 🎯 Passo 7: Verificar Funcionamento (3 min)

Execute este script de verificação:

```bash
python << 'EOF'
import pandas as pd
import os

# Verificações
checks = {
    "1. Dados brutos existem": os.path.exists('dados/raw/Dados_Antonio.xlsx'),
    "2. Ambiente virtual ativo": 'VIRTUAL_ENV' in os.environ,
    "3. Pandas instalado": True,
    "4. Estrutura de pastas OK": os.path.exists('notebooks') and os.path.exists('src'),
}

print("\n🔍 VERIFICAÇÃO DO AMBIENTE\n")
print("=" * 50)
for check, status in checks.items():
    symbol = "✅" if status else "❌"
    print(f"{symbol} {check}")
print("=" * 50)

if all(checks.values()):
    print("\n🎉 SUCESSO! Ambiente configurado corretamente.")
    print("\n📚 Próximos passos:")
    print("   1. Abra notebooks/01_EDA_Automatico.ipynb")
    print("   2. Execute célula por célula")
    print("   3. Analise os gráficos gerados")
else:
    print("\n⚠️  Há problemas na configuração. Revise os passos anteriores.")

EOF
```

---

## 🚨 Solução de Problemas Comuns

### Problema 1: "ModuleNotFoundError: No module named 'pandas'"

**Solução:**
```bash
# Verifique se o ambiente virtual está ativo
# Deve mostrar (venv) no prompt

# Se não estiver ativo:
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate     # Windows

# Reinstale as dependências
pip install -r scripts/requirements.txt
```

### Problema 2: "FileNotFoundError: Dados_Antonio.xlsx"

**Solução:**
```bash
# Verifique o caminho do arquivo
ls -la dados/raw/

# Se o arquivo não estiver lá, copie-o:
cp /caminho/correto/Dados_Antonio.xlsx dados/raw/
```

### Problema 3: "Permission denied" no Linux/Mac

**Solução:**
```bash
# Dê permissão de execução aos scripts
chmod +x scripts/*.sh
chmod +x scripts/*.py
```

### Problema 4: "Jupyter notebook command not found"

**Solução:**
```bash
# Instale o Jupyter
pip install jupyter notebook

# Ou use o Jupyter Lab (mais moderno)
pip install jupyterlab
jupyter lab
```

### Problema 5: Erro de memória ao carregar Excel

**Solução:**
```python
# Use chunks ou otimize a leitura
import pandas as pd

# Opção 1: Ler apenas colunas necessárias
colunas = ['EndUserName', 'VendorDivision4', '2022', '2023', '2024', '2025']
df = pd.read_excel('dados/raw/Dados_Antonio.xlsx', usecols=colunas)

# Opção 2: Converter para CSV (mais leve)
df = pd.read_excel('dados/raw/Dados_Antonio.xlsx')
df.to_csv('dados/raw/dados_antonio.csv', index=False)

# Depois use CSV
df = pd.read_csv('dados/raw/dados_antonio.csv')
```

---

## 📚 Próximos Passos (após configuração)

### Semana 1-2: Exploração

1. **Executar notebook 01_EDA_Automatico.ipynb**
   - Gera 15+ gráficos
   - Identifica padrões
   - Documenta insights

2. **Executar notebook 02_Feature_Engineering.ipynb**
   - Cria features temporais
   - Calcula RFM
   - Gera dataset para modelagem

### Semana 3-6: Modelagem Inicial

3. **Executar notebook 03_Modelagem_Modulo1_BigDeals.ipynb**
   - Primeiro modelo de classificação
   - Identifica contratos em risco
   - Métricas: F1-Score, Precision, Recall

### Cronograma completo

Consulte: `docs/Cronograma_12_Meses.xlsx`

---

## 🆘 Precisa de Ajuda?

### Documentação completa:
- 📖 `README.md` - Visão geral do projeto
- 📊 `ANALISE_EXPLORATORIA_INICIAL.md` - Análise detalhada dos dados
- 📅 `docs/Cronograma_12_Meses.xlsx` - Planejamento completo

### Contato:
- 📧 Email: antonio_oliveira76@hotmail.com
- 💼 LinkedIn: linkedin.com/in/antoniocruz2776
- 🐙 GitHub Issues: github.com/antoniocruz2776/TCC/issues

---

## ✅ Checklist Final

Antes de prosseguir, certifique-se de que:

- [ ] Ambiente virtual está ativo `(venv)`
- [ ] Todas as bibliotecas instaladas sem erros
- [ ] Arquivo `Dados_Antonio.xlsx` está em `dados/raw/`
- [ ] Consegue importar pandas, numpy, sklearn
- [ ] Jupyter Notebook abre sem erros
- [ ] Script de verificação passou em todos os testes

**Se todos os itens estão marcados:** 🎉 Parabéns! Você está pronto para começar o TCC.

**Se algum item falhou:** 🔧 Revise a seção "Solução de Problemas" acima.

---

**Documento criado em:** 19/02/2026  
**Última atualização:** 19/02/2026  
**Tempo de configuração:** ~30 minutos  
**Nível de dificuldade:** 🟢 Iniciante

---

## 🎓 Dicas Finais

1. **Trabalhe em pequenos incrementos**
   - Execute 1 notebook por vez
   - Valide os resultados antes de prosseguir
   - Documente suas observações

2. **Use controle de versão**
   ```bash
   git add .
   git commit -m "Análise exploratória concluída"
   git push origin main
   ```

3. **Faça backups regulares**
   - Salve os dados processados
   - Exporte os modelos treinados
   - Mantenha cópias dos gráficos

4. **Peça ajuda quando necessário**
   - Abra issues no GitHub
   - Envie email com dúvidas específicas
   - Compartilhe os erros completos

**Boa sorte no seu TCC! 🚀📊🎓**
