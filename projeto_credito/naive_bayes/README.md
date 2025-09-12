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

## 2) Metodologia
1. **Coleta e tratamento dos dados**  
   - Base `dados_credito.csv`  
   - Checagem de nulos, ajuste de tipos, normalização das variáveis  

2. **Análise exploratória (EDA)**  
   - Distribuição das variáveis  
   - Relações: renda vs dívida, idade vs inadimplência  

---

## 3) Construção e avaliação do modelo
- **Variáveis de entrada (X):** `renda`, `idade`, `divida`  
- **Alvo (y):** `inadimplencia`  
- **Split:** 80% treino / 20% teste (`random_state=42`)  
- **Modelo:** `GaussianNB` (Naive Bayes Gaussiano)  
- **Métrica principal:** **Acurácia**  
- **Métricas adicionais:** Matriz de Confusão + breve explicação  

### Explicação (Matriz de Confusão):
- **Verdadeiro Negativo (TN):** clientes corretamente previstos como 0 (pagaram).  
- **Falso Positivo (FP):** clientes previstos como 1 (não pagaram), mas na verdade eram 0.  
- **Falso Negativo (FN):** clientes previstos como 0, mas na verdade eram 1 (não pagaram).  
- **Verdadeiro Positivo (VP):** clientes corretamente previstos como 1 (não pagaram).  

Uma boa performance busca **maximizar TN e VP** e **minimizar FP e FN**.  
Dependendo do contexto do banco, **FN pode ser mais grave**, pois significa liberar crédito a quem não pagará.

---

## 4) Validação cruzada (10 folds)
A validação cruzada avalia o modelo de forma mais robusta, dividindo os dados em k partes (aqui, k=10).  
Em cada iteração, treina-se em k-1 partes e testa-se na parte restante, rotacionando até cobrir todos os folds.  
Isso reduz a dependência de um único split e fornece uma estimativa mais estável da performance.

- **Acurácias por fold:** `[0.94, 0.905, 0.915, 0.93, 0.9347, 0.9246, 0.9447, 0.9146, 0.9296, 0.9095]`  
- **Média da acurácia:** **92,5%**  
- **Desvio padrão:** **±1,3%**

---

## 5) Conclusão
O classificador **Naive Bayes** conseguiu prever inadimplência com **alta performance e estabilidade**.  
Por ser simples, rápido e interpretável, mostra-se um modelo promissor para cenários de análise de crédito.  

---

## 6) Estrutura do projeto
- `data/dados_credito.csv` → Base de dados  
- `notebooks/Naive_Bayes.ipynb` → Notebook com código e análises  
- `README.md` → Este documento explicativo
