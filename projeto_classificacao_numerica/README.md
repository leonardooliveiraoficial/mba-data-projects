# Projeto: Classificador de Números Inteiros

## 1) Definição do problema
O objetivo deste projeto é implementar um **classificador numérico** em Python.  
Dado um número inteiro fornecido pelo usuário, o programa identifica se ele é:

- Positivo, Negativo ou Zero  
- Par ou Ímpar  
- Primo ou Não Primo  

Este projeto demonstra boas práticas de **lógica de programação**, **estruturas condicionais**, **modularização em funções**, **tratamento de erros** e **registro de logs**.

---

## 2) Metodologia
1. **Entrada de dados**  
   - O usuário fornece um número inteiro via `input()`.  
   - O programa valida a entrada (erro tratado com `try/except`).  

2. **Classificação**  
   - Verifica sinal (positivo/negativo/zero).  
   - Verifica paridade (par/ímpar).  
   - Verifica primalidade (primo/não primo).  

3. **Registro em log**  
   - Cada execução é registrada em `classificador.log` com data/hora e resultado.  

---

## 3) Tecnologias utilizadas
- Python 3  
- Módulo `logging` para registro de execuções  

---

## 4) Como executar

1. **Via notebook (Colab ou Jupyter)**
   - Abra o arquivo `classificador_numero.ipynb`.
   - Rode todas as células.
   - Digite um número quando solicitado:
   - Pressione Enter no teclado

2. **Exemplos de resultados**
- Entrada: `-8` → Saída: “O número -8 é negativo, par e não primo.”  
- Entrada: `0` → Saída: “O número 0 é zero, par e não primo.”  
- Entrada: `13` → Saída: “O número 13 é positivo, ímpar e primo.”  

