# Projeto: Análise de Crédito com Naive Bayes

## 1) Definição do problema
- **Questão de negócio:** prever se um cliente irá inadimplir (não pagará) um empréstimo com base em suas características socioeconômicas.
- **Variáveis utilizadas:** renda, idade e valor da dívida.
- **Tipo de problema:** classificação binária  
  - Classe `0` = cliente adimplente (pagou)  
  - Classe `1` = cliente inadimplente (não pagou)

**Problema de pesquisa:**  
“Dadas variáveis socioeconômicas simples (renda, idade e dívida), qual a performance de um classificador probabilístico (*Naive Bayes*) para prever inadimplência?”

---

## 2) Etapas do projeto
1. **Coleta e tratamento dos dados**  
   - Base de dados de crédito (`dados de credito.csv`)  
   - Pré-processamento: checagem de nulos, ajustes de tipos, normalização das variáveis  

2. **Análise exploratória (EDA)**  
   - Histogramas e scatterplots das variáveis  
   - Relações: renda vs dívida, idade vs inadimplência  

3. **Construção do modelo**  
   - Algoritmo escolhido: **Naive Bayes Gaussiano**  
   - Divisão treino/teste  
   - Avaliação inicial com matriz de confusão e métricas de classificação  

4. **Validação cruzada (10 folds)**  
   - Técnica utilizada: *StratifiedKFold*  
   - Avaliação mais robusta, reduzindo dependência de um único split  

---

## 3) Resultados
- **Acurácias por fold:** `[0.94, 0.905, 0.915, 0.93, 0.9347, 0.9246, 0.9447, 0.9146, 0.9296, 0.9095]`  
- **Média da acurácia:** `92,5%`  
- **Desvio padrão:** `1,3%`  

O modelo apresentou desempenho **alto e consistente**, mostrando-se adequado como baseline para prever risco de inadimplência.

---

## 4) Conclusão
O classificador **Naive Bayes** conseguiu prever inadimplência com **mais de 92% de acurácia média**, provando-se um modelo robusto e de fácil implementação.  
Esse tipo de modelo pode ser útil em cenários de análise de crédito em que simplicidade, interpretabilidade e velocidade são fatores importantes.

---

## 5) Estrutura do projeto
- `Naive_Bayes.ipynb` → Notebook com código e análises  
- `dados de credito.csv` → Base de dados utilizada  
- `README.md` → Este documento explicativo  

---
