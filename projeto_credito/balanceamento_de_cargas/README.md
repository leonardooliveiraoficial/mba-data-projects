# 📊 **Análise de Crédito**  
> Balanceamento de Classes (Logistic Regression)

---

## **1. Definição do Problema**
O conjunto de dados apresenta um **desbalanceamento significativo (~14% positivos)** na variável-alvo **`inadimplência`**.  
Esse desbalanceamento pode comprometer a performance de classificadores, privilegiando a classe majoritária (adimplentes).  
O objetivo do projeto é **avaliar diferentes técnicas de balanceamento de classes** aplicadas a um modelo de Regressão Logística para melhorar a detecção de inadimplentes.

---

## **2. Coleta de Dados**
- Fonte: dataset acadêmico de crédito.  
- Variáveis de entrada: renda, idade, dívida, entre outras.  
- Variável-alvo: `inadimplência` (0 = adimplente, 1 = inadimplente).  
- Estrutura do conjunto: 2.080 registros, ~14% positivos.

---

## **3. Construção do Modelo**
- **Pré-processamento**: imputação de valores ausentes, codificação categórica (OHE), padronização (StandardScaler).  
- **Classificador base**: Regressão Logística (`LogisticRegression`).  
- **Estratégias avaliadas**:
  - Baseline (sem balanceamento)  
  - Class Weight = Balanced  
  - Random UnderSampling (RUS)  
  - Random OverSampling (ROS)  
  - SMOTE  
  - SMOTEENN  

---

## **4. Avaliação e Métricas**
As métricas utilizadas foram:  
- **F1-score**  
- **ROC AUC**  
- **PR AUC** (principal métrica, pois há desbalanceamento)  
- **Recall da classe positiva (inadimplente)**  

📌 **Resultados médios (5-fold cross-validation):**

| Estratégia                   | F1     | ROC AUC | PR AUC | Recall (1) |
|-------------------------------|--------|---------|--------|------------|
| Baseline (sem balanceamento)  | ~0.799 | 0.88    | 0.88   | 0.76       |
| Class Weight Balanced         | ~0.749 | -       | -      | 0.95       |
| UnderSampling (RUS)           | ~0.768 | -       | 0.88   | 0.97       |
| OverSampling (ROS)            | ~0.784 | -       | 0.88   | 0.94       |
| SMOTE                         | ~0.784 | -       | 0.88   | 0.94       |
| SMOTEENN                      | ~0.794 | -       | 0.88   | 0.97       |

*(valores arredondados dos resultados do notebook)*

---

## **5. Conclusão**
O conjunto está desbalanceado (~14% positivos).  

As técnicas avaliadas apresentaram **PR AUC muito semelhantes (≈0,88)**, indicando que, em termos de precisão-recall global, não há ganhos expressivos entre as estratégias. O **Baseline** obteve o maior **F1 (~0,80)**, mas com **recall mais baixo (~0,76)**.  

Já **SMOTEENN** e **RUS** elevaram significativamente o **recall (≈0,97)** com leve queda no F1, o que é desejável quando a prioridade é capturar o máximo de inadimplentes.  

Assim, recomenda-se:  
- **SMOTEENN** → quando a meta for **maximizar recall** (detecção de inadimplentes).  
- **Baseline com ajuste de limiar** → quando a meta for equilibrar **precisão e recall** (F1).  

Em produção, sugere-se **calibrar o threshold da Regressão Logística** para alinhar a taxa de alertas (positivos) ao custo de falso positivo do negócio.  

---

## **6. Estrutura do Repositório**

- `data/dados_credito.csv` → Base de dados  
- `notebooks/balanceamento_de_classe.ipynb` → Notebook com código e análises  
- `README.md` → Este documento explicativo
