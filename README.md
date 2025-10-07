# 📊 Dashboard Financeiro — Fluxo de Caixa, Despesas por Classificação e Setores

Dashboard desenvolvido no **Microsoft Power BI** para acompanhar **entradas e saídas de caixa**, consolidar **KPIs financeiros** (Receitas, Despesas e Saldo) e detalhar **despesas por classificação e por setor**.  
Tratamento e integração via **Power Query**, modelagem simples e **agregações nativas** nos visuais.

---

## 📢 Sobre
Painel com **visão executiva e operacional** do financeiro: evolução do fluxo de caixa, totais consolidados e composição de despesas.  
Construído a partir de **múltiplos CSVs** (pasta de extratos) e uma **tabela de setores**, aplicando boas práticas de **limpeza, modelagem e design** para garantir **clareza, consistência e tomada de decisão rápida**.

---

## 🎯 Objetivos
- **Tendência:** visualizar a evolução de **Entradas × Saídas** ao longo do tempo e identificar sazonalidades.
- **Panorama:** destacar **Receitas Totais**, **Despesas Totais** e o **Saldo** conforme filtros aplicados.
- **Composição:** entender onde estão os **maiores gastos por classificação** e **quais setores** mais impactam o total.
- **Exploração guiada:** permitir recortes por **Ano/Mês** e **Setor** com agregações configuradas nos visuais.

---

## ⚙️ Processos Realizados (ETL + Modelagem)

**Integração de dados**
- 📁 **Pasta “Extratos” com vários CSVs** (combinados no Power Query).
- 📄 **Tabela de Setores** (CSV/Excel) para enriquecimento e relacionamento.

**Tratamento e limpeza no Power Query**
1. Importar a **Pasta** e **Combinar** os CSVs de *Extratos*.
2. **Remover** a coluna `Origem` (não utilizada).
3. Limpar **Centro de Custo** removendo o prefixo **"CC"**  
   *(Transformar ▸ Extrair ▸ Texto após o delimitador “ ”)*.
4. **Definir `Centro de Custo` como inteiro**.
5. Importar **Setores**.
6. **Ajustar tipos** (`Data`, `Valor`, textos) e validar qualidade.

---

## 🎨 Guia de Cores (Design System)

- **Princípios:** paleta fria (roxo–verde–azul); números com cor única para legibilidade; acabamento discreto.
- **Cores principais:** Entradas `#16C99E` • Saídas `#5F21CE` • Números (KPIs/valores) `#2E2E2E`.
- **Rosca (Setores):** `#5F21CE`, `#16C99E`, `#3A7DFF`, `#A678FF`, `#7CA8FF`.
- **Barras (Classificação):** `#5F21CE`, `#16C99E`, `#3A7DFF`, `#A678FF`, `#7CA8FF`.
- **Acabamento:** borda de separação `#FFFFFF` 1px (opacidade ~45–50%); títulos/rótulos seguem o padrão do dashboard.

---

## 🔧 Como Executar

1. Abra **`Dashboard_Financeiro.pbix`** no **Power BI Desktop**.
2. Se necessário, **ajuste o caminho** da pasta de **CSV** em *Transformar Dados ▸ Fonte*.
3. Clique em **Atualizar** para carregar/atualizar os dados.
4. Utilize as **segmentações** (Ano/Mês e Setor) para explorar.

---

## 🧰 Stack

- **Microsoft Power BI Desktop**
- **Power Query** (Transformações/ETL)

---

## 🗂️ Estrutura do Projeto

- **/data** → contém os dados da análise  
  - `/data/Movimentacoes/` 
  - `Setores.xlsx`

- **/dashboard** → arquivo principal do Power BI  
  - `Dashboard_Financeiro.pbix` (modelagem e visuais)  
  - `Background_Dashboard.svg` (arte de fundo)

- **/images** → capturas de tela do dashboard  

---



