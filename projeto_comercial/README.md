# Case de BI: Análise de Vendas Imobiliárias (Colab)

Este projeto reproduz, em **Python/Colab**, um estudo de vendas imobiliárias a partir de três bases:  
**Vendas**, **Empreendimentos** e **Cidades/Regionais**.  
O objetivo é transformar os dados em **insights acionáveis** e **storytelling** de negócio.

> **Premissas do case**: considerar **set/2023** como data atual; gerar insights claros; e discutir como IA pode apoiar decisões. :contentReference[oaicite:0]{index=0}

---

## 1) Estrutura dos dados
- `dataset_venda.xlsx`  
  - Campos-chave: `identificador_empreendimento`, `data_base`, `vendas` (unidades).
- `dataset_empreendimento.xlsx`  
  - Campos: `identificador_empreendimento`, `identificador_cidade`, `total_apartamento`, datas de obra (quando disponíveis).
- `dataset_cidades.xlsx`  
  - Campos: `identificador`, `cidade`, `regional`.

> Os nomes são **padronizados** no notebook (minúsculas, sem acento, `_`).

---

## 2) O que o notebook faz
1. **Integração** das 3 bases: *vendas → empreendimentos → cidades*.  
2. **Medições principais**:
   - Unidades vendidas por **cidade** e por **regional**  
   - **Curva mensal** de vendas  
   - Painel por **empreendimento**:
     - `vendido_total` (acumulado)  
     - `% vendido` (`vendido_total / total_apartamento`)  
     - `estoque` (se informado)  
     - `dias_ate_100` (quando a base permite identificar a primeira data em que o acumulado ≥ total)  
3. **Qualidade / Outliers**:
   - `% vendido > 100%` (possível dado inconsistente)  
   - Vendas negativas (bloqueadas)  
4. **Insights automáticos** (texto gerado a partir dos KPIs).  
5. **Export** de tabelas em CSV (para entrega/validação).

---

## 3) Como executar (Google Colab)
1. Faça upload de:
   - `dataset_venda.xlsx`
   - `dataset_empreendimento.xlsx`
   - `dataset_cidades.xlsx`
2. Cole o código do notebook e **execute** (uma célula só).
3. Ao final, baixe os CSVs gerados (ex.: `kpi_vendas_por_cidade.csv`).

> Se sua coluna `vendas` **não** existe, o notebook automaticamente usa **contagem de linhas** como volume de vendas (fallback).

---

## 4) KPIs & Gráficos incluídos
- **Unidades vendidas por cidade** (Top 10)  
- **Unidades vendidas por regional**  
- **Curva mensal** (linha)  
- **Top empreendimentos por volume**  
- **% vendido por empreendimento**  
- **Velocidade (dias para 100%)**, quando possível

---

## 5) Insights (exemplos)
- Cidade/Regional com **maior volume** de vendas  
- Empreendimento com **maior volume acumulado**  
- **Maior % vendido** (proximidade de esgotamento)  
- **Mais rápido a 100%** (indicativo de alta demanda)  
- **Alerta** de inconsistências (ex.: % vendido > 100%)

---

## 6) Extensões recomendadas
- **Taxa de absorção** mensal por empreendimento/cidade.  
- **Análise de sazonalidade** e efeitos regionais.  
- **Mapa** (geocodificando cidades).  
- **Previsão** de vendas por **ARIMA/Prophet** ou **XGBoost**.  
- **Classificação** de empreendimentos com risco de baixa velocidade de vendas (feature engineering + árvore/SVM).

---

## 7) Limitações
- Sem coluna de **valor** nas vendas, KPI financeiros (receita/ticket) ficam indisponíveis.  
- Datas de obra podem não estar completas → algumas métricas de velocidade podem não ser calculáveis para todos.

---

## 8) Como IA pode ajudar
- **Previsão de demanda** por cidade/empreendimento.  
- **Recomendação de preço e ritmo de lançamento** (otimização).  
- **Segmentação** de empreendimentos por perfil de venda.  
- **Anomalias** (pipeline automático para detectar inconsistências em tempo real).

---

## 9) Arquivos gerados
- `kpi_vendas_por_cidade.csv`  
- `kpi_vendas_por_regional.csv` (se houver)  
- `kpi_vendas_por_mes.csv` (se houver datas)  
- `kpi_painel_empreendimentos.csv`  
- `qualidade_outliers_pct_mais_que_100.csv` (se houver)

---

## 10) Licença
Livre para uso acadêmico/portfólio. Cite a fonte dos dados se aplicável.
