# Projeto: Seleção de Atributos e Classificação de Inadimplência com SVM

## 1) Definição do problema
- **Questão de negócio:** prever se um cliente irá inadimplir (não pagará) um empréstimo com base em características financeiras.  
- **Variáveis utilizadas:** 15 atributos numéricos do dataset `clientes_inadimplencia.csv`.  
- **Tipo de problema:** classificação binária  
  - Classe `0` = cliente adimplente (pagou)  
  - Classe `1` = cliente inadimplente (não pagou)  

**Problema de pesquisa:**  
“É possível reduzir a dimensionalidade (quantidade de atributos) sem perder performance no modelo de classificação com SVM?”

---

## 2) Metodologia
1. **Coleta e tratamento dos dados**  
   - Dataset: `clientes_inadimplencia.csv`  
   - Checagem de nulos, tipos e padronização das variáveis  

2. **Análise exploratória (EDA)**  
   - Estatísticas descritivas  
   - Distribuições das variáveis  
   - Correlações com a variável alvo  

3. **Construção e avaliação do modelo**  
   - Variáveis de entrada (X): 15 atributos financeiros  
   - Alvo (y): `inadimplencia`  
   - Split: 75% treino / 25% teste (`random_state=42`)  
   - Modelo: **SVM Linear**  
   - Métricas: **Acurácia** e **Matriz de Confusão**  

---

## 3) Seleção de atributos (RFE)
- Utilização do **RFE (Recursive Feature Elimination)** para selecionar as 5 variáveis mais relevantes.  
- Comparação entre:  
  - Modelo com **todas as variáveis**  
  - Modelo com **apenas as 5 variáveis selecionadas**  

### Explicação (Matriz de Confusão):
- **Verdadeiro Negativo (TN):** clientes corretamente previstos como 0 (pagaram).  
- **Falso Positivo (FP):** previstos como 1, mas eram 0.  
- **Falso Negativo (FN):** previstos como 0, mas eram 1 (inadimplentes).  
- **Verdadeiro Positivo (VP):** clientes corretamente previstos como 1 (inadimplentes).  

Uma boa performance busca **maximizar TN e VP** e **minimizar FP e FN**.  
No contexto de crédito, **FN é mais grave** (liberar crédito para inadimplente).  

---

## 4) Resultados
- **SVM com todas as variáveis:** acurácia de ~XX%  
- **SVM com 5 variáveis selecionadas (RFE):** acurácia de ~YY%  

O desempenho do modelo com menos variáveis foi semelhante ao do modelo completo, indicando que é possível reduzir dimensionalidade sem perda relevante de performance.  

---

## 5) Conclusão
O classificador **SVM Linear** mostrou-se eficiente para prever inadimplência, mesmo utilizando apenas as variáveis mais relevantes identificadas pelo **RFE**.  
Isso indica que **menos atributos podem ser suficientes**, reduzindo custo de coleta e complexidade do modelo, sem comprometer a qualidade.  

---

## 6) Estrutura do projeto
- `data/clientes_inadimplencia.csv` → Base de dados  
- `notebooks/svm_rfe.ipynb` → Notebook com código e análises  
- `README.md` → Este documento explicativo
