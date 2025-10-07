# 📊 Dashboard Financeiro — Fluxo de Caixa, Despesas por Classificação e Setores

Dashboard em **Microsoft Power BI** para acompanhar **entradas e saídas**, consolidar **KPIs** (Receitas, Despesas e Saldo) e detalhar **despesas por classificação e por setor**.  
Tratamento e integração via **Power Query**, modelagem simples e **agregações nativas** nos visuais.

## ✨ Destaques
- Visão executiva de **fluxo de caixa** e **KPIs**.
- Detalhamento de **despesas por classificação** e **por setor**.
- Segmentações por **Ano/Mês** e **Setor**.
- Paleta fria consistente (roxo–verde–azul) com **números padronizados** para legibilidade.

---

## 📢 Sobre
Painel com visão **executiva e operacional**: evolução do fluxo, totais consolidados e composição de despesas.  
Baseado em **múltiplos CSVs** (pasta de extratos) e **tabela de setores**, com boas práticas de **limpeza, modelagem e design** para garantir **clareza e consistência**.

---

## 🎯 Objetivos
- **Tendência:** visualizar a evolução de **Entradas e Saídas** e identificar sazonalidades.
- **Panorama:** destacar **Receitas Totais**, **Despesas Totais** e o **Saldo** conforme filtros.
- **Composição:** entender **maiores gastos por classificação** e **setores de maior impacto**.
- **Exploração:** permitir recortes por **Ano/Mês** e **Setor** com agregações configuradas nos visuais.

---

## ⚙️ Processos (ETL + Modelagem)

**Integração de dados**
- 📁 Pasta **Extratos** com vários CSVs (combinados no Power Query).
- 📄 **Setores.xlsx** para enriquecimento/relacionamento.

**Tratamento no Power Query**
1. Importar a **Pasta** e **Combinar** os CSVs de *Extratos*.
2. Remover a coluna **Origem**.
3. Limpar **Centro de Custo** (remover prefixo “CC”: *Extrair ▸ Texto após delimitador*).
4. Definir **Centro de Custo** como **inteiro**.
5. Importar **Setores**.
6. Ajustar tipos (`Data`, `Valor`, textos) e validar qualidade.

**Modelagem**
- Relacionamento **muitos-para-um**: `Extratos (fato)` ➜ `Setores (dim)` via **Centro de Custo**.
- Filtros funcionais por **Ano/Mês** e **Setor**.
- KPIs/valores com **Soma de `Valor`** e filtros do relatório.

---

## 🎨 Guia de Cores (Design System)

- **Princípios:** paleta fria (roxo–verde–azul); números em cor única; acabamento discreto.
- **Principais:** Entradas `#16C99E` • Saídas `#5F21CE` • Números `#2E2E2E`.
- **Rosca (Setores):** `#5F21CE`, `#16C99E`, `#3A7DFF`, `#A678FF`, `#28E0B5`.
- **Barras (Classificação):** `#5F21CE`, `#16C99E`, `#3A7DFF`, `#A678FF`, `#7CA8FF`.
- **Acabamento:** borda `#FFFFFF` 1px (opacidade ~45–50%); títulos/rótulos no padrão do dashboard.

---

## 🔧 Como Executar

1. Abra **`Dashboard/Dashboard_Financeiro.pbix`** no **Power BI Desktop**.
2. Se necessário, ajuste o caminho da pasta de **dados** em *Transformar Dados ▸ Fonte*.
3. **Atualize os dados**.
4. Use as segmentações de **Ano/Mês** e **Setor** para explorar.

---

## 🗂️ Estrutura do Projeto

- **/data** → contém os dados da análise  
  - `/data/Movimentacoes/` (arquivos de movimentos)  
  - `Setores.xlsx` (tabela de referência)

- **/dashboard** → arquivo principal do Power BI  
  - `Dashboard_Financeiro.pbix` (modelagem e visuais)  
  - `Background_Dashboard.svg` (arte de fundo)

---

## 🧰 Stack
- **Microsoft Power BI Desktop**
- **Power Query** (ETL/transformações)
