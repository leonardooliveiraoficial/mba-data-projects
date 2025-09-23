# Portfólio de Projetos em Data Analytics

Este repositório reúne projetos desenvolvidos durante meu MBA em Data Science & BI.  
Cada projeto está documentado com definição do problema, metodologia, implementação e resultados.

## Projetos

- [Classificador de Números Inteiros](projeto_classificacao_numerica/README.md)

* Implementação em Python de um classificador numérico.
* Identifica se o número fornecido é positivo/negativo/zero, par/ímpar e primo/não primo.
* Demonstra boas práticas de lógica de programação, estruturas condicionais, modularização em funções, tratamento de erros e registro de logs.

- [Análise de Crédito: Classificação com Naive Bayes Gaussiano](projeto_credito/naive_bayes/README.md)

* Questão de negócio: prever se um cliente irá inadimplir (não pagar) um empréstimo.
* Variáveis utilizadas: renda, idade e valor da dívida.
* Modelo: Naive Bayes Gaussiano.
* Técnicas aplicadas: EDA, tratamento de dados, validação cruzada (10 folds).
* Resultado: acurácia média de 92,5% com alta performance e estabilidade.
 
- [Análise de Crédito: Classificação com SVM Linear e Seleção de Atributos (RFE)](projeto_credito/svm_rfe/README.md)  

* Questão de negócio: prever inadimplência a partir de 15 variáveis financeiras.
* Modelo: SVM Linear.
* Técnica aplicada: RFE (Recursive Feature Elimination) para selecionar as 5 variáveis mais relevantes.
* Resultado: desempenho semelhante ao modelo completo, mostrando que menos atributos podem ser suficientes sem perda significativa de performance.

- [Análise de Crédito: Balanceamento de Classes com Regressão Logística](projeto_credito/balanceamento_classe/README.md)  

* Questão de negócio: lidar com o desbalanceamento de ~14% de inadimplentes no dataset.  
* Modelo: Regressão Logística.  
* Estratégias avaliadas: Class Weight Balanced, UnderSampling (RUS), OverSampling (ROS), SMOTE, SMOTEENN.  
* Resultado: PR AUC semelhante em todas as técnicas (~0,88).  
  - Baseline apresentou maior F1 (~0,80) porém com recall mais baixo (~0,76).  
  - SMOTEENN e RUS atingiram recall ≈0,97 com leve perda de F1, sendo recomendados quando a prioridade é detectar o máximo de inadimplentes.  

---

## Sobre mim
Sou Leonardo Oliveira, Cientista de Dados.  
Tenho experiência em Business Intelligence, desenvolvimento web/mobile e análise de dados.

🔗 [LinkedIn](https://www.linkedin.com/in/leo-de-oliveira) | [GitHub](https://github.com/leonardooliveiraoficial)
